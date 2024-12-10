FROM pytorch/pytorch AS build
ENV TZ "Europe/Brussels"

RUN mkdir alltalk
RUN cd alltalk
RUN git clone -b alltalkbeta https://github.com/erew123/alltalk_tts
RUN cd alltalk_tts
RUN ./atsetup.sh -silent

WORKDIR /home/alltalk/alltalk_tts
CMD ./start_finetune.sh
EXPOSE 7052
