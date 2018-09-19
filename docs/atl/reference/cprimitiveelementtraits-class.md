---
title: CPrimitiveElementTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa5f96b8937168126509025735d20fab7b35c2b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019205"
---
# <a name="cprimitiveelementtraits-class"></a>CPrimitiveElementTraits sınıfı

Bu sınıfın sağladığı yöntemlerle varsayılan ve işlevleri koleksiyon sınıfı için temel veri türlerini oluşur.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyon sınıf nesnesinde depolanan verinin türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.|
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesneden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, varsayılan statik işlevler ve taşıma, kopyalama, karşılaştırma ve basit veri türü öğeleri koleksiyonu sınıf nesnesinde depolanan karma işlevi için yöntemler sağlar.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CPrimitiveElementTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="inargtype"></a>  CPrimitiveElementTraits::INARGTYPE

Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.

```
typedef T INARGTYPE;
```

##  <a name="outargtype"></a>  CPrimitiveElementTraits::OUTARGTYPE

Koleksiyon sınıfı nesneden öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca Bkz.

[CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
