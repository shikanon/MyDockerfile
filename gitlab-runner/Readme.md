# Puppeteer 镜像

version:
- gitlab-runner: 13.6.03
- kubectl：1.19.0
- docker: 19.03.14

## Running

```bash
docker run -it --name gitlab-runner registry.cn-shenzhen.aliyuncs.com/shikanon/gitlab-runner run 
--user=gitlab-runner --working-directory=/home/gitlab-runner
```