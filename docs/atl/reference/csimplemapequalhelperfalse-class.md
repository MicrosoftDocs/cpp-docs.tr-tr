---
title: "CSimpleMapEqualHelperFalse sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1418114233b59112fcffb58ef4ae7c437af5ab3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse sınıfı
Bu sınıf için bir Yardımcısı, [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Statik) İki anahtar eşitlik için test eder.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Statik) Yanlış değerini döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellikleri sınıf için bir ektir `CSimpleMap` sınıfı. İçindeki iki öğe karşılaştırma için bir yöntem sağlar `CSimpleMap` nesnesi, özellikle iki değer öğe veya iki anahtar öğeleri.  
  
 Değer karşılaştırma her zaman false döndürür ve ayrıca, çağıracak `ATLASSERT` bağımsız değişkeni hiç başvurulduğunda false. Burada eşitlik test yeterince tanımlanmamış durumlarda, bu sınıf için çoğu yöntemleri çalışmayabilir, ancak üzerinde karşılaştırmalarına gibi bağımlı yöntemleri için iyi tanımlanmış bir şekilde başarısız anahtar/değer çiftleri içeren bir eşleme sağlar [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>CSimpleMapEqualHelperFalse::IsEqualKey  
 İki anahtar eşitlik için test eder.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>Parametreler  
 `k1`  
 İlk anahtar.  
  
 `k2`  
 İkinci anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtarları yanlış Aksi takdirde, eşitse true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).  
  
##  <a name="isequalvalue"></a>CSimpleMapEqualHelperFalse::IsEqualValue  
 Yanlış değerini döndürür.  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yanlış değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem her zaman false değerini döndürür ve çağıracak `ATLASSERT` bağımsız değişkeni hiç başvurulduğunda false. Amacı `CSimpleMapEqualHelperFalse::IsEqualValue` eşitlik testleri yeterli tanımlanmamış olduğunda iyi tanımlanmış bir biçimde başarısız olmasına karşılaştırmaları kullanma yöntemleri zorlamak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSimpleMapEqualHelper sınıfı](../../atl/reference/csimplemapequalhelper-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
