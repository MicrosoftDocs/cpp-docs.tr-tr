---
title: Sözde hedefler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67dbc6ae3ad331ab3297b62d00044c3edf679994
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368414"
---
# <a name="pseudotargets"></a>Sözde Hedefler
Bir pseudotarget bir bağımlılık satırda bir dosya adı yerine kullanılan bir etiketi belirtin. Yok ve bu nedenle güncel olan bir dosya olarak yorumlanır. NMAKE pseudotarget ait zaman damgası tüm bağımlıları en son olduğunu varsayar. Hiçbir bağımlıları varsa, geçerli saati varsayılır. Bir pseudotarget hedef olarak kullanılıyorsa, kendi komutları her zaman yürütülür. Bağımlı kullanılan bir pseudotarget de başka bir bağımlılık olarak hedefi olarak yer almalıdır. Ancak, bu bağımlılık komutları blok olması gerekmez.  
  
 Pseudotarget adları hedefler için dosya adı sözdizimi kurallarına. Ancak, bir uzantı adı yoksa (yani, bir nokta içermeyen), dosya adları için 8 karakterlik sınırı aşabilir ve en fazla 256 karakterden uzun olamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefler](../build/targets.md)