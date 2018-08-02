---
title: CompareStringOrdinal yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs:
- C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58e808510868e375672ee5de0b27c4bed3c568e0
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464057"
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
 *lhs*  
 Karşılaştırılacak ilk HSTRING.  
  
 *Sol*  
 Karşılaştırılacak ikinci HSTRING.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Koşul|  
|-----------|---------------|  
|-1|*lhs* olduğu küçüktür *sol*.|  
|0|*lhs* eşittir *sol*.|  
|1.|*lhs* büyüktür *sol*.|  
  
## <a name="remarks"></a>Açıklamalar  
 İki belirtilen HSTRING nesneyi karşılaştırır ve bir sıralama düzeni kendi göreli konumunu belirten bir tamsayı döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::Details Ad Alanı](../windows/microsoft-wrl-wrappers-details-namespace.md)