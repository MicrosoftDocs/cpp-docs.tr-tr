---
title: Bildirimlerin Özeti
ms.date: 11/04/2016
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
ms.openlocfilehash: 21d6866f8e0b370d8a0d93253a6259302666963a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647206"
---
# <a name="summary-of-declarations"></a>Bildirimlerin Özeti

*bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *öznitelik-seq*<sub>iyileştirilmiş</sub> *init-declarator-list*<sub>iyileştirilmiş</sub> **;**

*bildirim tanımlayıcıları*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı tanımlayıcısı* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub>

*öznitelik-seq* :&nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*öznitelik* *öznitelik-seq*<sub>iyileştirilmiş</sub>

*öznitelik* : biri&nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;[__asm](../assembler/inline/asm.md) [__clrcall](../cpp/clrcall.md) [__stdcall](../cpp/stdcall.md) [__based](../cpp/based-grammar.md) [__fastcall](../cpp/fastcall.md) [__thiscall](../cpp/thiscall.md) [__cdecl](../cpp/cdecl.md) [__inline](../cpp/inline-functions-cpp.md) [__vectorcall](../cpp/vectorcall.md)

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list***,***init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci***=***Başlatıcı*  / \* skaler başlatma \*/

*depolama sınıfı tanımlayıcısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Otomatik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Kaydolun**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Statik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**tür tanımı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (** *genişletilmiş-decl-değiştirici-seq* **)**  / \* Microsoft Specific \*/

*tür belirticisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Geçersiz kılma**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Char**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kısa**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**int**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int8**  / \* Microsoft'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int16**  / \* Microsoft'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int32**  / \* Microsoft'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int64**  / \* Microsoft'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uzun**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kayan nokta**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**çift**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**İmzalı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**İşaretsiz**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya union tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sabit listesi belirticisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*TypeDef adı*

*tür niteleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**const**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Volatile**

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşaretçi*<sub>iyileştirilmiş</sub> *doğrudan bildirimcisi*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(** *bildirimci* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **[** *sabit-ifade*<sub>iyileştirilmiş</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *parametre türü listesi* **)**  / \* yeni stil bildirimci \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *tanımlayıcı listesi*<sub>iyileştirilmiş</sub> **)**  / \* Kullanımdan kalktı stili bildirimci \*/

*İşaretçi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *tür niteleyici listesi*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *tür niteleyici listesi*<sub>iyileştirilmiş</sub> *işaretçi*

*parametre türü listesi*:&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; / \* Parametre listesi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **,...**

*parametre listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parametre listesi* **,** *parametre bildirimi*

*tür niteleyici listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyici listesi* *tür niteleyicisi*

*sabit listesi belirticisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Enum** *tanımlayıcı*<sub>iyileştirilmiş</sub> **{** *numaralandırıcı-listesi* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Enum** *tanımlayıcısı*

*Numaralandırıcı-listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırıcı-listesi* **,** *numaralandırıcısı*

*Numaralandırıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırma sabiti*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırma sabiti* **=** *sabit-ifade*

*Numaralandırma sabiti*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*

*struct veya union tanımlayıcısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yapı veya birleşim* *tanımlayıcı*<sub>iyileştirilmiş</sub> **{** *yapı bildirim listesi* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yapı veya birleşim* *tanımlayıcısı*

*yapı veya birleşim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Yapı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**birleşim**

*Yapı bildirim listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yapı bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yapı bildirim listesi* *yapı bildirimi*

*Yapı bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Belirleyicisi niteleyici listesinin* *yapı bildirimci listesi* **;**

*Belirleyicisi niteleyici listesinin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *tanımlayıcısı niteleyici listesi*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *tanımlayıcısı niteleyici listesi*<sub>iyileştirilmiş</sub>

*Yapı-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yapı-declarator* *yapı bildirimci listesi* **,** *yapı bildirimcisi*

*Yapı-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *bildirimci*<sub>iyileştirilmiş</sub> **:** *sabit-ifade*

*parametre bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *bildirimci*  / \* adlandırılmış bildirimcisi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *soyut bildirimci*<sub>iyileştirilmiş</sub>  / \* anonim bildirimcisi \*/

*tanımlayıcı listesi*: /\* eski stil bildirimci için \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı listesi* **,** *tanımlayıcısı*

*soyut bildirimci*: /\* anonim Bildirimciler ile kullanılan \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşaretçi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşaretçi*<sub>iyileştirilmiş</sub> *doğrudan soyut bildirimci*

*doğrudan soyut bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(** *soyut bildirimci* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan soyut bildirimci*<sub>iyileştirilmiş</sub> **[** *sabit-ifade*<sub>iyileştirilmiş</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan soyut bildirimci*<sub>iyileştirilmiş</sub> **(** *parametre türü listesi*<sub>iyileştirilmiş</sub> **)**

*Başlatıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *başlatıcı listesi* **}**  / \* toplama başlatma \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *başlatıcı listesi* **,}**

*Başlatıcı listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Başlatıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Başlatıcı listesi* **,** *Başlatıcı*

*tür adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Belirleyicisi niteleyici listesinin* *soyut bildirimci*<sub>iyileştirilmiş</sub>

*TypeDef adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*

*Genişletilmiş-decl-değiştirici-seq*:&nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-değiştirici*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-değiştirici-seq* *genişletilmiş-decl-değiştirici*

*Genişletilmiş-decl-değiştirici*:&nbsp; &nbsp; &nbsp; &nbsp; / \* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**iş parçacığı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Kuralları](../cpp/calling-conventions.md)<br/>
[Tümcecik Yapısı Dil Bilgisi](../c-language/phrase-structure-grammar.md)<br/>
[Kullanılmayan Çağırma Kuralları](../cpp/obsolete-calling-conventions.md)