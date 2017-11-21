---
title: "alignment_of sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::alignment_of
dev_langs: C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e20d01c50ea743f62c1cca9e45eedd86a5d4b8c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="alignmentof-class"></a>alignment_of Sınıfı
Belirtilen tür hizalamasını alır. Bu yapı cinsinden uygulanan [alignof](../cpp/alignof-and-alignas-cpp.md). Kullanım `alignof` doğrudan yalnızca gerektiğinde bir hizalama değeri sorgulanamıyor. Etiket gönderme yaparken örneğin bir tamsayı sabiti gerektiğinde alignment_of kullanın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Ty>
struct alignment_of;
```  
  
#### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü bir sorgu değerini tutan türü hizalamasını `Ty`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [aligned_storage sınıfı](../standard-library/aligned-storage-class.md)
