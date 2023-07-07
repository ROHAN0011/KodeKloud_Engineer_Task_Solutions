[Login to given app server then switch to root]

``
docker images
``
``
docker save -o /tmp/games.tar ecommerce:xfusion
``
``
ll /tmp/
``
``
scp /tmp/ecommerce.tar banner@stapp03:/tmp
``
[From existing app server login to app server which is given to copy .tar file then switch to root]
`
cd /tmp
`
`
ll
`
`
systemctl start docker
`
`
systemctl status docker
`
`
docker load -i ecommerce.tar
`
`
docker images
`
