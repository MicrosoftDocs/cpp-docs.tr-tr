---
title: Bildirimlerin Özeti
ms.date: 11/04/2016
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
ms.openlocfilehash: 88cfc78089e0efd4765a40ab0d9c6dc333deb125
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857027"
---
# <a name="summary-of-declarations"></a>Bildirimlerin Özeti

*bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-tanımlayıcılar* *özniteliği-seq*<sub>opt</sub> *init-declarator-list*<sub>opt</sub> **;**

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>opt</sub>

*öznitelik-Seq* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*öznitelik* *özniteliği-seq*<sub>opt</sub>

*öznitelik* : bir&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;[__asm](../assembler/inline/asm.md) [__clrcall](../cpp/clrcall.md) [__stdcall](../cpp/stdcall.md) [__based](../cpp/based-grammar.md) [__fastcall](../cpp/fastcall.md) [__thiscall](../cpp/thiscall.md) [__cdecl](../cpp/cdecl.md) [__inline](../cpp/inline-functions-cpp.md) [__vectorcall](../cpp/vectorcall.md)

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list* **,** *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci* **=** *Başlatıcı*  / \* skaler başlatma \*/

*depolama sınıfı Belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Otomatik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Kaydet**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**statik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**typedef**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *Genişletilmiş-decl-değiştirici-seq* **)**  /\* Microsoft 'a özgü \*/

*tür belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**void**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**karakteri**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kısa**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**int**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int8** /\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int16** /\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int32** /\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int64** /\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uzun**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**float**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Double**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**imzalı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**işaretsiz**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-Union-belirleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enum belirleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*typedef-adı*

*tür niteleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**const**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**geçici**

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *bildirimci* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **[** *sabit ifade*<sub>katılımı</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *parametre-türü-listesi* **)**  /yeni stil bildirimci \* \*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *tanımlayıcı listesi*<sub>opt</sub> **)**  /eski stil bildirimci \* \*

*işaretçi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *tür niteleyicisi-List*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *tür niteleyicisi-List*<sub>opt</sub> *işaretçisi*

*parametre-tür-listesi*:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/\* parametre listesi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi* **,...**

*parametre-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-liste* **,** *parametre bildirimi*

*tür niteleyicisi-Listele*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi-List* *tür niteleyicisi*

*sabit listesi belirticisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**enum** *tanımlayıcı*<sub>opt</sub> **{** *Numaralandırıcı-listesi* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**enum** *tanımlayıcısı*

*Numaralandırıcı-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırıcı-liste* **,** *Numaralandırıcı*

*Numaralandırıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*numaralandırması-sabit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*numaralandırması-sabit* **=** *sabit ifadesi*

sabit *listesi-sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*

*struct veya-Union-belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-UNION* *Identifier*<sub>opt</sub> **{** *struct-declaration-List* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-Union* *tanımlayıcısı*

*struct veya-Union*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**yapısı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**birleşimi**

*struct-declaration-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-bildirimi-List* *struct-declaration*

*struct-bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcısı-niteleyici-List* *struct-declarator-list* **;**

*belirtici niteleyicisi-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *belirleyicisi-niteleyici-List*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *belirleyicisi-niteleyici-List*<sub>opt</sub>

*struct-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declarator* *struct-declarator-list* **,** *struct-declarator*

*struct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimci*<sub>opt</sub> **:** *sabit ifadesi*

*parametre bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-tanımlayıcılar* *bildirimci* /adlandırılmış bildirimci \* \*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-tanımlayıcılar* *soyut-bildirimci*<sub>opt</sub> /\* anonim bildirimci \*/

*tanımlayıcı listesi*: eski stil bildirimci \*için/\* /<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı-liste* **,** *tanımlayıcı*

*soyut-declarator*:/\* anonim bildirimciler \*kullanıldı /<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan Özet-bildirimci*

*doğrudan Özet-bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *soyut-declarator* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan soyut-declarator*<sub>opt</sub> **[** *sabit ifade*<sub>katılımı</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan soyut-declarator*<sub>opt</sub> **(** *Parameter-Type-List*<sub>opt</sub> **)**

*Başlatıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *Başlatıcı-listesi* **}**  /toplu başlatma \* \*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *Başlatıcı-listesi* **,}**

*Başlatıcı-Liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*başlatıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Başlatıcı-listesi* **,** *Başlatıcı*

*tür adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcısı-niteleyici-List* *abstract-declarator*<sub>opt</sub>

*typedef-adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*

*Genişletilmiş-decl-Modifier-Seq*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-Modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-değiştirici-seq* *Extended-decl-değiştiricisi*

*Extended-decl-değiştirici*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**iş parçacığı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Kuralları](../cpp/calling-conventions.md)<br/>
[Tümcecik Yapısı Dil Bilgisi](../c-language/phrase-structure-grammar.md)<br/>
[Kullanılmayan Çağırma Kuralları](../cpp/obsolete-calling-conventions.md)