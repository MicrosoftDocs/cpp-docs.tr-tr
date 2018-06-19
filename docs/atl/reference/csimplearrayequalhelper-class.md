---
title: CSimpleArrayEqualHelper sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6660f72dbd91a41670b3c5f8772d21caf4b8abc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362134"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper sınıfı
Bu sınıf için bir Yardımcısı, [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class CSimpleArrayEqualHelper
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Türetilmiş bir sınıf.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Statik) İki testleri `CSimpleArray` nesne eşitliği öğeleri.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellikleri sınıf için bir ektir `CSimpleArray` sınıfı. İçinde depolanan iki öğe karşılaştırma için bir yöntem sağlar. bir `CSimpleArray` nesnesi. Varsayılan olarak, öğeleri kullanılarak karşılaştırılır **operator=()**, ancak dizi kendi eşitlik işleci eksikliği karmaşık veri türlerini içeriyorsa, bu sınıfın geçersiz kılmak gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpcoll.h  
  
##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual  
 İki testleri `CSimpleArray` nesne eşitliği öğeleri.  
  
```
static bool IsEqual(
    const T& t1,
    const T& t2);
```  
  
### <a name="parameters"></a>Parametreler  
 *T1*  
 T türünde bir nesne  
  
 *T2*  
 T türünde bir nesne  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri yanlış Aksi takdirde, eşitse true döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSimpleArray sınıfı](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse sınıfı](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
