# pandas
#Informacion analisis de datos de python

#Agrupar datos de series de tiempo

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Para 7 dias de 24 horas con 60 minutos
periodo = 7 * 24 * 60
tidx = pd.date_range('2016-07-01', periods=periodo, freq='T')

#                        ^                 ^
#                        |                 |
#                fecha comienzo       frecuencia   codigo para minutos

# Genera datos aleatorios con numpy. We'll seed the random
# number generator so that others can see the same results.
# Otherwise, you don't have to seed it.
np.random.seed([3,1415])

# This will pick a number of normally distributed random numbers
# los numeros son especificado por periodo
data = np.random.randn(periodo)
ts = pd.Series(data=data, index=tidx, name='HelloTimeSeries')
ts.describe()


