---
title: "Açıklama blokları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cec8005599ab6d4e2b7d769f73b5ef2e3869accd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="description-blocks"></a>Açıklama Blokları
Açıklama bloğu komutları bloğu tarafından ardından isteğe bağlı bir bağımlılık satır şöyledir:  
  
```  
targets... : dependents...  
    commands...  
```  
  
 Bir veya daha fazla hedefleri ve sıfır veya daha fazla bağımlıları bir bağımlılık satırı belirtir. Bir hedef satır başlangıcında olması gerekir. İki nokta üst üste (:) tarafından bağımlılıklar ayrı hedeflerden; boşluk ya da sekme izin verilir. Satır bölmek için bir hedef veya bağımlı sonra ters eğik çizgi (\) kullanın. Bir hedef mevcut değilse, bir bağımlı daha önceki bir zaman damgası yok veya bir [pseudotarget](../build/pseudotargets.md), NMAKE komutları yürütür. Bağımlı bir hedef başka bir yerde ve mevcut değil ya da kendi bağımlıları göre güncel değil, geçerli bağımlılık güncelleştirmeden önce NMAKE bağımlı güncelleştirir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
 [Hedefleri](../build/targets.md)  
  
 [Bağımlılıklar](../build/dependents.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE başvurusu](../build/nmake-reference.md)