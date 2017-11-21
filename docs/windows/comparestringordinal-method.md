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
ms.openlocfilehash: 17415efa6519d8e3538f869168db2040ed6e73dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::WRL::Wrappers::details Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)