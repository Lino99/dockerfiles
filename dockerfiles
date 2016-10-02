FROM python:latest

MAINTAINER CoGe <xbian99@gmail.com>

RUN apt-get update && apt-get install -y --no-install-recommends \
	git \
	libav-tools \
	libffi-dev \
	libopus-dev \
	libssl-dev \
	unzip

RUN apt-get clean

RUN rm -rf /var/lib/apt/lists/*

RUN pip install -U \
	git+https://github.com/Rapptz/discord.py@master#egg=discord.py[voice] \
	imgurpython \
	youtube_dl \
	feedparser 

RUN git clone -b develop --single-branch https://github.com/Twentysix26/Red-DiscordBot.git /app

VOLUME /app/data
WORKDIR /app

CMD ["python", "./red.py", "--no-prompt"]
