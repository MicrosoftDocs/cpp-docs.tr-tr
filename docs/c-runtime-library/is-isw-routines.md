---
title: is, isw Rutinleri
ms.date: 11/04/2016
api_location:
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- isw
- is
helpviewer_keywords:
- is routines
- isw routines
ms.assetid: 1e171a57-2cde-41f6-a75f-a080fa3c12e5
ms.openlocfilehash: 4dad7ff74112da7fc7d0d01714b0cf0dd4e4495c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940174"
---
# <a name="is-isw-routines"></a>is, isw Rutinleri

|||
|-|-|
|[isalnum, iswalnum, _isalnum_l, _iswalnum_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md)|[isgraph, iswgraph, _isgraph_l, _iswgraph_l](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md)|
|[isalpha, iswalpha, _isalpha_l, _iswalpha_l](../c-runtime-library/reference/isalpha-iswalpha-isalpha-l-iswalpha-l.md)|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|
|[isascii, __isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)|[islower, iswlower, _islower_l, _iswlower_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md)|
|[isblank, iswblank, _isblank_l, _iswblank_l](../c-runtime-library/reference/isblank-iswblank-isblank-l-iswblank-l.md)|[isprint, iswprint, _isprint_l, _iswprint_l](../c-runtime-library/reference/isprint-iswprint-isprint-l-iswprint-l.md)|
|[iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md)|[ispunct, iswpunct, _ispunct_l, _iswpunct_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md)|
|[SCC, SCC, SCC, __scc \_,, _iswcsym, \__scc symf, \__iswcsymf, _scc sym_l, _iswcsym_l, _scc symf_l, _iswcsymf_l](../c-runtime-library/reference/iscsym-functions.md)|[isspace, iswspace, _isspace_l, _iswspace_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md)|
|[_isctype, iswctype, _isctype_l, _iswctype_l](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|[isupper, _isupper_l, iswupper, _iswupper_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md)|
|[isdigit, iswdigit, _isdigit_l, _iswdigit_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md)|[isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md)|

## <a name="remarks"></a>Açıklamalar

Bu yordamlar belirtilen koşullar için karakterleri test etme.

Bu **yordamlar,** -1 (`EOF`) ile **uchar_max** (0xFF) (dahil) arasında herhangi bir tamsayı bağımsız değişkeni için anlamlı sonuçlar üretir. Beklenen bağımsız değişken türü `int`.

> [!CAUTION]
> **In** yordamları için, türünde `char` bir bağımsız değişken geçirmek öngörülemeyen sonuçlara neden olabilir. 0x7F 'den büyük bir değere `char` sahip olan bir sbcs veya mbcs tek baytlı karakteri negatif. Bir `char` geçirildiğinde, derleyici değeri işaretli `int` veya imzalı bir **Long**değerine dönüştürebilir. Bu değer, derleyici tarafından, beklenmeyen sonuçlarla işaret eden genişletilmiş olabilir.

**İsw** yordamları,-1 ' den (**weof**), 0xFFFF, dahil olmak üzere herhangi bir tamsayı değeri için anlamlı sonuçlar üretir. **Wint_t** VERI türü wchar içinde tanımlanmıştır. **İşaretsiz kısa**olarak H; herhangi bir geniş karakter veya geniş karakter dosya sonu (**weof**) değeri tutabilir.

Çıkış değeri yerel ayarın `LC_CTYPE` kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) . **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

"C" yerel ayarında, **Bu yordamlar için** test koşulları aşağıdaki gibidir:

`isalnum`<br/>
Alfasayısal (A-Z, A-z veya 0-9).

`isalpha`<br/>
Alfabetik (A-Z veya A-z).

`__isascii`<br/>
ASCII karakteri (0x00-0x7F).

`isblank`<br/>
Yatay sekme veya boşluk karakteri (0x09 veya 0x20).

`iscntrl`<br/>
Denetim karakteri (0x00-0x1F veya 0x7F).

`__iscsym`<br/>
Harf, alt çizgi veya rakam.

`__iscsymf`<br/>
Harf veya alt çizgi.

`isdigit`<br/>
Ondalık basamak (0-9).

`isgraph`<br/>
Boşluk () dışında yazdırılabilir karakter.

`islower`<br/>
Küçük harf (a-z).

`isprint`<br/>
Boşluk (0x20-0x7E) dahil yazdırılabilir karakter.

`ispunct`<br/>
Noktalama karakteri.

