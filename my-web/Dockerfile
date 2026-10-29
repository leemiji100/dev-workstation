# 1. 기존 nginx 틀을 가져온다 (가벼운 alpine 버전)
FROM nginx:alpine

# 2. 이 틀에 이름표를 붙인다
LABEL org.opencontainers.image.title="my-custom-web"

# 3. 환경 변수를 넣는다 (지금은 개발 모드)
ENV APP_ENV=dev

# 4. 내 웹페이지를 nginx가 보여주는 폴더에 복사한다
COPY site/ /usr/share/nginx/html/

# 5. 이 컨테이너는 80번 문을 쓴다고 알려준다
EXPOSE 80

# 6. 30초마다 웹서버가 살아 있는지 스스로 검사한다
HEALTHCHECK --interval=30s --timeout=3s \
  CMD wget -qO- http://localhost/ || exit 1
