FROM registry.access.redhat.com/ubi8/python-39:1-73

WORKDIR /app
COPY requirements.txt /app/requirements.txt
RUN pip3 install -r requirements.txt

ARG SERVICE_PORT=8050
ENV GRPC_SERVER_URL="localhost:8085" \
    TONE_CLASSIFICATION_STOCK_MODEL="classification_ensemble-workflow_lang_en_tone-stock" \
    NLP_MODEL_SERVICE_TYPE="mm-model-id" \
    PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=python \
    SERVICE_PORT=${SERVICE_PORT}

EXPOSE ${SERVICE_PORT}

COPY ./*.py /app
COPY ./assets /app/assets
CMD ["python3","Tone_dash_app.py"]
