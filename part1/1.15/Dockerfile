FROM python:3.7.3
RUN git clone https://github.com/hd4niel/Lyrics-generation-webpage.git
WORKDIR Lyrics-generation-webpage
RUN pip install -r requirements.txt
EXPOSE 5000
CMD ["python", "main.py"] 
