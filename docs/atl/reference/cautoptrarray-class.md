---
title: CAutoPtrArray Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: 93fc5cfea4ea655e57e785ca234df59fe10d6570
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318890"
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray Sınıfı

Bu sınıf, bir dizi akıllı işaretçi yaparken yararlı yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Parametreler

*E*<br/>
İşaretçi türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf bir oluşturucu sağlar ve akıllı işaretçileri depolayan bir koleksiyon sınıfı nesnesi oluşturulmasına yardımcı olmak için [CAtlArray](../../atl/reference/catlarray-class.md) ve [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) yöntemleri türetilmiştir.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cautoptrarraycautoptrarray"></a><a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray

Oluşturucu.

```
CAutoPtrArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Akıllı işaretçi dizisini başharfe alır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlArray Sınıfı](../../atl/reference/catlarray-class.md)<br/>
[CAutoPtrElementTraits Sınıfı](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[CAutoPtrList Sınıfı](../../atl/reference/cautoptrlist-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
