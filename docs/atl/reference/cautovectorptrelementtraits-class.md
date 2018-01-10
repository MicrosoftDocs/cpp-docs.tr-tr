---
title: "CAutoVectorPtrElementTraits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
dev_langs: C++
helpviewer_keywords: CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e69be3fa7136b0d411b92299d99d877710d5f118
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cautovectorptrelementtraits-class"></a>CAutoVectorPtrElementTraits sınıfı
Bu sınıf, yöntemleri, statik işlevler ve tür tanımları vektör yeni kullanarak akıllı işaretçiler koleksiyonları oluşturma ve delete işleçleri olduğu durumlarda faydalıdır sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T>  
class CAutoVectorPtrElementTraits : 
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```    
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İşaretçi türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|  
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, kuruluşlara yardımcı olmaktayız akıllı işaretçiler içeren koleksiyon sınıfı nesneleri oluşturma yöntemleri, statik işlevler ve tür tanımları sağlar. Farklı [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md), bu sınıfı kullanır vektör yeni ve delete işleçleri.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoVectorPtrElementTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="inargtype"></a>CAutoVectorPtrElementTraits::INARGTYPE  
 Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.  
  
```
typedef CAutoVectorPtr<T>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CAutoVectorPtrElementTraits::OUTARGTYPE  
 Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.  
  
```
typedef T*& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md)   
 [CAutoVectorPtr sınıfı](../../atl/reference/cautovectorptr-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
