FROM docker.io/hummingbot/hummingbot:version-1.24.0
RUN conda install --name hummingbot psycopg2
CMD ["/bin/bash", "-lc", "conda activate hummingbot && ./bin/hummingbot_quickstart.py | tee ./logs/errors.log"]
