FROM python:3

WORKDIR /usr/src/app

RUN pip install scikit-learn
RUN pip install numpy
RUN pip install pandas
RUN pip install matplotlib

COPY . .
CMD [ "python", "regressor.py" ]

