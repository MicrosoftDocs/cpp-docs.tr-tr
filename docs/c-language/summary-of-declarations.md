---
title: "Bildirimlerin özeti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 61dae4cf26f881014f0d98bbf30ebd10a360b10f
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
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
  
 *init-declarator-list*:  
 *init-declarator*  
  
 *Init bildirimcisi listesi***,***init bildirimcisi*   
  
 *init-declarator*:  
 *bildirimcisi*  
  
 *bildirimcisi***=***Başlatıcı* / * skaler başlatma     \*/  
  
 *depolama sınıfı tanımlayıcısı*:  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **typedef**  
  
 **__declspec (**  *extended-decl-modifier-seq*  **)** /* Microsoft Specific \*/  
  
 *type-specifier*:  
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
  
 *struct-or-union-specifier*  
  
 *Liste belirticisi*  
  
 *typedef-name*  
  
 *tür niteleyicisi*:  
 **const**  
  
 `volatile`  
  
 `declarator`:  
 `pointer`<sub>OPT</sub> *doğrudan bildirimcisi*  
  
 *doğrudan bildirimcisi*:  
 *identifier*  
  
 **(***bildirimcisi***)**   
  
 *doğrudan bildirimcisi***[***sabit ifadesi* <sub>kabul</sub>**]**   
  
 *doğrudan bildirimcisi***(***parametre türü listesi***)** / * yeni stil bildirimcisi       \*/  
  
 *doğrudan bildirimcisi***(***tanımlayıcı listesi*<sub>kabul</sub>**)** / * Kullanımdan kalktı stili bildirimcisi     \*/  
  
 `pointer`:  
 **\*** *tür niteleyicisi listesi*<sub>iptal et</sub>  
  
 **\*** *tür niteleyicisi listesi*<sub>iptal et</sub>`pointer`  
  
 *parametre türü listesi*: /\* parametre listesi \*/  
 *parameter-list*  
  
 *parameter-list* **, ...**  
  
 *parameter-list*:  
 *parameter-declaration*  
  
 *parameter-list*  **,**  *parameter-declaration*  
  
 *tür niteleyicisi listesi*:  
 *tür niteleyicisi*  
  
 *tür niteleyicisi listesi tür niteleyicisi*  
  
 *Liste belirticisi*:  
 **Enum***tanımlayıcısı*<sub>kabul</sub>**{** *numaralandırıcı listesi* **}**   
  
 **Enum***tanımlayıcısı*   
  
 *Numaralandırıcı listesi*:  
 *Numaralandırıcı*  
  
 *Numaralandırıcı listesi***,**   `enumerator`  
  
 `enumerator`:  
 *Numaralandırma sabiti*  
  
 *Numaralandırma sabiti***=***sabit ifadesi*   
  
 *Numaralandırma sabiti*:  
 *identifier*  
  
 *yapı veya birleşim belirleyici*:  
 *struct veya union tanımlayıcı*<sub>kabul</sub>**{** *yapısı bildirimi listesi* **}** *struct veya union tanımlayıcı*  
  
 *struct-or-union*:  
 **struct**  
  
 **birleşim**  
  
 *Yapı bildirimi listesi*:  
 *Yapı bildirimi*  
  
 *Yapı bildirimi listesi yapısı-bildirimi*  
  
 *Yapı bildirimi*:  
 *belirleyici niteleyici listesinde yapısı bildirimcisi listesi***;**   
  
 *specifier-qualifier-list*:  
 *tür belirteci belirleyici niteleyicisi listesi*<sub>iptal et</sub>  
  
 *tür niteleyicisi belirleyici niteleyicisi listesi*<sub>iptal et</sub>  
  
 *Yapı bildirimcisi listesi*:  
 *Yapı bildirimcisi yapısı bildirimcisi listesi***,***yapısı bildirimcisi*   
  
 *Yapı bildirimcisi*:  
 *bildirimcisi*  
  
 *tür belirteci bildirimcisi*<sub>kabul</sub>**:** *sabit ifadesi*  
  
 *parameter-declaration*:  
 *bildirim tanımlayıcıları bildirimcisi* / * adlandırılmış bildirimcisi \*/  
  
 *bildirim tanımlayıcıları Özet-bildirimcisi*<sub>kabul</sub>  **/ \***  anonim bildirimcisi **\*/**  
  
 *tanımlayıcı listesi*:  **/ \***  eski Tarz bildirimcisi için **\* /**  
 *identifier*  
  
 *identifier-list*  **,**  *identifier*  
  
 *Özet bildirimcisi*:  **/ \***  anonim bildirimleri ile kullanılan **\*/**  
 *pointer*  
  
 `pointer`<sub>opt</sub>*direct-abstract-declarator*  
  
 *doğrudan Özet bildirimcisi*:  
 **(***Özet bildirimcisi***)**   
  
 *doğrudan Özet bildirimcisi*<sub>kabul</sub>**[** *sabit ifadesi*<sub>kabul</sub>**]**  
  
 *doğrudan Özet bildirimcisi*<sub>kabul</sub>**(** *parametre türü listesi* <sub>kabul</sub>**)**  
  
 *initializer*:  
 *assignment-expression*  
  
 **{**  *initializer-list*  **}** /* For aggregate initialization \*/  
  
 **{**  *initializer-list*  **, }**  
  
 *initializer-list*:  
 *initializer*  
  
 *initializer-list*  **,**  *initializer*  
  
 *tür adı*:  
 *specifier-qualifier-list abstract-declarator*<sub>opt</sub>  
  
 *TypeDef adı*:  
 *identifier*  
  
 *extended-decl-modifier-seq*:/\*    Microsoft Specific \*/  
 *extended-decl-modifier*<sub>opt</sub>  
  
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