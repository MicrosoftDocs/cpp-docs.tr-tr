---
title: CHeapPtrElementTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b873a615e04bd92e08abb51a048f227f19fd9eec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057502"
---
# <a name="cheapptrelementtraits-class"></a>CHeapPtrElementTraits sınıfı

Bu sınıf, yığın işaretçileri koleksiyonları oluştururken yöntemleri statik işlevler ve tür tanımları yararlı sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<typename T, class Allocator = ATL::CCRTAllocator>
class CHeapPtrElementTraits : 
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyon sınıfı içinde depolanan nesne türü.

*Ayırıcı*<br/>
Bellek ayırma kullanmak için sınıf. Varsayılan değer [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.|
|[CHeapPtrElementTraits::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesneden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, yöntem, statik işlevler ve tür tanımları kuruluşlara yardımcı olmaktayız yığın işaretçileri içeren koleksiyon sınıfı nesnelerini oluşturulmasını sağlar. Sınıf `CHeapPtrList` türetildiği `CHeapPtrElementTraits`.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CHeapPtrElementTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="inargtype"></a>  CHeapPtrElementTraits::INARGTYPE

Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.

```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```

##  <a name="outargtype"></a>  CHeapPtrElementTraits::OUTARGTYPE

Koleksiyon sınıfı nesneden öğeleri almak için kullanılacak veri türü.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca Bkz.

[CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CComHeapPtr Sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
