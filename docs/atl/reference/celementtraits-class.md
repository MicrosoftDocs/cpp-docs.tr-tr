---
description: 'Daha fazla bilgi edinin: Celementnitelikler sınıfı'
title: Celementnitelikler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 1bcb6c9da2bca733efe68b634eebd7f379ba0d10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141810"
---
# <a name="celementtraits-class"></a>Celementnitelikler sınıfı

Bu sınıf, taşıma, kopyalama, karşılaştırma ve karma işlemleri için yöntemler ve işlevler sağlamak üzere koleksiyon sınıfları tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir koleksiyon sınıfı nesnesinde depolanan öğeleri taşımak, kopyalamak, karşılaştırmak ve karma yapmak için varsayılan statik işlevleri ve yöntemleri sağlar. `CElementTraits` , [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md)ve [CRBTree](../../atl/reference/crbtree-class.md)koleksiyon sınıfları tarafından bu işlemlerin varsayılan sağlayıcısı olarak belirtilir.

Varsayılan uygulamalar basit veri türleri için yeterli olacaktır, ancak koleksiyon sınıfları daha karmaşık nesneleri depolamak için kullanılıyorsa, işlevler ve Yöntemler Kullanıcı tarafından sağlanan uygulamalar tarafından geçersiz kılınmalıdır.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[Cdefaultelementnitelikler sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
