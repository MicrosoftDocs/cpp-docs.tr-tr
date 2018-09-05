---
title: Microsoft uzantıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5699ce82a6e8537f12da50fdcb8288da167ecca3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752245"
---
# <a name="microsoft-extensions"></a>Microsoft Uzantıları

*asm deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm***derleme yönergesinin* **;** <sub>iyileştirilmiş  </sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm {***derleme yönerge listesi***};** <sub>iyileştirilmiş    </sub>

*derleme yönerge listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*derleme yönergesinin* **;** <sub>iyileştirilmiş</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*derleme yönergesinin* **;** *derleme yönerge listesi* **;** <sub>iyileştirilmiş</sub>

*MS-modifier-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MS-modifier* *ms-modifier-list*<sub>iyileştirilmiş</sub>

*MS-modifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__cdecl**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__fastcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__stdcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__syscall** (gelecekteki uygulamalar için ayrılmıştır)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__oldcall** (gelecekteki uygulamalar için ayrılmıştır)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__unaligned** (gelecekteki uygulamalar için ayrılmıştır)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*alan değiştiricisi*

*alan değiştiricisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__based (** *temel türü* **)**

*temel tür*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Adı*