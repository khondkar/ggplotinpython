import matplotlib as plt
    from pandas import Series, DataFrame
    df = pd.io.data.get_data_yahoo([ 'GE', 'KO', 'MSFT' ],
                                   start=datetime.datetime(2014, 1, 5), 
                                   end=datetime.datetime(2015, 10,5 ))['Adj Close']
    df['Date'] = df.index
    df = pd.melt(df, id_vars='Date')
    %matplotlib inline
    from ggplot import*
    ggplot(aes(x='Date',y='value',color= 'variable'),data=df)+geom_line()+ggtitle('Stock performance')


![png](output_1_0.png)





    <ggplot: (28832618)>




    
