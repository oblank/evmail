evmail
=====

imap and smtp email management package

Licence: FreeBSD

donation
--------

[![Flattr this git repo](http://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?category=software&language=go&tags=github&title=evmail&url=https%3A%2F%2Fgithub.com%2Fevalgo%2Fevmail&user_id=franciscsimon)

documentation
-------------
[package documentation at go.pkgdoc.org](http://go.pkgdoc.org/github.com/evalgo/evmail)

git commit hooks
-----------------------
enable commit hooks via

        cd .git ; rm -rf hooks; ln -s ../git-hooks hooks ; cd ..

continous integration
---------------------

[![Build Status](https://drone.io/github.com/evalgo/evmail/status.png)](https://drone.io/github.com/evalgo/evmail/latest)

usage
=====

sending simple mail
-------------------

```go
Mail := NewEVMailEmail()
Mail.User = "<sender@address.com>"
Mail.Password = "<secret_password>"
Mail.Server = "smtp.address.com"
Mail.Port = 587
Mail.To = []string{"<receipient@address.com>"}
Mail.From = "<sender@address.com>"
Mail.Subject = "Hello from EVMail!"
Mail.Body = "EVMail content here ..."
err := Mail.Send()
if err != nil {
	log.Fatal(err)
}
```

sending mail with attachment
----------------------------

```go
Mail := NewEVMailEmail()
Mail.User = "<sender@address.com>"
Mail.Password = "<secret_password>"
Mail.Server = "smtp.address.com"
Mail.Port = 587
Mail.To = []string{"<receipient@address.com>"}
Mail.From = "<sender@address.com>"
Mail.Subject = "Hello from EVMail!"
Mail.Body = "EVMail content here ..."
Mail.Attach("/path/to/your/file")
err := Mail.Send()
if err != nil {
	log.Fatal(err)
}
```
