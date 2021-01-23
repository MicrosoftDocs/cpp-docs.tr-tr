---
title: Ön işlemci dil bilgisi özeti (C/C++)
description: Microsoft C/C++ derleyicisi (MSVC) Önişlemci dilbilgisi sözdizimini tanımlar ve tanımlar.
ms.date: 01/22/2021
helpviewer_keywords:
- grammar
- preprocessor, grammar
ms.openlocfilehash: dbe46a67337bf55cb98100878dedb8c92120472b
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713642"
---
# <a name="preprocessor-grammar-summary-cc"></a>Ön işlemci dil bilgisi özeti (C/C++)

Bu makalede, C ve C++ Önişlemci 'nin biçimsel dilbilgisi açıklanır. Ön işleme yönergelerinin ve işleçlerinin sözdizimini içerir. Daha fazla bilgi için bkz. [Önişlemci](../preprocessor/preprocessor.md) ve [pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md).

## <a name="definitions-for-the-grammar-summary"></a><a name="definitions"></a> Dilbilgisi özeti tanımları

Terminal, bir sözdizimi tanımındaki uç noktalardır. Başka bir çözüm mümkün değildir. Terminal, ayrılmış sözcükler ve Kullanıcı tanımlı tanımlayıcılar kümesini içerir.

Terminal dışı, söz dizimi içindeki yer tutuculardır. Çoğu, bu söz dizimi özetinde başka bir yerde tanımlanır. Tanımlar özyinelemeli olabilir. Aşağıdaki terminallerde, *C++ dil başvurusunun* [sözlü kuralları](../cpp/lexical-conventions.md) bölümünde tanımlanmıştır:

*`constant`*, *`constant-expression`*, *`identifier`*, *`keyword`*, *`operator`*, *`punctuator`*

İsteğe bağlı bir bileşen, alt indisli <sub>opt</sub>tarafından gösterilir. Örneğin, aşağıdaki sözdizimi, küme ayraçları içine alınmış bir isteğe bağlı ifadeyi gösterir:

**`{`***`expression`* <sub>opt</sub>**`}`**

## <a name="document-conventions"></a><a name="conventions"></a> Belge kuralları

Kurallar, sözdiziminin farklı bileşenleri için farklı yazı tipi öznitelikleri kullanır. Simgeler ve yazı tipleri aşağıdaki gibidir:

| Öznitelik | Açıklama |
|---------------|-----------------|
| *`nonterminal`* | İtalik tür terminal olmayanları gösterir. |
| **`#include`** | Kalın türdeki terminaller, gösterildiği gibi girilmesi gereken sabit ayrılmış sözcükler ve simgelerdir. Bu bağlamdaki karakterler, her zaman büyük/küçük harfe duyarlıdır. |
| <sub>opt</sub> | Terminal olmayan ve <sub>opt</sub> tarafından izlenen, her zaman isteğe bağlıdır.|
| varsayılan yazı tipi | Bu yazı tipinde açıklanan veya listelenen kümedeki karakterler, deyimlerde terminaller olarak kullanılabilir. |

**`:`** Terminalden sonraki bir iki nokta () tanımı tanıtılmıştır. Alternatif tanımlar, ayrı satırlarda listelenmiştir.

Kod sözdizimi blokları ' nda, varsayılan yazı tipindeki bu simgelerin özel bir anlamı vardır:

| Sembol | Açıklama |
|---|---|
| \[ ] | Köşeli ayraçlar isteğe bağlı bir öğe. |
| { \| } | Küme ayraçları dikey çubuklarla ayrılmış alternatif öğeleri. |
| ... | Önceki öğe deseninin tekrarlanabilir olduğunu gösterir. |

Kod sözdizimi blokları, virgüller ( `,` ), noktalar ( `.` ), noktalı virgül (), `;` iki nokta üst üste (), `:` parantez ( `( )` ), çift tırnak ( `"` ) ve tek tırnak ( `'` ) değişmez değerleri.

## <a name="preprocessor-grammar"></a><a name="grammar"></a> Önişlemci dilbilgisi

*`control-line`*:\
&emsp;**`#define`***`identifier`* *`token-string`* <sub>opt</sub>\
&emsp;**`#define`***`identifier`* **`(`** *`identifier`* <sub>opt</sub> **`,`** ... **`,`** *`identifier`* <sub></sub> **`)`** opt *`token-string`* <sub>opt</sub>\
&emsp;**`#include`** **`"`**_`path-spec`_**`"`**\
&emsp;**`#include`** **`<`**_`path-spec`_**`>`**\
&emsp;**`#line`***`digit-sequence`* **`"`**_`filename`_**`"`** <sub>opt</sub>\
&emsp;**`#undef`** *`identifier`*\
&emsp;**`#error`** *`token-string`*\
&emsp;**`#pragma`** *`token-string`*

*`constant-expression`*:\
&emsp;**`defined(`** *`identifier`* **`)`**\
&emsp;**`defined`** *`identifier`*\
&emsp;diğer herhangi bir sabit ifade

*`conditional`*:\
&emsp;*`if-part`**`elif-parts`* <sub>opt</sub> *`else-part`* <sub>kabul</sub>*`endif-line`*

*`if-part`*:\
&emsp;*`if-line`* *`text`*

*`if-line`*:\
&emsp;**`#if`** *`constant-expression`*\
&emsp;**`#ifdef`** *`identifier`*\
&emsp;**`#ifndef`** *`identifier`*

*`elif-parts`*:\
&emsp;*`elif-line`* *`text`*\
&emsp;*`elif-parts`* *`elif-line`* *`text`*

*`elif-line`*:\
&emsp;**`#elif`** *`constant-expression`*

*`else-part`*:\
&emsp;*`else-line`* *`text`*

*`else-line`*:\
&emsp;**`#else`**

*`endif-line`*:\
&emsp;**`#endif`**

*`digit-sequence`*:\
&emsp;*`digit`*\
&emsp;*`digit-sequence`* *`digit`*

*`digit`*: bunlardan biri \
&emsp;**`0` `1` `2` `3` `4` `5` `6` `7` `8` `9`**

*`token-string`*:\
&emsp;Dize *`token`*

*`token`*:\
&emsp;*`keyword`*\
&emsp;*`identifier`*\
&emsp;*`constant`*\
&emsp;*`operator`*\
&emsp;*`punctuator`*

*`filename`*:\
&emsp;Geçerli işletim sistemi dosya adı

*`path-spec`*:\
&emsp;Yasal dosya yolu

*`text`*:\
&emsp;Herhangi bir metin dizisi

> [!NOTE]
> Aşağıdaki Terminaller, *C++ dil başvurusunun* [sözlü kuralları](../cpp/lexical-conventions.md) bölümünde genişletilir: *`constant`* , *`constant-expression`* ,, *`identifier`* *`keyword`* , *`operator`* ve *`punctuator`* .

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ ön işlemci başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)
