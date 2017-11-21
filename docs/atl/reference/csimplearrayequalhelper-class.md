---
title: "CSimpleArrayEqualHelper sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs: C++
helpviewer_keywords: CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d53e09c64aa19b4e843297b64bad132c64a75a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
##  <a name="isequal"></a>CSimpleArrayEqualHelper::IsEqual  
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
