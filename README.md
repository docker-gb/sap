sha256:dacf92d3639ca38f523009a1e286cedf1e851d9943ed808f9db59c4ac39c3193


# Step 1: 拉取原始镜像
docker pull uncleluo/mous:latest

# Step 2: 重命名为 GHCR 格式
docker tag uncleluo/mous:latest ghcr.io/docker-gb/sap:latest

# Step 3: 登录 GHCR（使用 GitHub PAT）
https://github.com/settings/tokens ①write:packages  ②read:packages  ③repo（如果你的仓库是私有的）

echo YOUR_GITHUB_PAT | docker login ghcr.io -u YOUR_GITHUB_USERNAME --password-stdin

# Step 4: 推送到 GHCR
docker push ghcr.io/docker-gb/sap:latest

# Step 5: 检查是否可以匿名拉取
docker logout ghcr.io<div>
docker pull ghcr.io/docker-gb/sap:latest<div>
