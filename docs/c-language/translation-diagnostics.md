---
title: 'Çeviri: Tanılamalar | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c6a59abc48e5a6bc2aa727508b61abe120c8425
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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