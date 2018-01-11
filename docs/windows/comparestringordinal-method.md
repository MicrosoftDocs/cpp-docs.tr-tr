---
title: "CompareStringOrdinal yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs: C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c7e83d78bd311d7a3bfcba0cbe1a092c6c1c46b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lhs`  
 Karşılaştırma yapılacak ilk HSTRING.  
  
 `rhs`  
 Karşılaştırılacak ikinci HSTRING.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Koşul|  
|-----------|---------------|  
|-1|`lhs`olan değerinden `rhs`.|  
|0|`lhs`eşittir `rhs`.|  
|1.|`lhs`Daha fazla `rhs`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen iki HSTRING nesneyi karşılaştırır ve bir sıralama düzeni göreli konumlarını gösteren bir tamsayı döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::Details Ad Alanı](../windows/microsoft-wrl-wrappers-details-namespace.md)