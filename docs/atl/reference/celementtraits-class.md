---
title: CElementTraits sınıfı
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 646b445aed93c9041932c60442f61792f5e1a7e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245774"
---
# <a name="celementtraits-class"></a>CElementTraits sınıfı

Bu sınıf, taşıma, kopyalama, karşılaştırma ve karma işlemleri için yöntemleri ve işlevleri sağlamak için koleksiyon sınıfları tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="remarks"></a>Açıklamalar

Bu sınıf, taşıma, kopyalama, karşılaştırma ve bir koleksiyon sınıfı nesnesinde depolanan karma öğeleri için varsayılan statik işlevler ve yöntemleri sağlar. `CElementTraits` Bu işlemlerin varsayılan sağlayıcı olarak koleksiyon sınıfları tarafından belirtilen [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), ve [CRBTree](../../atl/reference/crbtree-class.md).

Varsayılan uygulamaları basit veri türleri için yeterli olacaktır, ancak daha karmaşık nesneleri depolamak için kullanılan koleksiyon sınıfları, yöntemleri ve işlevleri kullanıcı tarafından sağlanan uygulamaları tarafından geçersiz kılınmalıdır.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

## <a name="see-also"></a>Ayrıca bkz.

[CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
