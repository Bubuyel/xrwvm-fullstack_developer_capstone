FROM python:3.9.18-slim-bookworm


WORKDIR /python-docker

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt
COPY . .

# Make the bundled VADER lexicon available to NLTK
ENV NLTK_DATA=/python-docker/nltk_data
RUN mkdir -p /python-docker/nltk_data/sentiment \
    && cp /python-docker/sentiment/vader_lexicon.zip /python-docker/nltk_data/sentiment/vader_lexicon.zip

RUN ls
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]
