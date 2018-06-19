---
title: Çalışma zamanı türü bilgileri | Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b23188b3dd49afb619576fa9cdcece69feca94f3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419998"
---
# <a name="run-time-type-information"></a>Çalışma Zamanı Türü Bilgileri
Çalışma zamanı türü bilgileri (RTTI) program yürütülmesi sırasında belirlenmesi için bir nesne türü izin veren bir mekanizmadır. Sınıf kitaplıkları birçok satıcıları bu işlevselliği kendilerini uygulama çünkü RTTI C++ dili eklendi. Bu kitaplıklar arasındaki uyumsuzluklar neden oldu. Bu nedenle, belirgin hale çalışma zamanı türü bilgileri dil düzeyinde gerektiği için destek.  
  
 Daha anlaşılır olması amacıyla bu RTTI tartışması işaretçileri neredeyse tamamen büyük/küçük harf sınırlıdır. Ancak, açıklanan kavramları başvurular için de geçerlidir.  
  
 Çalışma zamanı türü bilgileri için üç ana C++ dil öğeleri şunlardır:  
  
-   [Dynamic_cast](../cpp/dynamic-cast-operator.md) işleci.  
  
     Çok biçimli türleri dönüştürme için kullanılır.  
  
-   [TypeID](../cpp/typeid-operator.md) işleci.  
  
     Tam bir nesne türünü tanımlamak için kullanılır.  
  
-   [Type_info](../cpp/type-info-class.md) sınıfı.  
  
     Tarafından döndürülen tür bilgiyi tutmak için kullanılan `typeid` işleci.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama](../cpp/casting.md)