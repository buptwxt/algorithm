递归求N位格雷码，利用对称原则

```
vector<string> geneNGrayCode(int n)
{
    vector<string> vs;

    if ( n == 1 )
    {
        string s1 = "0";
        string s2 = "1";
        vs.push_back(s1);
        vs.push_back(s2);
        return vs;
    }

    vector<string> vecStrRet = geneNGrayCode( n-1 );
    vector<string> vecStrRet2;
    for( int k =0; k<2; k++ )
    {
        string temp = "0";
        if( k == 1)
        {
            temp = "1";
        }

        for( vector<string>::iterator iter = vecStrRet.begin();
             iter != vecStrRet.end(); iter++ )
        {
            vecStrRet2.push_back( temp + *iter );
        }
    }
    return vecStrRet2;
}
```

验证结果
```
int main()
{
    vector<string> vecStrRet = geneNGrayCode(3);
    vector<string>::iterator iter = vecStrRet.begin();
    for( ; iter != vecStrRet.end() ; iter++ )
    {
        cout << *iter << endl;
    }
    cout << "Hello World!" << endl;
    return 0;
}
```