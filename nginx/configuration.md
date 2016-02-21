### Why does nginx return 404 not found from mean server when loading assets?

I have an nginx reverse proxy that cannot get assets from upstream mean stack server. It's a single page app that is very small. The index file will load just fine but all assets respond with 404 not found. 

Remove this section:
```
location ~ ^/(assets|fonts|system)/|favicon.ico|robots.txt {
  gzip_static on;
  expires max;
  add_header Cache-Control public;
}
```
