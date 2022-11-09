---
title: "Test Note 1"
subtitle: This is just a test of the local extreme weather response system
date: 2022-09-13T18:22:18-04:00
draft: true
tags: 
  - test
toc: false
nonProject: true

---

# This is a Test note

Indeed Very Note like 
 asdlfkasdhfasd
 ads;lkfjasdklfjasd;lkfajsdkl;fjas
 dfaskdl;jfaksldjfas
 dfasl;djflkasdjfklas
 dfaslk;djfklasdjfa
 s
 ## Now for somthing completely Different

```go 
// Servers defines a slice of Server
type Servers []*Server

// GetServers returns all servers from the database
func GetServers() (Servers, error) {
	pool, err := server_database.GetServersDBConnPool()
	if err != nil {
		return nil, err
	}
	var servers []*Server
	err = pgxscan.Select(context.Background(), pool, &servers, sqlGetAllServers)
	var pgErr *pgconn.PgError
	if err != nil {
		// Checks if the error is PG Error
		if errors.As(err, &pgErr) {
			// Break out into a switch statement
			switch pgErr.Code {
			case pgerrcode.CaseNotFound:
				return nil, ErrServerNotFound
			default:
				log.Println(errGenericSQLERROR, pgErr)
				return nil, pgErr
			}
		} else {
			log.Panic("[ERROR]: Expected SQL Error got something else:  ", err)
			return nil, err
		}
	}
	return servers, nil
}
```