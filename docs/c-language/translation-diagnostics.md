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
ms.openlocfilehash: bb7f826be88ebec640a6f3b40b38478eea91ed36
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="translation-diagnostics"></a>Çeviri: Tanılamalar
**ANSI 2.1.1.3** bir tanılama nasıl tanımlanır  
  
 Microsoft C şu şekilde hata iletileri oluşturur:  
  
```  
  
filename( line-number ) : diagnostic Cnumbermessage  
```  
  
 Burada *filename* içinde hata ile karşılaşıldı; kaynak dosya adı *satır numarası* derleyici sırasında hata oluştu; algılanan satır numarası `diagnostic` "error" veya "uyarı"; `number` benzersiz dört basamaklı bir sayı değil (öncesinde bir **C**, sözdiziminde belirtildiği gibi) hata veya uyarı; tanımlar `message` açıklayıcı bir iletidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama tanımlı davranış](../c-language/implementation-defined-behavior.md)