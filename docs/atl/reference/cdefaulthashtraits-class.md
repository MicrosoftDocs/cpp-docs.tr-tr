---
title: CDefaultHashTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a87ecddfff7cb3096ae30d9da5d9e5b6913adcbd
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886251"
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits sınıfı
Bu sınıf, karma değerleri hesaplamak için statik işlev sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>  
class CDefaultHashTraits
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Koleksiyonda depolanacak veri türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDefaultHashTraits::Hash](#hash)|(Statik) Belirli bir öğe için bir karma değeri hesaplamak için bu işlevi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf belirli bir öğe için bir karma değer döndüren tek bir statik işlev içerir. Bu sınıf tarafından kullanılan [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="hash"></a>  CDefaultHashTraits::Hash  
 Belirli bir öğe için bir karma değeri hesaplamak için bu işlevi çağırın.  
  
```
static ULONG Hash(const T& element) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *Öğesi*  
 Öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karma değer döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin varsayılan karma algoritması çok basittir: öğe numarası dönüş değeridir. Daha karmaşık bir algoritma gerekli olduğunda bu işlev geçersiz kılar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
