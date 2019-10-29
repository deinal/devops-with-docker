# Chose slim buster over alpine because of the extensive 
# amount of libraries used in my app
# Also speed (?) https://pythonspeed.com/articles/base-image-python-docker-images/
FROM python:3.7-slim-buster

WORKDIR /app

# I have a dockerignorefile I did not have before. It most importantly omits virtual 
# environment files and pycache when copying below
COPY . .

# All run statements in one for less layers. Change of user for security reasons.
# https://medium.com/@mccode/processes-in-containers-should-not-run-as-root-2feae3f0df3b
RUN pip install -r requirements.txt && \
    useradd -m chad && \
    chown -R chad .

# Run as non root user
USER chad

# docker run -p 5000:5000 lightlyrics
EXPOSE 5000
CMD ["python", "main.py"] 

# All in all size went from 2.39GB to 981MB
# It is still big because the machine learning model in the app needs a 
# ridiculous amount of libraries
