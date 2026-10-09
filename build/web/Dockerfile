# Upstream's Dockerfile (XBEN-006-24/app/Dockerfile) with these changes:
# - the sources are copied from app/app/ (the vendored benchmark folder sits in app/)
# - the build argument FLAG defaults to this lab's fixed flag, the value upstream's Makefile passes
#   (FLAG{sha256 of "XBEN-006-24"}), since the spec passes no build arguments

FROM tiangolo/uvicorn-gunicorn-fastapi:python3.9

COPY app/app/ /app

ARG FLAG=FLAG{9c935b35ad7746d14fa2c01708b767f4cb0a9eaa867e77af44c14592439e53eb}

RUN sed -i s/FLAG/$FLAG/g flag.txt

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]
