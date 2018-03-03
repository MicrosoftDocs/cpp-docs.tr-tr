---
title: "Çalışma zamanı türü bilgileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b0b0124a69a0110bda94055964fbcdb54e5a754
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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