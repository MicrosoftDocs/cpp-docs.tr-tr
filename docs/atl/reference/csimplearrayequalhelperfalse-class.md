---
title: "CSimpleArrayEqualHelperFalse sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28d43b6a83842373c2fc169ce43022f1912c4e0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse sınıfı
Bu sınıf için bir Yardımcısı, [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Türetilmiş bir sınıf.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Statik) Yanlış değerini döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu nitelikler sınıf, bir tamamlama `CSimpleArray` sınıfı. BT döndürür false değerini ve ayrıca, çağıracaktır her zaman `ATLASSERT` bağımsız değişkeni hiç başvurulduğunda false. Burada eşitlik test yeterince tanımlanmamış durumlarda, bu sınıf için çoğu yöntemleri çalışmayabilir, ancak üzerinde karşılaştırmalarına gibi bağımlı yöntemleri için iyi tanımlanmış bir şekilde başarısız öğeleri içeren bir dizi sağlar [CSimpleArray:: Bul](../../atl/reference/csimplearray-class.md#find).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelperFalse::IsEqual  
 Yanlış değerini döndürür.  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yanlış değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem her zaman false değerini döndürür ve çağıracak `ATLASSERT` bağımsız değişkeni başvurulan false. Amacı `CSimpleArrayEqualHelperFalse::IsEqual` eşitlik testleri yeterli tanımlanmamış olduğunda iyi tanımlanmış bir biçimde başarısız olmasına karşılaştırmaları kullanma yöntemleri zorlamak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSimpleArrayEqualHelper sınıfı](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
