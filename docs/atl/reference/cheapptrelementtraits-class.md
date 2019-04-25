---
title: CHeapPtrElementTraits sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
ms.openlocfilehash: e535afb3a49a5720c8394cc1ab9186c360527fea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258929"
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

## <a name="see-also"></a>Ayrıca bkz.

[CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CComHeapPtr Sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
