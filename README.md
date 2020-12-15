# nginx-variable

# Embedded Variables
The ngx_http_core_module module supports embedded variables with names matching the Apache Server variables. First of all, these are variables representing client request header fields, such as $http_user_agent, $http_cookie, and so on. Also there are other variables:

## $arg_name

argument name in the request line

## $args
arguments in the request line

## $binary_remote_addr
client address in a binary form, value’s length is always 4 bytes for IPv4 addresses or 16 bytes for IPv6 addresses

## $body_bytes_sent
number of bytes sent to a client, not counting the response header; this variable is compatible with the “%B” parameter of the mod_log_config Apache module
## $bytes_sent
number of bytes sent to a client (1.3.8, 1.2.5)
## $connection
connection serial number (1.3.8, 1.2.5)
## $connection_requests
current number of requests made through a connection (1.3.8, 1.2.5)
## $content_length
“Content-Length” request header field
## $content_type
“Content-Type” request header field
## $cookie_name
the name cookie
## $document_root
root or alias directive’s value for the current request
## $document_uri
same as $uri
## $host
in this order of precedence: host name from the request line, or host name from the “Host” request header field, or the server name matching a request
## $hostname
host name
## $http_name
arbitrary request header field; the last part of a variable name is the field name converted to lower case with dashes replaced by underscores
## $https
“on” if connection operates in SSL mode, or an empty string otherwise
## $is_args
“?” if a request line has arguments, or an empty string otherwise
## $limit_rate
setting this variable enables response rate limiting; see limit_rate
## $msec
current time in seconds with the milliseconds resolution (1.3.9, 1.2.6)
## $nginx_version
nginx version
## $pid
PID of the worker process
## $pipe
“p” if request was pipelined, “.” otherwise (1.3.12, 1.2.7)
## $proxy_protocol_addr
client address from the PROXY protocol header (1.5.12)
The PROXY protocol must be previously enabled by setting the proxy_protocol parameter in the listen directive.

## $proxy_protocol_port
client port from the PROXY protocol header (1.11.0)
The PROXY protocol must be previously enabled by setting the proxy_protocol parameter in the listen directive.

## $proxy_protocol_server_addr
server address from the PROXY protocol header (1.17.6)
The PROXY protocol must be previously enabled by setting the proxy_protocol parameter in the listen directive.

## $proxy_protocol_server_port
server port from the PROXY protocol header (1.17.6)
The PROXY protocol must be previously enabled by setting the proxy_protocol parameter in the listen directive.

## $query_string
same as $args
## $realpath_root
an absolute pathname corresponding to the root or alias directive’s value for the current request, with all symbolic links resolved to real paths
## $remote_addr
client address
## $remote_port
client port
## $remote_user
user name supplied with the Basic authentication
## $request
full original request line
## $request_body
request body
The variable’s value is made available in locations processed by the proxy_pass, fastcgi_pass, uwsgi_pass, and scgi_pass directives when the request body was read to a memory buffer.

## $request_body_file
name of a temporary file with the request body
At the end of processing, the file needs to be removed. To always write the request body to a file, client_body_in_file_only needs to be enabled. When the name of a temporary file is passed in a proxied request or in a request to a FastCGI/uwsgi/SCGI server, passing the request body should be disabled by the proxy_pass_request_body off, fastcgi_pass_request_body off, uwsgi_pass_request_body off, or scgi_pass_request_body off directives, respectively.

## $request_completion
“OK” if a request has completed, or an empty string otherwise
## $request_filename
file path for the current request, based on the root or alias directives, and the request URI
## $request_id
unique request identifier generated from 16 random bytes, in hexadecimal (1.11.0)
## $request_length
request length (including request line, header, and request body) (1.3.12, 1.2.7)
## $request_method
request method, usually “GET” or “POST”
## $request_time
request processing time in seconds with a milliseconds resolution (1.3.9, 1.2.6); time elapsed since the first bytes were read from the client
## $request_uri
full original request URI (with arguments)
## $scheme
request scheme, “http” or “https”
## $sent_http_name
arbitrary response header field; the last part of a variable name is the field name converted to lower case with dashes replaced by underscores
## $sent_trailer_name
arbitrary field sent at the end of the response (1.13.2); the last part of a variable name is the field name converted to lower case with dashes replaced by underscores
## $server_addr
an address of the server which accepted a request
Computing a value of this variable usually requires one system call. To avoid a system call, the listen directives must specify addresses and use the bind parameter.

## $server_name
name of the server which accepted a request
## $server_port
port of the server which accepted a request
## $server_protocol
request protocol, usually “HTTP/1.0”, “HTTP/1.1”, or “HTTP/2.0”
## $status
response status (1.3.2, 1.2.2)
## $tcpinfo_rtt, $tcpinfo_rttvar, $tcpinfo_snd_cwnd, $tcpinfo_rcv_space
information about the client TCP connection; available on systems that support the TCP_INFO socket option
## $time_iso8601
local time in the ISO 8601 standard format (1.3.12, 1.2.7)
## $time_local
local time in the Common Log Format (1.3.12, 1.2.7)
## $uri
current URI in request, normalized
The value of $uri may change during request processing, e.g. when doing internal redirects, or when using index files.
