## docker 如何运行
### 建立openclaw docker
docker volume create openclaw_config
docker run -it --rm  --gpus all  --network research-net --name openclaw_research   -v ./config:/home/node/.openclaw    -v  /mnt/nfs/eye_video_HD/notebook:/notebook  -p 18789:18789   --shm-size=16g   fourplayers/openclaw:latest 
docker run -it -d  --gpus all  --network research-net --name openclaw_research   -v ./config:/home/node/.openclaw    -v  /mnt/nfs/eye_video_HD/notebook:/notebook  -p 18789:18789   --shm-size=16g   fourplayers/openclaw:latest 
### 进入openclaw docker
docker exec -it openclaw_research bash
### 配置openclaw
openclaw configure
openclaw pairing approve telegram ***
openclaw config set agents.defaults.memorySearch.model nomic-embed-text:latest

wget https://github.com/Yakitrak/notesmd-cli/releases/download/v0.3.4/notesmd-cli_0.3.4_linux_amd64.tar.gz
cp notesmd-cli /usr/local/bin/
chmod +x /usr/local/bin/notesmd-cli



## 更新 openclaw
docker pull  fourplayers/openclaw:latest
docker stop openclaw_research
docker rm openclaw_research
docker run -it -d --gpus all  --network research-net --name openclaw_research   -v ./config:/home/node/.openclaw    -v  /mnt/nfs/eye_video_HD/notebook:/notebook  -p 18789:18789   --shm-size=16g   fourplayers/openclaw:latest 


 

## openclaw 工作
1. 整理文件夹
notebook文件夹大量的文件进行清理













