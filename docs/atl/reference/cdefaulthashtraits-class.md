---
title: "CDefaultHashTraits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2407ffdd5d8ea327cd4669f2c33ccda5e0246d6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits sınıfı
Bu sınıf, karma değerleri hesaplamak için statik bir işlev sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>  
class CDefaultHashTraits
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir koleksiyonda depolanan verilerin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDefaultHashTraits::Hash](#hash)|(Statik) Verilen öğe için bir karma değer hesaplamak için bu işlevini çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf için belirli bir öğenin bir karma değer döndürür tek bir statik işlevi içerir. Bu sınıf tarafından kullanılan [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="hash"></a>CDefaultHashTraits::Hash  
 Verilen öğe için bir karma değer hesaplamak için bu işlevini çağırın.  
  
```
static ULONG Hash(const T& element) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `element`  
 Öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karma değer döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan karma algoritması çok basittir: dönüş değeri öğesi sayısıdır. Daha karmaşık bir algoritma gerekli olduğunda bu işlev geçersiz kılar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