`isspace`<br/>
Boşluk karakteri (0x09-0x0D veya 0x20).

`isupper`<br/>
Büyük harf (A-Z).

`isxdigit`<br/>
Onaltılık basamak (A-F, A-f veya 0-9).

**İsw** yordamları için, belirtilen koşulun test sonucu yerel ayardan bağımsızdır. **İsw** işlevleri için test koşulları aşağıdaki gibidir:

`iswalnum`<br/>
`iswalpha`veya `iswdigit`.

`iswalpha`<br/>
`iswcntrl` `iswdigit`,,, Veya`iswspace` hiçbiri sıfır dışında olmayan, uygulama tanımlı bir küme olan herhangi bir geniş karakter. `iswpunct` `iswalpha`yalnızca `iswupper` veya`iswlower` sıfır dışında bir geniş karakter için sıfır dışında bir değer döndürür.

`iswascii`<br/>
ASCII karakterinin geniş karakterli temsili (0x0000-0x007F).

`iswblank`<br/>
Standart boşluk karakterine karşılık gelen veya yanlış olan `iswalnum` uygulama tanımlı geniş karakter kümesinden biri olan geniş karakter. Standart boş karakterler boşluk (L ' ') ve yatay sekme (L ' \t ').

`iswcntrl`<br/>
Denetim geniş karakter.

`__iswcsym`<br/>
İçin geçerli olan `isalnum` herhangi bir geniş karakter veya ' _ ' karakteri.

`__iswcsymf`<br/>
İçin geçerli olan `iswalpha` herhangi bir geniş karakter veya ' _ ' karakteri.

`iswctype`<br/>
Karakter, `desc` bağımsız değişken tarafından belirtilen özelliğe sahip. Bağımsız değişkeninin geçerli her bir değeri için,aşağıdakitablodagösterildiğigibieşdeğerbirgenişkaraktersınıflandırmayordamıvardır:`iswctype` `desc`

### <a name="equivalence-of-iswctypec-desc-to-other-isw-testing-routines"></a>İswctype (c, DESC) diğer isw test yordamlarına denklik

|*DESC* bağımsız değişkeninin değeri|ıwctype ( *c, DESC* ) eşdeğeri|
|------------------------------|----------------------------------------|
|**_ALFA**|**iswalpha (** `c` **)**|
|**_ALPHA** &#124; **_DIGIT**|**iswalnum (** `c` **)**|
|**_BLANK**|**ıwıblank (** `c` **)**|
|**_DENETIM**|**iswcnw (** `c` **)**|
|**_BASAMAK**|**iswdigit (** `c` **)**|
|**_ALPHA** &#124; **_DIGIT** &#124; **_PUNCT**|**iswgraf (** `c` **)**|
|**_DÜŞÜK**|**iswlower (** `c` **)**|
|**_ALPHA** &#124; **_BLANK** &#124; **_DIGIT** &#124; **_PUNCT**|**iswprint (** `c` **)**|
|**_PUNCT**|**iswpunct (** `c` **)**|
|**_BLANK**|**ıwıblank (** `c` **)**|
|**_BOŞLUK**|**iswspace (** `c` **)**|
|**_ÜST**|**iswupper (** `c` **)**|
|**_ONALTILI**|**iswxdigit (** `c` **)**|

`iswdigit`<br/>
Ondalık basamaklı bir karaktere karşılık gelen geniş karakter.

`iswgraph`<br/>
Boşluk geniş karakteri (L ' ') dışında yazdırılabilir geniş karakter.

`iswlower`<br/>
Küçük `iswcntrl`harf veya `iswdigit` ,,,veya`iswspace` olmayan, ,,yadasıfırdanfarklıbiruygulamatanımlıgenişkarakterkümesi.`iswpunct` `iswlower`yalnızca küçük harflere karşılık gelen geniş karakterler için sıfır dışında bir değer döndürür.

`iswprint`<br/>
Boşluk geniş karakteri (L ' ') içeren yazdırılabilir geniş karakter.

`iswpunct`<br/>
Boşluk geniş karakteri (L ' ') veya geniş karakter `iswalnum` olmayan, yazdırılabilir geniş karakter.

`iswspace`<br/>
Standart boşluk karakterine karşılık gelen veya yanlış olan `iswalnum` uygulama tanımlı geniş karakter kümesinden biri olan geniş karakter. Standart boşluk karakterleri şunlardır: boşluk (L ' '), form akışı (L ' \f '), yeni satır (L ' \n '), satır başı (l ' \r '), yatay sekme (L ' \t ') ve dikey sekme (L ' \v ').

