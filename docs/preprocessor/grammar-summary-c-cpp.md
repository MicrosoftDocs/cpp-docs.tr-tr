---
title: Ön işlemci dil bilgisi özeti (C/C++)
description: Microsoft C/C++ DERLEYICISI (MSVC) Önişlemci dilbilgisi sözdizimini tanımlar ve tanımlar.
ms.date: 08/29/2019
helpviewer_keywords:
- grammar
- preprocessor, grammar
ms.assetid: 0acb6e9b-364c-4ef8-ace4-7be980521121
ms.openlocfilehash: 68e5f09acfc6444afb46bcbc0f7e9db10b04afed
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076868"
---
# <a name="preprocessor-grammar-summary-cc"></a>Ön işlemci dil bilgisi özeti (C/C++)

Bu makalede C ve C++ Önişlemci 'nin biçimsel dilbilgisi açıklanır. Ön işleme yönergelerinin ve işleçlerinin sözdizimini içerir. Daha fazla bilgi için bkz. [Önişlemci](../preprocessor/preprocessor.md) ve [Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md).

## <a name="definitions-for-the-grammar-summary"></a><a name="definitions"></a>Dilbilgisi özeti tanımları

Terminal, bir sözdizimi tanımındaki uç noktalardır. Başka bir çözüm mümkün değildir. Terminal, ayrılmış sözcükler ve Kullanıcı tanımlı tanımlayıcılar kümesini içerir.

Terminal dışı, söz dizimi içindeki yer tutuculardır. Çoğu, bu söz dizimi özetinde başka bir yerde tanımlanır. Tanımlar özyinelemeli olabilir. Aşağıdaki Terminaller,  *C++ dil başvurusunun* [sözlü kuralları](../cpp/lexical-conventions.md) bölümünde tanımlanmıştır:

*sabit*, *sabit ifade*, *tanımlayıcı*, *anahtar sözcük*, *işleç*, *noktalama*

İsteğe bağlı bir bileşen, alt indisli <sub>opt</sub>tarafından gösterilir. Örneğin, aşağıdaki sözdizimi, küme ayraçları içine alınmış bir isteğe bağlı ifadeyi gösterir:

**{** *Expression*<sub>opt</sub> **}**

## <a name="document-conventions"></a><a name="conventions"></a>Belge kuralları

Kurallar, sözdiziminin farklı bileşenleri için farklı yazı tipi öznitelikleri kullanır. Simgeler ve yazı tipleri aşağıdaki gibidir:

| Öznitelik | Açıklama |
|---------------|-----------------|
| *& gt* | İtalik tür terminal olmayanları gösterir. |
| **#include** | Kalın türdeki terminaller, gösterildiği gibi girilmesi gereken sabit ayrılmış sözcükler ve simgelerdir. Bu bağlamdaki karakterler, her zaman büyük/küçük harfe duyarlıdır. |
| <sub>et</sub> | Terminal olmayan ve <sub>opt</sub> tarafından izlenen, her zaman isteğe bağlıdır.|
| varsayılan yazı tipi | Bu yazı tipinde açıklanan veya listelenen kümedeki karakterler, deyimlerde terminaller olarak kullanılabilir. |

Terminalden sonraki bir iki nokta üst üste ( **:** ) tanımı tanıtılmıştır. Alternatif tanımlar, ayrı satırlarda listelenmiştir.

Kod sözdizimi blokları ' nda, varsayılan yazı tipindeki bu simgelerin özel bir anlamı vardır:

| Sembol | Açıklama |
|---|---|
| \[] | Köşeli ayraçlar isteğe bağlı bir öğe. |
| {\|} | Küme ayraçları dikey çubuklarla ayrılmış alternatif öğeleri. |
| ... | Önceki öğe deseninin tekrarlanabilir olduğunu gösterir. |

Kod sözdizimi blokları, virgüller (`,`), nokta (`.`), noktalı virgül (`;`), iki nokta üst üste (`:`), parantez (`( )`), çift tırnak (`"`) ve tek tırnak (`'`) değişmez değerler.

## <a name="preprocessor-grammar"></a><a name="grammar"></a>Önişlemci dilbilgisi

*denetim satırı*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *tanımlayıcı* *belirteci-dize*<sub>opt</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *tanımlayıcı* **(** *tanımlayıcı*<sub>opt</sub> **,** ... **,** *tanımlayıcı*<sub>opt</sub> **)** *belirteç-dize*<sub>opt</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **"** _Path-spec_ **"** \
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **\<** _Path-spec_ **>** \
&nbsp;&nbsp;&nbsp;&nbsp; **#line** *basamak sırası* **"** _filename_ **"** <sub>opt</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#undef** *tanımlayıcı*\
&nbsp;&nbsp;&nbsp;&nbsp; **#error** *belirteci-dize*\
&nbsp;&nbsp;&nbsp;&nbsp; **#pragma** *belirteci-dize*

*sabit ifadesi*: \
&nbsp;&nbsp;&nbsp;&nbsp;**tanımlı (** *tanımlayıcı* **)** \
&nbsp;&nbsp;&nbsp;&nbsp;**tanımlı** *tanımlayıcı*\
diğer herhangi bir sabit ifade &nbsp;&nbsp;&nbsp;&nbsp;

*koşullu*: \
&nbsp;&nbsp;&nbsp;&nbsp;*IF-Part* *Elif-Parts*<sub>opt</sub> *Else-parçalı*<sub>opt</sub> *endif-Line*

*IF-Part*: \
&nbsp;&nbsp;&nbsp;&nbsp;*IF-Line* *metni*

*IF-Line*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#if** *sabit ifadesi*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifdef** *tanımlayıcı*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifndef** *tanımlayıcı*

*Elif-parçalar*: \
&nbsp;&nbsp;&nbsp;&nbsp;*Elif-Line* *metin*\
&nbsp;&nbsp;&nbsp;&nbsp;*Elif-parçalar* *Elif-Line* *metin*

*Elif-satır*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#elif** *sabit ifadesi*

*Else-bölüm*: \
&nbsp;&nbsp;&nbsp;&nbsp;*başka satır* *metin*

*Else-Line*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*endif-satır*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

*basamak sırası*: \
&nbsp;&nbsp;&nbsp;&nbsp;*basamak*\
&nbsp;&nbsp;&nbsp;&nbsp;*basamak sırası* *basamağı*

*basamak*: bunlardan biri \
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*belirteç-dize*: \
&nbsp;&nbsp;&nbsp;&nbsp;belirteçleri dizesi

*belirteç*: \
&nbsp;&nbsp;&nbsp;&nbsp;*anahtar sözcüğü*\
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*\
&nbsp;&nbsp;&nbsp;&nbsp;*sabiti*\
&nbsp;&nbsp;&nbsp;&nbsp;*işleci*\
&nbsp;&nbsp;&nbsp;&nbsp;*noktalama*

*dosya adı*: \
&nbsp;&nbsp;&nbsp;&nbsp;yasal işletim sistemi dosya adı

*yol-spec*: \
&nbsp;&nbsp;&nbsp;yasal dosya yolu &nbsp;

*metin*: \
Herhangi bir metin dizisini &nbsp;&nbsp;&nbsp;&nbsp;

> [!NOTE]
> Aşağıdaki Terminaller,  *C++ dil başvurusunun* [sözlü kuralları](../cpp/lexical-conventions.md) bölümünde genişletilir: *sabit*, *sabit-ifade*, *tanımlayıcı*, *anahtar sözcük*, *işleç*ve *noktalama*.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)
