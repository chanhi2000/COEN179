# mergeSort

## PSEUDOCODE
```cpp
void mergesort(int a[], int left, int right) {
    int i, j, k, mid;
    if (right > left) {
		mid = (left+right)/2;
		mergesort(a, left, mid);
		mergesort(a, mid+1, right);

		for (i=mid+1; i > left; i--)
			b[i-1] = a[i-1];
		for (j=mid; j < right; j++)
			b[right+mid-j] = a[j+1];
		for (k=left; k <= right; k++)
	    	a[k] = (b[i] < b[j]) ? b[i++] : b[j--];
    }
}
```

## EXAMPLE
<pre>
	<b><font size="+4">MERGESORT</font></b>
	<br><b><font size="+4">MERGE<font color="#999999">SORT</font></font></b>
	<br><b><font size="+4">MER<font color="#999999">GE</font><font color="#CCCCCC">SORT</font></font></b>
	<br><b><font size="+4"><font color="#000000">ME</font><font color="#999999">R</font><font color="#CCCCCC">GE</font><font color="#999999"></font><font color="#CCCCCC">SORT</font></font></b>
	<br><b><font size="+4"><font color="#000000"><u>M</u></font><font color="#999999">E</font><font color="#CCCCCC">RGE</font><font color="#999999"></font><font color="#CCCCCC">SORT</font></font></b>
	<br><b><font size="+4"><font color="#999999"></font><u><font color="#FF6600">M</font></u><font color="#999999"></font><font color="#000000"><u>E</u></font><font color="#CCCCCC">R</font><font color="#999999"></font><font color="#CCCCCC">GE</font><font color="#999999"></font><font color="#CCCCCC">SORT</font></font></b>
	<br><font color="#CCCCCC">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font><b><font size="+4"><font color="#CCCCCC"></font><font color="#3366FF">M | E</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#FF6600"><u>EM</u></font><font color="#CCCCCC">R</font><font color="#999999"></font><font color="#CCCCCC">GE</font><font color="#999999"></font><font color="#CCCCCC">SORT</font></font></b>
	<br><b><font size="+4"><font color="#CCCCCC"></font><font color="#FF6600"><u>EM</u></font><font color="#000000"><u>R</u></font><font color="#CCCCCC">GESORT</font></font></b>
	<br><font color="#CCCCCC">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font><b><font size="+4"><font color="#CCCCCC"></font><font color="#3366FF">EM | R</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><u><font color="#FF6600">EMR</font></u><font color="#000000"></font><font color="#CCCCCC">GESORT</font></font></b>
	<br><b><font size="+4"><font color="#FF6600"></font><font color="#FFCC33"><u>EMR</u></font><font color="#000000">GE</font><font color="#CCCCCC">SORT</font></font></b>
	<br><b><font size="+4"><font color="#FF6600"></font><u><font color="#FFCC33">EMR</font></u><font color="#000000"><u>G</u></font><font color="#999999">E</font><font color="#CCCCCC">SORT</font></font></b>
	<br><b><font size="+4"><font color="#FF6600"></font><u><font color="#FFCC33">EMR</font></u><font color="#000000"></font><u><font color="#FF6600">G</font></u><font color="#000000"><u>E</u></font><font color="#CCCCCC">SORT</font></font></b>
	<br><font color="#CCCCCC">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font size="+4"><font color="#CCCCCC"></font><font color="#3366FF">G | E</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#FF6600"><u>EMR</u><u>EG</u></font><font color="#000000"></font><font color="#CCCCCC">SORT</font></font></b>
	<br><font color="#CCCCCC">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font><b><font size="+4"><font color="#CCCCCC"></font><font color="#3366FF">EMR | GE</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#FF6600"><u>EEGMR</u></font><font color="#000000"></font><font color="#CCCCCC">SORT</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#FF6600"></font><u><font color="#FFCC33">EEGMR</font></u><font color="#000000">SORT</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#FF6600"></font><u><font color="#FFCC33">EEGMR</font></u><font color="#000000">SO</font><font color="#999999">RT</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#FF6600"></font><u><font color="#FFCC33">EEGMR</font></u><font color="#000000"><u>S</u></font><font color="#999999">O</font><font color="#000000"></font><font color="#CCCCCC">RT</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#FF6600"></font><u><font color="#FFCC33">EEGMR</font></u><font color="#000000"></font><u><font color="#FF6600">S</font></u><font color="#000000"><u>O</u></font><font color="#CCCCCC">RT</font></font></b>
	<br><font color="#CCCCCC">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font size="+4"><font color="#CCCCCC"></font><font color="#3366FF">S | O</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#FF6600"></font><u><font color="#FFCC33">EEGMR</font></u><font color="#FF6600"><u>OS</u></font><font color="#000000">RT</font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#FF6600"></font><u><font color="#FFCC33">EEGMR</font></u><font color="#FF6600"></font><u><font color="#FFCC33">OS</font></u><font color="#000000"><u>R</u></font><font color="#999999">T</font></font></b>
	<br><b><font size="+4"><font color="#FF6600"></font><u><font color="#FFCC33">EEGMR</font></u><font color="#FF6600"></font><u><font color="#FFCC33">OS</font></u><font color="#000000"></font><u><font color="#FF6600">R</font></u><font color="#000000"><u>T</u></font></font></b>
	<br><font color="#CCCCCC">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font size="+4"><font color="#CCCCCC"></font><font color="#3366FF">R | T</font></font></b>
	<br><b><font size="+4"><font color="#FF6600"></font><u><font color="#FFCC33">EEGMR</font></u><font color="#FF6600"><u>OS</u></font><font color="#000000"></font><u><font color="#FF6600">RT</font></u></font></b>
	<br><font color="#CCCCCC">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font size="+4"><font color="#CCCCCC"></font><font color="#3366FF">OS | TR</font></font></b>
	<br><b><font size="+4"><font color="#CCCCCC"></font><u><font color="#FF6600">EEGMR</font></u><font color="#FF6600"><u>ORST</u></font><font color="#CCCCCC"></font></font></b>
	<br><font color="#CCCCCC">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font size="+4"><font color="#CCCCCC"></font><font color="#3366FF">EEGMR | TSRO</font><font color="#CCCCCC"></font></font></b>
	<br><b><font size="+4"><font color="#3366FF"></font><font color="#CCCCCC"></font><u><font color="#FF6600">EEGMORRST</font></u><font color="#FF6600"></font><font color="#CCCCCC"></font></font></b>
</pre>
