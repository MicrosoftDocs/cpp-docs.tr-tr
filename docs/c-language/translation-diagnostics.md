---
title: "Çeviri: Tanılamalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 10349357fa0411357b702ff48ff9407c1f5b91e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="translation-diagnostics"></a>Çeviri: Tanılamalar
**ANSI 2.1.1.3** bir tanılama nasıl tanımlanır  
  
 Microsoft C şu şekilde hata iletileri oluşturur:  
  
```  
  
filename( line-number ) : diagnostic Cnumbermessage  
```  
  
 Burada *filename* içinde hata ile karşılaşıldı; kaynak dosya adı *satır numarası* derleyici sırasında hata oluştu; algılanan satır numarası `diagnostic` "error" veya "uyarı"; `number` benzersiz dört basamaklı bir sayı değil (öncesinde bir **C**, sözdiziminde belirtildiği gibi) hata veya uyarı; tanımlar `message` açıklayıcı bir iletidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama Tanımlı Davranış](../c-language/implementation-defined-behavior.md)