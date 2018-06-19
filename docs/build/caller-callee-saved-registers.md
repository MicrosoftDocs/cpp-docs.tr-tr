---
title: Çağıran ve Çağrılan Kaydedilmiş Yazmaçlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f65e88c8609d6a2097e9e54c3f52cbd27dce36d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366802"
---
# <a name="callercallee-saved-registers"></a>Çağıran ve Çağrılan Kaydedilmiş Yazmaçlar
İşlev çağrıları RAX, RCX, RDX, R8, R9, R10, R11 geçici olarak kabul edilir ve dikkate alınmalıdır kayıtları yok (sürece aksi tarafından güvenliği kanıtlanabilme analiz bütün program iyileştirmesi gibi).  
  
 Yazmaçları RBX, RBP, RDI, RSI, RSP, R12, R13, R14 ve R15 kayıtları kalıcı olarak kabul edilir ve kaydedilmesi gerekir ve bir işlev tarafından geri, bunları kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralı](../build/calling-convention.md)