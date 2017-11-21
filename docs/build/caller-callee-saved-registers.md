---
title: "Çağıran ve Çağrılan Kaydedilmiş Yazmaçlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ebdcf30ea56587b71015a04b5e514dd9ff21aeba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="callercallee-saved-registers"></a>Çağıran ve Çağrılan Kaydedilmiş Yazmaçlar
İşlev çağrıları RAX, RCX, RDX, R8, R9, R10, R11 geçici olarak kabul edilir ve dikkate alınmalıdır kayıtları yok (sürece aksi tarafından güvenliği kanıtlanabilme analiz bütün program iyileştirmesi gibi).  
  
 Yazmaçları RBX, RBP, RDI, RSI, RSP, R12, R13, R14 ve R15 kayıtları kalıcı olarak kabul edilir ve kaydedilmesi gerekir ve bir işlev tarafından geri, bunları kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma kuralı](../build/calling-convention.md)