`iswupper`<br/>
Büyük harf olan veya `iswcntrl`,, `iswpunct`, ya `iswspace` da sıfırdan farklı olmayan, `iswdigit`uygulama tanımlı geniş karakter kümesinden biri olan geniş karakter. `iswupper`yalnızca büyük harfli karakterlere karşılık gelen geniş karakterler için sıfır dışında bir değer döndürür.

`iswxdigit`<br/>
Onaltılık basamaklı bir karaktere karşılık gelen geniş karakter.

## <a name="example"></a>Örnek

```C
// crt_isfam.c
/* This program tests all characters between 0x0
* and 0x7F, then displays each character with abbreviations
* for the character-type codes that apply.
*/

#include <stdio.h>
#include <ctype.h>

int main( void )
{
   int ch;
   for( ch = 0; ch <= 0x7F; ch++ )
   {
      printf( "%.2x  ", ch );
      printf( " %c", isprint( ch )  ? ch   : ' ' );
      printf( "%4s", isalnum( ch )  ? "AN" : "" );
      printf( "%3s", isalpha( ch )  ? "A"  : "" );
      printf( "%3s", __isascii( ch )  ? "AS" : "" );
      printf( "%3s", iscntrl( ch )  ? "C"  : "" );
      printf( "%3s", __iscsym( ch )  ? "CS "  : "" );
      printf( "%3s", __iscsymf( ch )  ? "CSF"  : "" );
      printf( "%3s", isdigit( ch )  ? "D"  : "" );
      printf( "%3s", isgraph( ch )  ? "G"  : "" );
      printf( "%3s", islower( ch )  ? "L"  : "" );
      printf( "%3s", ispunct( ch )  ? "PU" : "" );
      printf( "%3s", isspace( ch )  ? "S"  : "" );
      printf( "%3s", isprint( ch )  ? "PR" : "" );
      printf( "%3s", isupper( ch )  ? "U"  : "" );
      printf( "%3s", isxdigit( ch ) ? "X"  : "" );
      printf( ".\n" );
   }
}
```

## <a name="output"></a>Çıkış

