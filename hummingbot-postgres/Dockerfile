FROM docker.io/hummingbot/hummingbot:version-1.24.0
RUN conda install --name hummingbot psycopg2
CMD ["/bin/bash", "-lc", "conda activate hummingbot && ./bin/hummingbot_quickstart.py -p $HUMMINGBOT_PASSWORD | tee ./logs/errors.log"]
