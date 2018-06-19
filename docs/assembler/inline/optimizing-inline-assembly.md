---
title: Satır içi derleme en iyi duruma getirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c494594e3b7c541487f34fd33359b0e31f73dd61
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050564"
---
# <a name="optimizing-inline-assembly"></a>Satır İçi Derlemeyi En İyi Duruma Getirme
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Varlığını bir `__asm` bir işlev bloğunda iyileştirme çeşitli şekillerde etkiler. İlk olarak, derleyici en iyi duruma getirme dener `__asm` kendisini engelleyin. Assembly dili yazma tam olarak aldığınızdır. İkincisi, varlığını bir `__asm` blok etkiler değişken depolama kaydedin. Derleyici enregistering değişkenleri arasında önler bir `__asm` kasanın içindekileri tarafından değiştirilmesi bloke `__asm` bloğu. Son olarak, diğer bir işlev genelinde iyileştirmeleri eklenmesi, bir işlev derleme dili tarafından etkilenmez.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)