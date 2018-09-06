---
title: is, isw rutinleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apilocation:
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- isw
- is
dev_langs:
- C++
helpviewer_keywords:
- is routines
- isw routines
ms.assetid: 1e171a57-2cde-41f6-a75f-a080fa3c12e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98f7edcf115a6fadc741c7f1bcde8f240c93abcc
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895129"
---
# <a name="is-isw-routines"></a>is, isw Rutinleri

|||
|-|-|
|[isalnum, iswalnum, _isalnum_l, _iswalnum_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md)|[isgraph, iswgraph, _isgraph_l, _iswgraph_l](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md)|
|[isalpha, iswalpha, _isalpha_l, _iswalpha_l](../c-runtime-library/reference/isalpha-iswalpha-isalpha-l-iswalpha-l.md)|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|
|[isascii, __isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)|[islower, iswlower, _islower_l, _iswlower_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md)|
|[isblank, iswblank, _isblank_l, _iswblank_l](../c-runtime-library/reference/isblank-iswblank-isblank-l-iswblank-l.md)|[isprint, iswprint, _isprint_l, _iswprint_l](../c-runtime-library/reference/isprint-iswprint-isprint-l-iswprint-l.md)|
|[iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md)|[ispunct, iswpunct, _ispunct_l, _iswpunct_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md)|
|[iscsym, iscsymf, __iscsym, \__iswcsym, \__iscsymf, \__iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l](../c-runtime-library/reference/iscsym-functions.md)|[isspace, iswspace, _isspace_l, _iswspace_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md)|
|[_isctype, iswctype, _isctype_l, _iswctype_l](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|[isupper, _isupper_l, iswupper, _iswupper_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md)|
|[isdigit, iswdigit, _isdigit_l, _iswdigit_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md)|[isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md)|

## <a name="remarks"></a>Açıklamalar

Bu yordamlar, belirtilen koşullar için karakterleri test edin.

**Olduğu** yordamları-1 herhangi bir tamsayı bağımsız değişkeni için anlamlı sonuçlar oluşturur (`EOF`) için **UCHAR_MAX** (0xFF) dahil. Beklenen değişken türü `int`.

> [!CAUTION]
> İçin **olduğu** türünde bir bağımsız değişken geçirme yordamlarını `char` öngörülemeyen sonuçlara neden olabilir. Türü bir SBCS veya MBCS tek baytlık karakteri `char` 0x7F değerinden büyük bir değere sahip. Varsa bir `char` olan geçti, derleyici değeri işaretli dönüştürebiliriz `int` ya da işaretli bir **uzun**. Bu değer, beklenmeyen sonuçlarla derleyici tarafından işareti genişletilmiş olabilir.

**İsw** yordamları - 1 arasında herhangi bir tamsayı değeri için anlamlı sonuçlar oluşturur (**WEOF**) ile 0xFFFF arasında kapsamlı. **Wint_t** veri türü WCHAR içinde tanımlanmıştır. H olarak bir **işaretsiz**; herhangi bir geniş karakter veya geniş karakter son dosya tutun (**WEOF**) değeri.

Çıkış değeri ayarından etkilenir `LC_CTYPE` yerel ayarının kategori ayarına; bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümleriyle **_l** sonekine bunların yerel ayar parametresini kullanmalarıdır Bunun yerine iletilmiş.

İçin "C" yerel ayarında test koşulları **olduğu** yordamları aşağıdaki gibidir:

`isalnum`  
Alfasayısal (A - Z, a - z veya 0 - 9).

`isalpha`  
Alfabetik (A - Z veya a - z).

`__isascii`  
ASCII karakter (0x00 - 0x7F).

`isblank`  
Yatay sekme veya boşluk karakteri (0x09 veya 0x20).

`iscntrl`  
Denetim karakteri (0x00-0x1F veya 0x7F).

`__iscsym`  
Harf, alt çizgi veya rakam.

`__iscsymf`  
Harf veya alt çizgi.

`isdigit`  
Ondalık basamak (0 - 9).

`isgraph`  
Boşluk () dışında yazdırılabilir karakter.

`islower`  
Küçük harf (a - z).

`isprint`  
Boşluk da içinde yazdırılabilir karakter (0x20 - 0x7E).

`ispunct`  
Noktalama karakteri.

`isspace`  
Boşluk karakteri (0x09-0x0D veya 0x20).

`isupper`  
Büyük harf (A - Z).

`isxdigit`  
Onaltılık basamak (A - F, a - f veya 0 - 9).

İçin **isw** rutinleri için belirtilen koşula ilişkin test sonucu yerel ayardan bağımsızdır. Sınama koşulları **isw** işlevleri aşağıdaki gibidir:

`iswalnum`  
`iswalpha` veya `iswdigit`.

`iswalpha`  
Bir uygulama tanımlı kümesinin öğelerinin hiçbiri biri olan geniş karakter `iswcntrl`, `iswdigit`, `iswpunct`, veya `iswspace` sıfır değil. `iswalpha` geniş karakterler için sıfır olmayan döndüğü `iswupper` veya `iswlower` sıfır değil.

`iswascii`  
ASCII karakterinin geniş karakter gösterimi (0x0000 - 0x007F).

`iswblank`  
Geniş karakter standart boşluk karakterine karşılık gelen veya kendisi için geniş karakterlerin uygulama tanımlı bir dizi biri `iswalnum` false'tur. Standart boş karakterler: boşluk (L' ') ve yatay sekmedir (L '\t').

`iswcntrl`  
Geniş karakteri denetleyin.

`__iswcsym`  
Bir geniş karakter `isalnum` doğru ya da '_' karakteri.

`__iswcsymf`  
Bir geniş karakter `iswalpha` doğru ya da '_' karakteri.

`iswctype`  
Karakteri tarafından belirtilen özelliğe sahip `desc` bağımsız değişken. Her bir geçerli değerini `desc` bağımsız değişkeni `iswctype`, aşağıdaki tabloda gösterildiği gibi bir eşdeğer bir geniş karakter sınıflandırma rutini olan:

### <a name="equivalence-of-iswctypec-desc-to-other-isw-testing-routines"></a>İswctype (c, desc) için diğer isw sınama yordamları denkliği

|Değeri *desc* bağımsız değişken|iswctype ( *c, desc* ) eşdeğer|
|------------------------------|----------------------------------------|
|**_ALPHA**|**iswalpha (** `c` **)**|
|**_ALPHA** &AMP;#124; **_DIGIT**|**iswalnum (** `c` **)**|
|**_BLANK**|**iswblank (** `c` **)**|
|**_DENETİM**|**iswcntrl (** `c` **)**|
|**_DIGIT**|**iswdigit (** `c` **)**|
|**_ALPHA** &AMP;#124; **_DIGIT** &AMP;#124; **_PUNCT**|**iswgraph (** `c` **)**|
|**_LOWER**|**iswlower (** `c` **)**|
|**_ALPHA** &AMP;#124; **_BLANK** &AMP;#124; **_DIGIT** &AMP;#124; **_PUNCT**|**iswprint (** `c` **)**|
|**_PUNCT**|**iswpunct (** `c` **)**|
|**_BLANK**|**iswblank (** `c` **)**|
|**_SPACE**|**iswspace (** `c` **)**|
|**_UPPER**|**iswupper (** `c` **)**|
|**_HEX**|**iswxdigit (** `c` **)**|

`iswdigit`  
Bir ondalık basamak karakterine karşılık gelen geniş karakter.

`iswgraph`  
Boşluk geniş karakteri dışında yazdırılabilir geniş karakteri (L' ').

`iswlower`  
Küçük Harf ya da bir uygulama tanımlı kümesinin geniş karakterler öğelerinin hiçbiri `iswcntrl`, `iswdigit`, `iswpunct`, veya `iswspace` sıfır değil. `iswlower` küçük harfe karşılık gelen geniş karakterler için sıfır döndürür.

`iswprint`  
Boşluk geniş karakteri dahil yazdırılabilir geniş karakteri (L' ').

`iswpunct`  
Ne boşluk geniş karakteri yazdırılabilir geniş karakteri (L' ') ne de geniş karakter `iswalnum` sıfır değil.

`iswspace`  
Geniş karakter standart boşluk karakterine karşılık gelen veya uygulama tanımlı olan geniş karakterler kümesi biri `iswalnum` false'tur. Standart beyaz boşluk karakterleri: boşluk (L' '), form besleme (L '\f'), satır başı karakteri (L '\n'), satır başı (L '\r'), yatay sekme (L '\t') ve dikey sekmedir (L '\v').

`iswupper`  
Geniş karakter, büyük harf ya da hiçbiri geniş karakterlerin uygulama tanımlı bir dizi biri `iswcntrl`, `iswdigit`, `iswpunct`, veya `iswspace` sıfır değil. `iswupper` büyük harf karakterlere karşılık gelen geniş karakterler için sıfır döndürür.

`iswxdigit`  
Bir onaltılık basamak karakterine karşılık gelen geniş karakter.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Karakter Sınıflaması](../c-runtime-library/character-classification.md)   
[Yerel ayar](../c-runtime-library/locale.md)   
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
[Çok baytlı karakter sıralarının yorumu](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
[to İşlevleri](../c-runtime-library/to-functions.md)