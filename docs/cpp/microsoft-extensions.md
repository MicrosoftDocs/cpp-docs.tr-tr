---
title: Microsoft Uzantıları
ms.date: 11/04/2016
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
ms.openlocfilehash: a2d0846e55122f177b4868c2e80c4f1d27267f5e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179412"
---
# <a name="microsoft-extensions"></a>Microsoft Uzantıları

*asm-ekstresi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm***derleme-yönerge* **;** <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm {** *Assembly-instruction-List* **};** <sub>opt</sub>

*Assembly-instruction-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*derlemesi-yönerge* **;** <sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Assembly-yönerge* **;** *Assembly-instruction-List* **;** <sub>opt</sub>

*MS-değiştirici-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MS-değiştirici* *MS-Modifier-List*<sub>opt</sub>

*MS-değiştirici*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__cdecl**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__fastcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__stdcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__syscall** (gelecekteki uygulamalar için ayrılmıştır)<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__oldcall** (gelecekteki uygulamalar için ayrılmıştır)<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__unaligned** (gelecekteki uygulamalar için ayrılmıştır)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tabanlı-değiştirici*

*temel değiştirici*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__based (** *tabanlı tür* **)**

*temel tür*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*adı*
