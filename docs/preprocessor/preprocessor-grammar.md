---
title: Ön işlemci dil bilgisi
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: f0916e3cc9bbdb398db693286dacc4517df03557
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222264"
---
# <a name="preprocessor-grammar"></a>Ön işlemci dil bilgisi

*denetim satırı*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *tanımlayıcı* *belirteç-dize* <sub>opt</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *tanımlayıcı* **(** &#x2800;tanımlayıcı&#x200B;<sub>opt</sub> **,** ... **,** *tanımlayıcı* &#x200B; <sub></sub>opt&#x2800; **)** *belirteci-dize*<sub>katılımı</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **"** _yol-spec_ **"** \
&nbsp;&nbsp;&nbsp;&nbsp; **#include** _yol-spec_ **\<** **>** \
&nbsp;&nbsp;&nbsp;&nbsp; **#line** *basamak sırası* **"** _dosya adı_ **"** &#x200B; <sub>opt</sub>  \
&nbsp;&nbsp;&nbsp;&nbsp; **#undef** *tanımlayıcı*\
&nbsp;&nbsp;&nbsp;&nbsp; **#error** *belirteç-dize*\
&nbsp;&nbsp;&nbsp;&nbsp; **#pragma** *token-string*

*sabit ifadesi*: \
&nbsp;&nbsp;&nbsp;&nbsp;**tanımlı (** &#x2800;*tanımlayıcı*&#x2800; **)** \
&nbsp;&nbsp;&nbsp;&nbsp;**tanımlı** *tanımlayıcı*\
&nbsp;&nbsp;&nbsp;&nbsp;diğer herhangi bir sabit ifade

*koşullu*: \
&nbsp;&nbsp;&nbsp;&nbsp;*IF-Part* *Elif-parçalar* <sub>opt</sub> *Else-bölüm* <sub>opt</sub> *endif-çizgi*

*IF-Part*: \
&nbsp;&nbsp;&nbsp;&nbsp;*IF-Line* *metin*

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
&nbsp;&nbsp;&nbsp;&nbsp;*Else-Line* *metin*

*Else-Line*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*endif-satır*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

*basamak sırası*: \
&nbsp;&nbsp;&nbsp;&nbsp;*Gurmukhi*\
&nbsp;&nbsp;&nbsp;&nbsp;*basamak sırası* *basamak*

*basamak*: bunlardan biri \
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*belirteç-dize*: \
&nbsp;&nbsp;&nbsp;&nbsp;Belirteçlerin dizesi

*belirteç*: \
&nbsp;&nbsp;&nbsp;&nbsp;*sözcükle*\
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*\
&nbsp;&nbsp;&nbsp;&nbsp;*sabit*\
&nbsp;&nbsp;&nbsp;&nbsp;*işlecinde*\
&nbsp;&nbsp;&nbsp;&nbsp;*noktalama işareti*

*dosya adı*: \
&nbsp;&nbsp;&nbsp;&nbsp;Geçerli işletim sistemi dosya adı

*yol-spec*: \
&nbsp;&nbsp;&nbsp;&nbsp;Yasal dosya yolu

*metin*: \
&nbsp;&nbsp;&nbsp;&nbsp;Herhangi bir metin dizisi

> [!NOTE]
> Aşağıdaki Terminaller,  *C++ dil başvurusunun* [sözlü kuralları](../cpp/lexical-conventions.md) bölümünde genişletilir: *sabit*, *sabit-ifade*, *tanımlayıcı*, *anahtar sözcük*, *işleç*ve  *noktalama*.

## <a name="see-also"></a>Ayrıca bkz.

[Dilbilgisi özeti (C/C++)](../preprocessor/grammar-summary-c-cpp.md)