```Output
00            AS  C                              .
01            AS  C                              .
02            AS  C                              .
03            AS  C                              .
04            AS  C                              .
05            AS  C                              .
06            AS  C                              .
07            AS  C                              .
08            AS  C                              .
09            AS  C                    S         .
0a            AS  C                    S         .
0b            AS  C                    S         .
0c            AS  C                    S         .
0d            AS  C                    S         .
0e            AS  C                              .
0f            AS  C                              .
10            AS  C                              .
11            AS  C                              .
12            AS  C                              .
13            AS  C                              .
14            AS  C                              .
15            AS  C                              .
16            AS  C                              .
17            AS  C                              .
18            AS  C                              .
19            AS  C                              .
1a            AS  C                              .
1b            AS  C                              .
1c            AS  C                              .
1d            AS  C                              .
1e            AS  C                              .
1f            AS  C                              .
20            AS                       S PR      .
21   !        AS              G    PU    PR      .
22   "        AS              G    PU    PR      .
23   #        AS              G    PU    PR      .
24   $        AS              G    PU    PR      .
25   %        AS              G    PU    PR      .
26   &        AS              G    PU    PR      .
27   '        AS              G    PU    PR      .
28   (        AS              G    PU    PR      .
29   )        AS              G    PU    PR      .
2a   *        AS              G    PU    PR      .
2b   +        AS              G    PU    PR      .
2c   ,        AS              G    PU    PR      .
2d   -        AS              G    PU    PR      .
2e   .        AS              G    PU    PR      .
2f   /        AS              G    PU    PR      .
30   0  AN    AS   CS      D  G          PR     X.
31   1  AN    AS   CS      D  G          PR     X.
32   2  AN    AS   CS      D  G          PR     X.
33   3  AN    AS   CS      D  G          PR     X.
34   4  AN    AS   CS      D  G          PR     X.
35   5  AN    AS   CS      D  G          PR     X.
36   6  AN    AS   CS      D  G          PR     X.
37   7  AN    AS   CS      D  G          PR     X.
38   8  AN    AS   CS      D  G          PR     X.
39   9  AN    AS   CS      D  G          PR     X.
3a   :        AS              G    PU    PR      .
3b   ;        AS              G    PU    PR      .
3c   <        AS              G    PU    PR      .
3d   =        AS              G    PU    PR      .
3e   >        AS              G    PU    PR      .
3f   ?        AS              G    PU    PR      .
40   @        AS              G    PU    PR      .
41   A  AN  A AS   CS CSF     G          PR  U  X.
42   B  AN  A AS   CS CSF     G          PR  U  X.
43   C  AN  A AS   CS CSF     G          PR  U  X.
44   D  AN  A AS   CS CSF     G          PR  U  X.
45   E  AN  A AS   CS CSF     G          PR  U  X.
46   F  AN  A AS   CS CSF     G          PR  U  X.
47   G  AN  A AS   CS CSF     G          PR  U   .
48   H  AN  A AS   CS CSF     G          PR  U   .
49   I  AN  A AS   CS CSF     G          PR  U   .
4a   J  AN  A AS   CS CSF     G          PR  U   .
4b   K  AN  A AS   CS CSF     G          PR  U   .
4c   L  AN  A AS   CS CSF     G          PR  U   .
4d   M  AN  A AS   CS CSF     G          PR  U   .
4e   N  AN  A AS   CS CSF     G          PR  U   .
4f   O  AN  A AS   CS CSF     G          PR  U   .
50   P  AN  A AS   CS CSF     G          PR  U   .
51   Q  AN  A AS   CS CSF     G          PR  U   .
52   R  AN  A AS   CS CSF     G          PR  U   .
53   S  AN  A AS   CS CSF     G          PR  U   .
54   T  AN  A AS   CS CSF     G          PR  U   .
55   U  AN  A AS   CS CSF     G          PR  U   .
56   V  AN  A AS   CS CSF     G          PR  U   .
57   W  AN  A AS   CS CSF     G          PR  U   .
58   X  AN  A AS   CS CSF     G          PR  U   .
59   Y  AN  A AS   CS CSF     G          PR  U   .
5a   Z  AN  A AS   CS CSF     G          PR  U   .
5b   [        AS              G    PU    PR      .
5c   \        AS              G    PU    PR      .
5d   ]        AS              G    PU    PR      .
5e   ^        AS              G    PU    PR      .
5f   _        AS   CS CSF     G    PU    PR      .
60   `        AS              G    PU    PR      .
61   a  AN  A AS   CS CSF     G  L       PR     X.
62   b  AN  A AS   CS CSF     G  L       PR     X.
63   c  AN  A AS   CS CSF     G  L       PR     X.
64   d  AN  A AS   CS CSF     G  L       PR     X.
65   e  AN  A AS   CS CSF     G  L       PR     X.
66   f  AN  A AS   CS CSF     G  L       PR     X.
67   g  AN  A AS   CS CSF     G  L       PR      .
68   h  AN  A AS   CS CSF     G  L       PR      .
69   i  AN  A AS   CS CSF     G  L       PR      .
6a   j  AN  A AS   CS CSF     G  L       PR      .
6b   k  AN  A AS   CS CSF     G  L       PR      .
6c   l  AN  A AS   CS CSF     G  L       PR      .
6d   m  AN  A AS   CS CSF     G  L       PR      .
6e   n  AN  A AS   CS CSF     G  L       PR      .
6f   o  AN  A AS   CS CSF     G  L       PR      .
70   p  AN  A AS   CS CSF     G  L       PR      .
71   q  AN  A AS   CS CSF     G  L       PR      .
72   r  AN  A AS   CS CSF     G  L       PR      .
73   s  AN  A AS   CS CSF     G  L       PR      .
74   t  AN  A AS   CS CSF     G  L       PR      .
75   u  AN  A AS   CS CSF     G  L       PR      .
76   v  AN  A AS   CS CSF     G  L       PR      .
77   w  AN  A AS   CS CSF     G  L       PR      .
78   x  AN  A AS   CS CSF     G  L       PR      .
79   y  AN  A AS   CS CSF     G  L       PR      .
7a   z  AN  A AS   CS CSF     G  L       PR      .
7b   {        AS              G    PU    PR      .
7c   |        AS              G    PU    PR      .
7d   }        AS              G    PU    PR      .
7e   ~        AS              G    PU    PR      .
7f            AS  C                              .
```

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../c-runtime-library/character-classification.md)<br/>
[locale](../c-runtime-library/locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[to İşlevleri](../c-runtime-library/to-functions.md)
