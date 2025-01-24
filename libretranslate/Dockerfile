FROM libretranslate/libretranslate:latest

USER 1000:1000

WORKDIR /app

COPY ./libretranslate_startup.sh .

EXPOSE 5000

ENTRYPOINT ["/usr/bin/env"]

CMD [ "bash", "./libretranslate_startup.sh" ]