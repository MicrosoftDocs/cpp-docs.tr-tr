---
title: CAutoPtrArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: c7a2a7e9592b120204582334f69e27e72cd7364f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677948"
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray sınıfı

Bu sınıf, bir akıllı işaretçiler dizisi oluştururken kullanışlı yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

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

|Ad|Açıklama|
|----------|-----------------|
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir oluşturucu sağlar ve türeyen yöntemlerinden [CAtlArray](../../atl/reference/catlarray-class.md) ve [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) akıllı işaretçiler depolama koleksiyon sınıf nesnesi oluşturmaya yardımcı olmak için.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="cautoptrarray"></a>  CAutoPtrArray::CAutoPtrArray

Oluşturucu.

```
CAutoPtrArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Akıllı işaretçi dizi başlatır.

## <a name="see-also"></a>Ayrıca Bkz.

[CAtlArray Sınıfı](../../atl/reference/catlarray-class.md)<br/>
[CAutoPtrElementTraits Sınıfı](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[CAutoPtrList Sınıfı](../../atl/reference/cautoptrlist-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
