---
title: Bildirimlerin özeti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9e5fe380d41b5d1e58a63b1aa0b99a239dee515
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392529"
---
# <a name="summary-of-declarations"></a>Bildirimlerin Özeti
`declaration`:  
 *bildirim tanımlayıcıları öznitelik-seq* <sub>kabul</sub> *init bildirimcisi listesi*<sub>kabul</sub>**;**  
  
 /\* *öznitelik seq* Microsoft Specific * /  
  
 *bildirim tanımlayıcıları*:  
 *depolama sınıfı tanımlayıcısı bildirim tanımlayıcıları*<sub>iptal et</sub>  
  
 *tür belirteci bildirim tanımlayıcıları*<sub>iptal et</sub>  
  
 *tür niteleyicisi bildirim tanımlayıcıları*<sub>iptal et</sub>  
  
 *öznitelik seq* : /\* *özniteliği seq* Microsoft Specific \*/  
 *öznitelik özniteliği seq* <sub>iptal et</sub>  
  
 *öznitelik* : aşağıdakilerden birini / * Microsoft Specific \*/  
 ||||  
|-|-|-|  
|[__asm](../assembler/inline/asm.md)|[__clrcall](../cpp/clrcall.md)|[__stdcall](../cpp/stdcall.md)|  
|[__based](../cpp/based-grammar.md)|[__fastcall](../cpp/fastcall.md)|[__thiscall](../cpp/thiscall.md)|  
|[__cdecl](../cpp/cdecl.md)|[__inline](../cpp/inline-functions-cpp.md)|[__vectorcall](../cpp/vectorcall.md)|  
  
 *Init bildirimcisi listesi*:  
 *Init bildirimcisi*  
  
 *Init bildirimcisi listesi***,***init bildirimcisi*  
  
 *Init bildirimcisi*:  
 *bildirimcisi*  
  
 *bildirimcisi***=***Başlatıcı* / * skaler başlatma \*/  
  
 *depolama sınıfı tanımlayıcısı*:  
 **auto**  
  
 **Kaydetme**  
  
 **static**  
  
 **extern**  
  
 **TypeDef**  
  
 **__declspec (***genişletilmiş-decl-değiştirici-seq***)** / * Microsoft Specific     \*/  
  
 *tür belirteci*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 `__int8` / * Microsoft özel \*/  
  
 `__int16` / * Microsoft özel \*/  
  
 `__int32` / * Microsoft özel \*/  
  
 `__int64` / * Microsoft özel \*/  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **İmzalı**  
  
 **İmzasız**  
  
 *yapı veya birleşim belirticisi*  
  
 *Liste belirticisi*  
  
 *TypeDef adı*  
  
 *tür niteleyicisi*:  
 **const**  
  
 `volatile`  
  
 `declarator`:  
 `pointer`<sub>OPT</sub> *doğrudan bildirimcisi*  
  
 *doğrudan bildirimcisi*:  
 *Tanımlayıcı*  
  
 **(***bildirimcisi***)**  
  
 *doğrudan bildirimcisi***[***sabit ifadesi* <sub>kabul</sub>**]**  
  
 *doğrudan bildirimcisi***(***parametre türü listesi***)** / * yeni stil bildirimcisi \*/  
  
 *doğrudan bildirimcisi***(***tanımlayıcı listesi*<sub>kabul</sub>**)** / * Kullanımdan kalktı stili bildirimcisi \*/  
  
 `pointer`:  
 **\*** *tür niteleyicisi listesi*<sub>iptal et</sub>  
  
 **\*** *tür niteleyicisi listesi*<sub>iptal et</sub>`pointer`  
  
 *parametre türü listesi*: /\* parametre listesi \*/  
 *parameter-list*  
  
 *parametre listesi* **,...**  
  
 *parametre listesi*:  
 *parameter-declaration*  
  
 *parametre listesi***,***parametre bildirimi*   
  
 *tür niteleyicisi listesi*:  
 *tür niteleyicisi*  
  
 *tür niteleyicisi listesi tür niteleyicisi*  
  
 *Liste belirticisi*:  
 **Enum***tanımlayıcısı*<sub>kabul</sub>**{** *numaralandırıcı listesi* **}**  
  
 **Enum***tanımlayıcısı*  
  
 *Numaralandırıcı listesi*:  
 *Numaralandırıcı*  
  
 *Numaralandırıcı listesi***,**  `enumerator`  
  
 `enumerator`:  
 *Numaralandırma sabiti*  
  
 *Numaralandırma sabiti***=***sabit ifadesi*  
  
 *Numaralandırma sabiti*:  
 *Tanımlayıcı*  
  
 *yapı veya birleşim belirleyici*:  
 *struct veya union tanımlayıcı*<sub>kabul</sub>**{** *yapısı bildirimi listesi* **}** *struct veya union tanımlayıcı*  
  
 *struct veya union*:  
 **struct**  
  
 **birleşim**  
  
 *Yapı bildirimi listesi*:  
 *Yapı bildirimi*  
  
 *Yapı bildirimi listesi yapısı-bildirimi*  
  
 *Yapı bildirimi*:  
 *belirleyici niteleyici listesinde yapısı bildirimcisi listesi***;**  
  
 *belirleyici niteleyici listesinde*:  
 *tür belirteci belirleyici niteleyicisi listesi*<sub>iptal et</sub>  
  
 *tür niteleyicisi belirleyici niteleyicisi listesi*<sub>iptal et</sub>  
  
 *Yapı bildirimcisi listesi*:  
 *Yapı bildirimcisi yapısı bildirimcisi listesi***,***yapısı bildirimcisi*  
  
 *Yapı bildirimcisi*:  
 *bildirimcisi*  
  
 *tür belirteci bildirimcisi*<sub>kabul</sub>**:** *sabit ifadesi*  
  
 *parametre bildirimi*:  
 *bildirim tanımlayıcıları bildirimcisi* / * adlandırılmış bildirimcisi \*/  
  
 *bildirim tanımlayıcıları Özet-bildirimcisi*<sub>kabul</sub> **/ \*** anonim bildirimcisi **\*/**  
  
 *tanımlayıcı listesi*: **/ \*** eski Tarz bildirimcisi için **\* /**  
 *Tanımlayıcı*  
  
 *tanımlayıcı listesi***,***tanımlayıcısı*   
  
 *Özet bildirimcisi*: **/ \*** anonim bildirimleri ile kullanılan **\*/**  
 *İşaretçi*  
  
 `pointer`<sub>OPT</sub>*doğrudan Özet bildirimcisi*  
  
 *doğrudan Özet bildirimcisi*:  
 **(***Özet bildirimcisi***)**  
  
 *doğrudan Özet bildirimcisi*<sub>kabul</sub>**[** *sabit ifadesi*<sub>kabul</sub>**]**  
  
 *doğrudan Özet bildirimcisi*<sub>kabul</sub>**(** *parametre türü listesi* <sub>kabul</sub>**)**  
  
 *Başlatıcı*:  
 *atama ifadesi*  
  
 **{***başlatıcı listesi***}** / * toplu başlatma için     \*/  
  
 **{***başlatıcı listesi***,}**   
  
 *Başlatıcı listesi*:  
 *Başlatıcı*  
  
 *Başlatıcı listesi***,***Başlatıcı*   
  
 *tür adı*:  
 *belirleyici niteleyici listesinde Özet-bildirimcisi*<sub>iptal et</sub>  
  
 *TypeDef adı*:  
 *Tanımlayıcı*  
  
 *Genişletilmiş-decl-değiştirici-seq*:/\* Microsoft Specific \*/  
 *Genişletilmiş decl-değiştirici*<sub>iptal et</sub>  
  
 *Genişletilmiş-decl-değiştirici-seq genişletilmiş decl-değiştirici*  
  
 *Genişletilmiş decl-değiştirici*: /\* Microsoft Specific \*/  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma kuralları](../cpp/calling-conventions.md)   
 [Tümcecik yapısı dil bilgisi](../c-language/phrase-structure-grammar.md)   
 [Kullanılmayan Çağırma Kuralları](../cpp/obsolete-calling-conventions.md)