FROM node:20-alpine

# 必要なパッケージをインストール
RUN apk add --no-cache git

# pnpmをグローバルにインストール
RUN npm install -g pnpm

# アプリケーションディレクトリを作成
WORKDIR /workspace

# 非rootユーザーを使用（セキュリティのため）
ARG USERNAME=node
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# ユーザーがsudoを使えるようにする
RUN apk add --no-cache sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# コンテナ起動時に実行されるコマンド（コンテナが起動し続けるように）
CMD [ "sleep", "infinity" ]
