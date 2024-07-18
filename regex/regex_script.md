# Encontrar textos entre chars

```regex
- Exrair textos entre chars [] ou {}:
- regex: '(?<=\[|\{)(.*?)(?=\]|\})'

'[texto1]_[texto2]_{texto3}_[texto4]_[texto5]_[texto6]'

```

- Encontrar textos

 ```regex
- Extrair textos que começam e finalizam com: <BEGIN> e <END>
regex: '<BEGIN>(.*?)<END>'

- Encontrar Bloco de texto que contenham quebra de linha 
regex: '(?<=<BEGIN>)([\S\s]*?)(?=<END>)'   

<BEGIN> 
 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
<END>
 ```

- Split de textos entre <NL>

 ```regex
- Exrair textos entre <NL>  
- regex: '(?<=<NL>|^)(.+?)(?=<NL>|$)'

Lorem<NL>ipsum<NL>dolor<NL>sit<NL>amet,<NL>consectetur<NL>adipiscing<NL>elit,<NL>sed<NL>do<NL>eiusmod<NL>tempor<NL>incididunt<NL>ut<NL>labore<NL>et<NL>dolore<NL>magna<NL>aliqua.<NL>Ut<NL>enim<NL>ad<NL>minim<NL>veniam,<NL>quis<NL>nostrud<NL>exercitation<NL>ullamco<NL>laboris<NL>nisi<NL>ut<NL>aliquip<NL>ex<NL>ea<NL>commodo<NL>consequat.<NL>Duis<NL>aute<NL>irure<NL>dolor<NL>in<NL>reprehenderit<NL>in<NL>voluptate<NL>velit<NL>esse<NL>cillum<NL>dolore<NL>eu<NL>fugiat<NL>nulla<NL>pariatur.<NL>Excepteur<NL>sint<NL>occaecat<NL>cupidatat<NL>non<NL>proident,<NL>sunt<NL>in<NL>culpa<NL>qui<NL>officia<NL>deserunt<NL>mollit<NL>anim<NL>id<NL>est<NL>laborum.   

 ```
