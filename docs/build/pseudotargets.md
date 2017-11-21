---
title: "Sözde hedefler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b018cd586e48f344b93b31571ba60ae9982ad4fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="pseudotargets"></a>Sözde Hedefler
Bir pseudotarget bir bağımlılık satırda bir dosya adı yerine kullanılan bir etiketi belirtin. Yok ve bu nedenle güncel olan bir dosya olarak yorumlanır. NMAKE pseudotarget ait zaman damgası tüm bağımlıları en son olduğunu varsayar. Hiçbir bağımlıları varsa, geçerli saati varsayılır. Bir pseudotarget hedef olarak kullanılıyorsa, kendi komutları her zaman yürütülür. Bağımlı kullanılan bir pseudotarget de başka bir bağımlılık olarak hedefi olarak yer almalıdır. Ancak, bu bağımlılık komutları blok olması gerekmez.  
  
 Pseudotarget adları hedefler için dosya adı sözdizimi kurallarına. Ancak, bir uzantı adı yoksa (yani, bir nokta içermeyen), dosya adları için 8 karakterlik sınırı aşabilir ve en fazla 256 karakterden uzun olamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefleri](../build/targets.md)