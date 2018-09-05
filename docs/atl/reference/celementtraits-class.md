---
title: CElementTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45139b16ebb923acd004d995cd9466ea9e39e163
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765742"
---
# <a name="celementtraits-class"></a>CElementTraits sınıfı

Bu sınıf, taşıma, kopyalama, karşılaştırma ve karma işlemleri için yöntemleri ve işlevleri sağlamak için koleksiyon sınıfları tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>  
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parametreler

`T`  
Koleksiyonda depolanacak veri türü.

## <a name="remarks"></a>Açıklamalar

Bu sınıf, taşıma, kopyalama, karşılaştırma ve bir koleksiyon sınıfı nesnesinde depolanan karma öğeleri için varsayılan statik işlevler ve yöntemleri sağlar. `CElementTraits` Bu işlemlerin varsayılan sağlayıcı olarak koleksiyon sınıfları tarafından belirtilen [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), ve [CRBTree](../../atl/reference/crbtree-class.md).

Varsayılan uygulamaları basit veri türleri için yeterli olacaktır, ancak daha karmaşık nesneleri depolamak için kullanılan koleksiyon sınıfları, yöntemleri ve işlevleri kullanıcı tarafından sağlanan uygulamaları tarafından geçersiz kılınmalıdır.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

## <a name="see-also"></a>Ayrıca Bkz.

[CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
