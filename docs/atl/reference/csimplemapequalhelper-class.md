---
title: CSimpleMapEqualHelper sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d629806582d7ad9902ef5ca0d9425d6f1ecd7d7
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879701"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper sınıfı
Bu sınıf için Yardımcısı, [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelper
```  
  
#### <a name="parameters"></a>Parametreler  
 *TKey*  
 Anahtar öğesi.  
  
 *TVal*  
 Değer öğesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Statik) İki anahtar eşitlik için test eder.|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Statik) Eşitlik için iki değeri test eder.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu nitelikler sınıfı için bir ektir `CSimpleMap` sınıfı. İki karşılaştırma yöntemlerini sağlar `CSimpleMap` nesne eşitliği (özellikle, anahtar ve değer bileşenleri) öğeleri. Varsayılan olarak, anahtarları ve değerleri kullanılarak karşılaştırılır **operator==()**, ancak fazladan gerekli işlevselliği sağlamak için eşleme eksik kendi eşitlik işleci karmaşık veri türleri içeriyorsa, bu sınıf kılınabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>  CSimpleMapEqualHelper::IsEqualKey  
 İki anahtar eşitlik için test eder.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>Parametreler  
 *K1*  
 İlk anahtar.  
  
 *K2*  
 İkinci anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtarları false, eşitse true döndürür.  
  
##  <a name="isequalvalue"></a>  CSimpleMapEqualHelper::IsEqualValue  
 Eşitlik için iki değeri test eder.  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>Parametreler  
 *V1*  
 İlk değer.  
  
 *v2*  
 İkinci değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değerler yanlış Aksi takdirde, eşitse true döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSimpleMapEqualHelperFalse sınıfı](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
