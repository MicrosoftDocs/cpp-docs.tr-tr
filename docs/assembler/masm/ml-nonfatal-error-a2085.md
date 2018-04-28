---
title: ML önemli olmayan hatası A2085 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f0a014810679f0b48f79198b1335240f5cd6a8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="ml-nonfatal-error-a2085"></a>ML Önemli Olmayan Hatası A2085
**yönerge veya kayıt geçerli CPU modunda kabul edilmedi**  
  
 Bir yönerge, Kaydet veya geçerli işlemci modu için geçerli değil. anahtar sözcüğü kullanmak için girişimde bulunuldu.  
  
 Örneğin, 32-bit yazmaçlar zorunlu [.386](../../assembler/masm/dot-386.md) veya üstü. Denetim kaydeder CR0 kaydının gerektiren ayrıcalıklı modda gibi [.386P](../../assembler/masm/dot-386p.md) veya üstü. Bu hata için de oluşturulacak **NEAR32**, **FAR32**, ve **DÜZ** gerektiren anahtar sözcükler. **386** veya üstü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ML Hata İletileri](../../assembler/masm/ml-error-messages.md)