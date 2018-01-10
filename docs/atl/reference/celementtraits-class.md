---
title: "CElementTraits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs: C++
helpviewer_keywords: CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ebe629a08170ce011b22595c8b821b278e16faa7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="celementtraits-class"></a>CElementTraits sınıfı
Bu sınıf tarafından koleksiyon sınıfları, yöntemleri ve işlevleri taşıma, kopyalama, karşılaştırma ve karma işlemleri için sağlamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>  
class CElementTraits : public CDefaultElementTraits<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir koleksiyonda depolanan verilerin türü.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, taşıma, kopyalama, karşılaştırma ve bir koleksiyon sınıfı nesnesinde depolanan karma öğeleri için varsayılan statik işlevler ve yöntemler sağlar. `CElementTraits`Bu işlemler varsayılan sağlayıcı olarak koleksiyon sınıfları tarafından belirtilen [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), ve [CRBTree](../../atl/reference/crbtree-class.md).  
  
 Basit veri türleri için varsayılan uygulamaları yeterli olacaktır, ancak daha karmaşık nesneleri depolamak için kullanılan koleksiyon sınıfları, yöntemleri ve İşlevler kullanıcı tarafından sağlanan uygulamaları tarafından geçersiz kılınmalıdır.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
