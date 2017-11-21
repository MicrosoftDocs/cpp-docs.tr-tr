---
title: "Satır içi derleme en iyi duruma getirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e977c89408917643c79f55d415fac212726c50d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="optimizing-inline-assembly"></a>Satır İçi Derlemeyi En İyi Duruma Getirme
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Varlığını bir `__asm` bir işlev bloğunda iyileştirme çeşitli şekillerde etkiler. İlk olarak, derleyici en iyi duruma getirme dener `__asm` kendisini engelleyin. Assembly dili yazma tam olarak aldığınızdır. İkincisi, varlığını bir `__asm` blok etkiler değişken depolama kaydedin. Derleyici enregistering değişkenleri arasında önler bir `__asm` kasanın içindekileri tarafından değiştirilmesi bloke `__asm` bloğu. Son olarak, diğer bir işlev genelinde iyileştirmeleri eklenmesi, bir işlev derleme dili tarafından etkilenmez.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır içi derleyicisi](../../assembler/inline/inline-assembler.md)