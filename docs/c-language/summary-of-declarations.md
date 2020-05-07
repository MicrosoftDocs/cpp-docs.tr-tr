---
title: Bildirimlerin Özeti
ms.date: 11/04/2016
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
ms.openlocfilehash: e553f4bdfffcd4bba6a39b2d37af6ba25a3d65d9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170442"
---
# <a name="summary-of-declarations"></a>Bildirimlerin Özeti

*bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-tanımlayıcılar* *özniteliği-seq*<sub>opt</sub> *init-declarator-list*<sub>opt</sub> **;**

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub>

*öznitelik-Seq* &nbsp; &nbsp; &nbsp; &nbsp; :/ Microsoft 'a özgü\*\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*öznitelik* *özniteliği-seq*<sub>opt</sub>

*öznitelik* &nbsp; &nbsp; &nbsp; &nbsp; / :\* Microsoft 'a özgü bir\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;[__asm](../assembler/inline/asm.md) [__clrcall](../cpp/clrcall.md) [__stdcall](../cpp/stdcall.md) [__based](../cpp/based-grammar.md) [__fastcall](../cpp/fastcall.md) [__thiscall](../cpp/thiscall.md) [__cdecl](../cpp/cdecl.md) [__inline](../cpp/inline-functions-cpp.md) [__vectorcall](../cpp/vectorcall.md)

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list*  **,**  *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*skaler başlatma için bildirimci***=***başlatıcısı*  / \*    \*/

*depolama sınıfı Belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Otomatik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kaydolunamadı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**se**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Dış**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**genişletiyor**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (** *Genişletilmiş-decl-değiştirici-seq* **)**  / \* Microsoft 'a özgü\*/

*tür belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Kağıt**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Char**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kısadır**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**'tir**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int8** / __int8\* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int16** / __int16\* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int32** / __int32\* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int64** / __int64\* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kalacağını**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**float**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Çift**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**imza**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**işaretlenmemiş**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya-Union-Belirleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Sabit Listesi belirticisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*TypeDef-adı*

*tür niteleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sabit**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**katılımcıdan**

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(** *bildirimci* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-declarator* **[** *sabit ifade*<sub>katılımı</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-bildirimci* **(** *parametre türü-liste* **)**  / \* yeni stil bildirimci\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-bildirimci* **(** *tanımlayıcı listesi*<sub>opt</sub> **)**  / \* eski stil bildirimci\*/

*işaretçi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong>*tür niteleyicisi-List*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong>*tür niteleyicisi-liste*<sub>opt</sub> *işaretçisi*

*parametre-tür-listesi*&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; :&nbsp; &nbsp; &nbsp; &nbsp; parametre listesi&nbsp; &nbsp; / \*\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-liste* **,...**

*parametre-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre-listesi* **,** *parametre bildirimi*

*tür niteleyicisi-Listele*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi-liste* *tür niteleyicisi*

*sabit listesi belirticisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**enum** *tanımlayıcı*<sub>opt</sub> **{** *Numaralandırıcı-listesi* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sabit listesi** *tanımlayıcısı*

*Numaralandırıcı-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sının*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırıcı-liste* **,** *Numaralandırıcı*

*Numaralandırıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sabit listesi-sabit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;sabit *listesi-sabit* **=** *sabit ifadesi*

sabit *listesi-sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*

*struct veya-Union-belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya-Union* *tanımlayıcısı*<sub>opt</sub> **{** *struct-declaration-List* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya-Union* *tanımlayıcısı*

*struct veya-Union*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sýný**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**birleşim**

*struct-declaration-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declaration-List* *struct-bildirimi*

*struct-bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*belirtici niteleyicisi-List* *struct-declarator-list* **;**

*belirtici niteleyicisi-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *belirleyicisi-niteleyici-List*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *belirleyicisi-niteleyici-List*<sub>opt</sub>

*struct-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declarator* *yapısı-bildirimci-List* **,** *struct-declarator*

*struct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimci*<sub>opt</sub> **:** *sabit ifadesi*

*parametre bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirim-belirticileri* *declarator*  / \* bildirimci adlandırılmış bildirimci\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-tanımlayıcılar* *abstract-bildirimci*<sub>opt</sub>  / \* anonim bildirimci\*/

*tanımlayıcı-liste*:/\* eski stil bildirimci için\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı listesi* **,** *tanımlayıcı*

*abstract-declarator*:/\* anonim bildirimcilerde kullanılır\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çağrısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan Özet bildirimci*

*doğrudan Özet-bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(** *soyut-declarator* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-abstract-declarator*<sub>opt</sub> **[** *sabit ifade*<sub>katılımı</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-abstract-declarator*<sub>opt</sub> **(** *parametre-türü-List*<sub>opt</sub> **)**

*Başlatıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;toplu başlatma için **{** *Başlatıcı-listesi* **}**  / \*\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *Başlatıcı-listesi* **,}**

*Başlatıcı-Liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*izer*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Başlatıcı-Liste* **,** *Başlatıcı*

*tür adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*belirtici niteleyicisi-List* *abstract-declarator*<sub>opt</sub>

*typedef-adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*

*Extended-decl-değiştirici-seq*:&nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Extended-decl-değiştirici*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Extended-decl-değiştirici-seq* *Extended-decl-değiştiricisi*

*Extended-decl-değiştirici*:&nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**zincirinin**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Kuralları](../cpp/calling-conventions.md)<br/>
[Tümcecik Yapısı Dil Bilgisi](../c-language/phrase-structure-grammar.md)<br/>
[Kullanılmayan Çağırma Kuralları](../cpp/obsolete-calling-conventions.md)
