---
title: "Birden çok açıklama bloğundaki hedefler | Microsoft Docs"
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
- blocks, multiple description
- multiple description blocks
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 395a70203018f20c86cbd906e1f622722cabc539
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="targets-in-multiple-description-blocks"></a>Birden Çok Açıklama Bloğundaki Hedefler
Bir hedef farklı komutlarını kullanarak birden çok açıklama bloğundaki güncelleştirmek için iki birbirini izleyen iki nokta üst üste (:) hedefleri ve bağımlılıklar arasında belirtin.  
  
```  
target.lib :: one.asm two.asm three.asm  
    ml one.asm two.asm three.asm  
    lib target one.obj two.obj three.obj  
target.lib :: four.c five.c  
    cl /c four.c five.c  
    lib target four.obj five.obj  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefleri](../build/targets.md)