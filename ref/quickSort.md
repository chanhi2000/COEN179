# quickSort

## PSEUDOCODE
```cpp
void quicksort(char a[], int left, int right) {
    int i,j;  char v;
    if (right > left)	{
		v = a[right]; i = left-1; j = right;
		for (;;) {
	    	while (a[++i] < v);
	    	while (a[--j] > v);
	    	if (i >= j) break;
	    	swap(a, i, j);
		}
		swap(a, i, right);
		quicksort(a, left, i-1);
		quicksort(a, i+1, right);
    }
}
```

## EXAMPLE
<pre>
    <br><b><font size="+4">ALGORITHMI<font color="#993300"></font><font color="#993399">C</font></font></b>

    <br><b><font size="+4"><font color="#3333FF">A</font><font color="#FF9900">L</font>GORITHMI<font color="#993399">C</font></font></b>

    <br><b><font size="+4"><font color="#000000">A<u>C</u></font>GORITHMIL</font></b>

    <br><b><font size="+4"><font color="#993399">A</font><font color="#000000"></font><font color="#CCCCCC"><u>C</u>GORITHMIL</font></font></b>

    <br><b><u><font size="+4"><font color="#000000">A</font><font color="#CCCCCC">C</font></font></u><font color="#CCCCCC"><font size="+4">GORITHMIL</font></font></b>

    <br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">GORITHMI</font><font color="#663300"></font><font color="#993399">L</font></font></b>

    <br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G</font><font color="#FF9900">O</font><font color="#000000">RITHM</font><font color="#3333FF">I</font><font color="#993399">L</font></font></b>
    <br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G&nbsp;IRITHMO</font><font color="#993399">L</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G&nbsp;I</font><font color="#FFCC33"></font><font color="#FF9900">R</font><font color="#000000">IT</font><font color="#3333FF">H</font><font color="#000000">MO</font><font color="#993399">L</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G&nbsp;I</font><font color="#FFCC33"></font><font color="#000000">H</font><font color="#3333FF">I</font><font color="#FF9900">T</font><font color="#000000">RMO</font><font color="#993399">L</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G&nbsp;I</font><font color="#FFCC33"></font><font color="#000000">HI<u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G&nbsp;I</font><font color="#FFCC33"></font><font color="#000000">H</font><font color="#993399">I</font><font color="#000000"></font><font color="#CCCCCC"><u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G&nbsp;</font><font color="#FF9900">I</font><font color="#3333FF">H</font><font color="#993399">I</font><font color="#CCCCCC"><u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G&nbsp;HI</font><font color="#3333FF"></font><font color="#993399">I</font><font color="#FFCCCC"></font><font color="#CCCCCC"><u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G&nbsp;</font><font color="#3333FF">H</font><font color="#FF9900">I</font><font color="#993399">I</font><font color="#FFCCCC"></font><font color="#CCCCCC"><u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G&nbsp;H<u>I</u>I</font><font color="#FFCCCC"></font><font color="#CCCCCC"><u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G</font><font color="#993399">H</font><font color="#CCCCCC"><u>I</u>I<u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#3333FF">G</font><font color="#000000"></font><font color="#FF9900">H</font><font color="#CCCCCC"><u>I</u>I<u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><font color="#000000">G<u>H</u></font><font color="#CCCCCC"><u>I</u>I<u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>C</u></font><u><font color="#000000">G</font><font color="#CCCCCC">H</font></u><font color="#000000"></font><font color="#CCCCCC"><u>I</u>I<u>L</u>RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u></font><u><font color="#000000">I</font><font color="#CCCCCC">L</font></u><font color="#CCCCCC">RMOT</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u><u>IL</u></font><font color="#000000">RMO</font><font color="#993399">T</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u><u>IL</u></font><font color="#000000">RM</font><font color="#3333FF">O</font><font color="#FF9900">T</font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u><u>IL</u></font><font color="#000000">RMO<u>T</u></font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u><u>IL</u></font><font color="#FF9900">R</font><font color="#3333FF">M</font><font color="#FFCCCC">O</font><u><font color="#CCCCCC">T</font></u></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u><u>IL</u></font><font color="#000000">MR</font><font color="#FFCCCC">O</font><u><font color="#CCCCCC">T</font></u></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u><u>IL</u></font><font color="#3333FF">M</font><font color="#FF6600">R</font><font color="#FFCCCC">O</font><u><font color="#CCCCCC">T</font></u></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u><u>IL</u></font><font color="#000000">M<u>O</u>R</font><u><font color="#CCCCCC">T</font></u></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u><u>IL</u></font><font color="#000000"><u>M</u></font><font color="#CCCCCC"><u>O</u>R<u>T</u></font></font></b>

	<br><b><font size="+4"><font color="#CCCCCC"><u>A</u><u>CG&nbsp;</u><u>HI</u><u>ILM</u><u>O</u></font><u><font color="#000000">R</font><font color="#CCCCCC">T</font></u></font></b>
</pre>

