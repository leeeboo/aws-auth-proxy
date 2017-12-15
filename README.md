#aws-auth-proxy

##Installation

pre-reqs:
* go1.5
* [glide package manager](https://github.com/Masterminds/glide)

```sh
#requires go1.5
export GO15VENDOREXPERIMENT=1

mkdir -p $GOPATH/src/github.com/leeeboo
cd $GOPATH/src/github.com/leeeboo
git clone https://github.com/leeeboo/aws-auth-proxy
cd aws-auth-proxy
glide install
go build github.com/leeeboo/aws-auth-proxy
```
##Example

```sh
# aws elasticsearch example
./aws-auth-proxy \
-access-key=xxx \
-secret-key=xxxx \
-service-name=es \
-region-name=<your-aws-region> \
-upstream-host=<your-aws-elastic-search-endpoint> \
-upstream-scheme=https \
-listen-address=":9200"
```

Your proxied elasticsearch endpoint is now here: [http://localhost:9200](http://localhost:9200)


No more securing elastic search endpoints with IP addresses!



