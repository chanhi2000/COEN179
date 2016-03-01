# insertionSort

## PSEUDOCODE
```cpp
void insertion(itemType a[], int N) {
    int i,j;

    for (i = 2; i<=N; i++) {
		j = i;
		while ((a[j-1] > a[j]) && (j>1)) {
	    	swap(a, j-1, j);
	    	j--;
		}
    }
}
```

## EXAMPLE
<pre>
<font size="+4"><b>I</b><font face="Courier New,Courier">NSERTION</font></font>
<br><font size="+4"><b>I</b><b>N</b><font face="Courier New,Courier">SERTION</font></font>
<br><font size="+4"><b>I</b><b>NS</b><font face="Courier New,Courier">ERTION</font></font>
<br><font size="+4"><b>IN</b><b>SE</b><font face="Courier New,Courier">RTION</font></font>
<br><font size="+4"><b>IN</b><b><font color="#FF6600">ES</font></b><font face="Courier New,Courier">RTION</font></font>
<br><font size="+4"><b>I</b><b><font color="#FF9900">EN</font>S</b><font face="Courier New,Courier">RTION</font></font>
<br><b><font size="+4"><font color="#FF9900">EI</font>NSR</font></b><font face="Courier New,Courier"><font size="+4">TION</font></font>
<br><font size="+4"><b>EIN<font color="#FF9900">RS</font></b><font face="Courier New,Courier">TION</font></font>
<br><font size="+4"><b>EINRST</b><font face="Courier New,Courier">ION</font></font>
<br><font size="+4"><b>EINRSTI</b><font face="Courier New,Courier">ON</font></font>
<br><b><font size="+4">EINRS<font color="#FF9900">IT</font></font></b><font face="Courier New,Courier"><font size="+4">ON</font></font>
<br><b><font size="+4">EINR<font color="#FF9900">IS</font>T</font></b><font face="Courier New,Courier"><font size="+4">ON</font></font>
<br><b><font size="+4">EIN<font color="#FF9900">IR</font>ST</font></b><font face="Courier New,Courier"><font size="+4">ON</font></font>
<br><b><font size="+4">EI<font color="#FF9900">IN</font>RST</font></b><font face="Courier New,Courier"><font size="+4">ON</font></font>
<br><font size="+4"><b>EIINRSTO</b><font face="Courier New,Courier">N</font></font>
<br><font size="+4"><b>EIINRS<font color="#FF9900">OT</font></b><font face="Courier New,Courier">N</font></font>
<br><b><font size="+4">EIINR<font color="#FF9900">OS</font>T</font></b><font face="Courier New,Courier"><font size="+4">N</font></font>
<br><b><font size="+4">EIIN<font color="#FF9900">OR</font>ST</font></b><font face="Courier New,Courier"><font size="+4">N</font></font>
<br><b><font size="+4">EIINORSTN</font></b>
<br><b><font size="+4">EIINORS<font color="#FF9900">NT</font></font></b>
<br><b><font size="+4">EIINOR<font color="#FF9900">NS</font>T</font></b>
<br><b><font size="+4">EIINO<font color="#FF9900">NR</font>ST</font></b>
<br><b><font size="+4">EIIN<font color="#FF9900">NO</font>RST</font></b>
</pre>
