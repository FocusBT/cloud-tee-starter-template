FROM python:3.11

WORKDIR /tmp

# poetry
RUN pip install poetry==1.8.5
COPY pyproject.toml poetry.lock ./
RUN poetry export -f requirements.txt --output requirements.txt --without-hashes \
    && pip install --no-cache-dir --upgrade -r requirements.txt \
    && rm -rf requirements.txt

WORKDIR /app
COPY ./ ./
EXPOSE 8000

ENTRYPOINT ["./entrypoint.sh"]
# trigger redeploy
# trigger redeploy
