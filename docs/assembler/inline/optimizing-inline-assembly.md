---
title: "Satır içi derleme en iyi duruma getirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21f6954ece6adcc60fbb3a8620dd427e7c21042a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="optimizing-inline-assembly"></a>Satır İçi Derlemeyi En İyi Duruma Getirme
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Varlığını bir `__asm` bir işlev bloğunda iyileştirme çeşitli şekillerde etkiler. İlk olarak, derleyici en iyi duruma getirme dener `__asm` kendisini engelleyin. Assembly dili yazma tam olarak aldığınızdır. İkincisi, varlığını bir `__asm` blok etkiler değişken depolama kaydedin. Derleyici enregistering değişkenleri arasında önler bir `__asm` kasanın içindekileri tarafından değiştirilmesi bloke `__asm` bloğu. Son olarak, diğer bir işlev genelinde iyileştirmeleri eklenmesi, bir işlev derleme dili tarafından etkilenmez.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)