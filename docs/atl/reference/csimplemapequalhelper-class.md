---
title: "CSimpleMapEqualHelper sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
dev_langs: C++
helpviewer_keywords: CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 42c6ef6562b737952782edfac41d3ba405a60ed1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper sınıfı
Bu sınıf için bir Yardımcısı, [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelper
```  
  
#### <a name="parameters"></a>Parametreler  
 `TKey`  
 Anahtar öğesi.  
  
 `TVal`  
 Değer öğesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Statik) İki anahtar eşitlik için test eder.|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Statik) İki değer eşitlik için test eder.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellikleri sınıf için bir ektir `CSimpleMap` sınıfı. İki karşılaştırma için yöntemler sağlar `CSimpleMap` nesne eşitliği öğeleri (özellikle, anahtar ve değer bileşenleri). Varsayılan olarak, anahtarlar ve değerler kullanılarak karşılaştırılır `operator==()`, ancak kendi eşitlik işleci eksikliği karmaşık veri türlerini eşleme içeriyorsa, bu sınıf ek gerekli işlevselliği sağlamak için geçersiz kılınabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>CSimpleMapEqualHelper::IsEqualKey  
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
  
##  <a name="isequalvalue"></a>CSimpleMapEqualHelper::IsEqualValue  
 İki değer eşitlik için test eder.  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>Parametreler  
 *V1*  
 İlk değer.  
  
 *v2*  
 İkinci değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değeri false Aksi takdirde, eşitse true değerini döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSimpleMapEqualHelperFalse sınıfı](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
