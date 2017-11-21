---
title: "CAutoPtrElementTraits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
dev_langs: C++
helpviewer_keywords: CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1b7d09894e7258ab740e09fb45008a4eeb8a3ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cautoptrelementtraits-class"></a>CAutoPtrElementTraits sınıfı
Bu sınıf, akıllı işaretçiler koleksiyonları oluştururken yöntemleri, statik işlevler ve tür tanımları yararlı sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>  
class CAutoPtrElementTraits 
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```    
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İşaretçi türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|  
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, kuruluşlara yardımcı olmaktayız akıllı işaretçiler içeren koleksiyon sınıfı nesneleri oluşturma yöntemleri, statik işlevler ve tür tanımları sağlar. Sınıfları [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) ve [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) öğesinden türetilen `CAutoPtrElementTraits`. Akıllı işaretçiler koleksiyonu oluşturma vektör yeni ve delete işleçleri gerektiriyorsa, kullanın [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) yerine.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoPtrElementTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="inargtype"></a>CAutoPtrElementTraits::INARGTYPE  
 Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.  
  
```
typedef CAutoPtr<T>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CAutoPtrElementTraits::OUTARGTYPE  
 Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.  
  
```
typedef T *& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
