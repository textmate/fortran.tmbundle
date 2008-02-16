The `'fmt='` specifier in a `read` or `write` statement can give either the line number of a `format` statement, an actual format string, or a `*` for free format.

# Syntax

A format specifier is a parenthesized string of format descriptors.

<table class="pro_table">
	<tr>
		<th>Descriptor</th>
		<th>Meaning</th>
	</tr>
	
	<tr>
		<td>I<em>n</em></td>
		<td><em>n</em> positions of integer data</td>
	</tr>
	
	<tr>
		<td>F<em>n</em>.d</td>
		<td><em>n</em> positions of real data (with d decimal places) &mdash; Decimal point form</td>
	</tr>
	
	<tr>
		<td>E<em>n</em>.d</td>
		<td><em>n</em> positions of real data (with d decimal places) &mdash; Exponent form</td>
	</tr>
	
	<tr>
		<td>L<em>n</em></td>
		<td><em>n</em> positions of logical data</td>
	</tr>
	
	<tr>
		<td>A[<em>n</em>]</td>
		<td>[<em>n</em> positions of] character data</td>
	</tr>
	
	<tr>
		<td><em>n</em>X</td>
		<td>skip <em>n</em> horizontal positions (X spaces)</td>
	</tr>

	<tr>
		<td>\</td>
		<td>skip line</td>
	</tr>

	<tr>
		<td>T<em>c</em></td>
		<td>tab to column number <em>c</em></td>
	</tr>

</table>

Descriptors, or groups of descriptors, can be repeated by prefixing, or parenthesizing and prefixing, with the number of repeats. For example `I4` can be repeated as `2I4` and `I4,1X` as `2(I4,1X)`.

Plain text strings can be inserted in the format string using double quotes (or two single quotes).

When the variable cannot be printed entirely given the format specified, it is displayed as placeholders (`'*'` usually)

# Examples

NB: &#x2423; is a space

	write(*,'(i6,i2)') 3, 2

&#x2423;&#x2423;&#x2423;&#x2423;&#x2423;3&#x2423;2

	write(*,'(f10.4,e15.7)') 12.7864, 234.4591

&#x2423;&#x2423;&#x2423;12.7864&#x2423;&#x2423;0.2344591E+03


	write(*,'(2x,"record Nº",i2," is ",A6)') 10, 'Philip'

&#x2423;&#x2423;record&#x2423;Nº10&#x2423;is&#x2423;Philip


	write(*,'(2X,2(I4,1X),''name '',A4,F13.5,1X,E13.5)') 77778, 3, 'ABCDEFGHI', 14.45, 15.5666666
	
&#x2423;&#x2423;\*\*\*\*&#x2423;&#x2423;&#x2423;&#x2423;3&#x2423;name&#x2423;ABCD&#x2423;&#x2423;&#x2423;&#x2423;&#x2423;14.45000&#x2423;&#x2423;&#x2423;0.15567E+02


