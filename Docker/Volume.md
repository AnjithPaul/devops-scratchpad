#devOps #docker #volume
## Volume

- **==Anonymous==** Volume
		-  created with VOLUME layer in dockerfile or `-v <WORKDIR>`
		- get removed after container removed with `-rm` flag
		- will get **orphaned** if container is removed manually
		- `docker volume prune` to remove orphans
- **==Named==** Volume
		- created with `-v <name>:<WORKDIR>` flag
		- doesn't get removed even if container is removed
		- managed by **docker**
- **==Bind Mount==**
		- created with `-v "<absolutePathToCode>:<WORKDIR>"`
		- managed by **user**
		- other processes besides docker can access and modify the storage
		- files in bind mounted local volume will **override** files in container (e.g: files created with npm install in container)
		- to avoid overriding by local files, add required container files to anonymous volume.
		- if multiple volumes are used **more specific path wins**. (*eg: WORKDIR is bindmounted and WORKDIR/node_modules is Anonymous volume, node_modules in anonymous volume will be used instead of the one in bind mount*)
		- as local files overrides container files, change in **code will be immediately reflected** in container without building new image. (new code will be reflected after **restarting** the container, unless by using tools like **nodemon** which will automatically detect code change and restart the container)
- ==Read Only== 
		- Any Volume can be made read only by adding **`:ro`** tothe end of container path (*e.g: `-v <absolutePath>:<WORKDIR>:ro`*)
		- While making a bindmount read only, specify the folders which need write access as anonymous/named volumes.
		- Adding `/app/temp` as anonymous volume is better for **performance**