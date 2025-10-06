ARG PYTHON_VERSION=3.13.7-alpine3.22

FROM python:${PYTHON_VERSION}

RUN apk update && apk upgrade

WORKDIR /server

COPY . .

RUN python -m pip install --user --upgrade pip && \
	python -m pip install --user --no-cache-dir -r requirements.txt

EXPOSE 8000

CMD ["python", "-m", "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]