---
title: Ön işlemci Dil Bilgisi
ms.date: 09/04/2018
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: 17768b7ec1442f2af1abf76596527d4df69b1534
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614194"
---
# <a name="preprocessor-grammar"></a>Ön işlemci Dil Bilgisi

*Satır içi denetim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** *tanımlayıcı* *belirteç dizesinde*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** <em>tanımlayıcı</em>**(** *tanımlayıcı*<sub>iyileştirilmiş</sub> **,** ... **,** *tanımlayıcı*<sub>iyileştirilmiş</sub> **)** *belirteç dizesinde*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **"** *path-spec* **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **\<** *path-spec* **>**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#line** *basamak dizisi***"** *filename* **"**<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#undef** *tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#error** *belirteci dizesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#pragma** *belirteci dizesi*

*Sabit ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**tanımlanan (** *tanımlayıcı* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**tanımlanan** *tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;herhangi bir sabit ifade

*Koşullu* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Eğer bölümü* *elif-parts*<sub>iyileştirilmiş</sub> *else bölümünü*<sub>iyileştirilmiş</sub> *endif satır*

*Eğer bölümü* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Eğer satır içi* *metin*

*Eğer satır içi* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#if** *sabit-ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifdef** *tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifndef** *tanımlayıcısı*

*elif-parts* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif-satırı* *metin*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif-parts* *elif-satırı* *metin*

*elif-satırı* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#elif** *sabit-ifade*

*else bölümünü* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*başka satır* *metin*

*başka satır* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#else**

*Satır içi endif* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#endif**

*basamak dizisi* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak dizisi* *basamak*

*basamak* : biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1, 2, 3, 4, 5, 6, 7, 8, 9**

*belirteç dizesinde* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Dize belirteçleri

*belirteç* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Anahtar sözcüğü*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Sabit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşleci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Noktalama işaretçisi*

*filename* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Geçerli işletim sistemi dosya adı

*PATH-spec* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Geçerli dosya yolu

*metin* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Metin dizisi

> [!NOTE]
> İçinde aşağıdaki Terminal olmayanları Genişletilmiş [sözcük kuralları](../cpp/lexical-conventions.md) bölümünü *C++ dil başvurusu*: *sabit*, *sabit-ifade* , *tanımlayıcı*, *anahtar sözcüğü*, *işleci*, ve *noktalama işaretçisi*.

## <a name="see-also"></a>Ayrıca Bkz.

[Dilbilgisi Özeti (C/C++)](../preprocessor/grammar-summary-c-cpp.md)