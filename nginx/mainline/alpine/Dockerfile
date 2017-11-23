FROM alpine:3.6

RUN apk add --update nginx && rm -rf /var/cache/apk/*

COPY nginx.non-root.conf /etc/nginx/nginx.conf
COPY index.html /usr/share/nginx/html/index.html



# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /tmp/access.log \
	&& ln -sf /dev/stderr /tmp/error.log

USER nobody

CMD ["nginx", "-g", "daemon off;"]
