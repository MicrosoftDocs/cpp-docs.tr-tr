---
title: "ML önemli olmayan hatası A2085 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2085
dev_langs: C++
helpviewer_keywords: A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f987b775c13b0e477fd5c1d215d556069535a0fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2085"></a>ML Önemli Olmayan Hatası A2085
**yönerge veya kayıt geçerli CPU modunda kabul edilmedi**  
  
 Bir yönerge, Kaydet veya geçerli işlemci modu için geçerli değil. anahtar sözcüğü kullanmak için girişimde bulunuldu.  
  
 Örneğin, 32-bit yazmaçlar zorunlu [.386](../../assembler/masm/dot-386.md) veya üstü. Denetim kaydeder CR0 kaydının gerektiren ayrıcalıklı modda gibi [.386P](../../assembler/masm/dot-386p.md) veya üstü. Bu hata için de oluşturulacak **NEAR32**, **FAR32**, ve **DÜZ** gerektiren anahtar sözcükler. **386** veya üstü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ML Hata İletileri](../../assembler/masm/ml-error-messages.md)