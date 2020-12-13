---
description: 'Daha fazla bilgi edinin: CAutoPtrArray sınıfı'
title: CAutoPtrArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: 55f9382c82a1e242342d0d740c369a571c43f9ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152586"
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray sınıfı

Bu sınıf, akıllı işaretçiler dizisi oluştururken yararlı yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

### <a name="parameters"></a>Parametreler

*E*<br/>
İşaretçi türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAutoPtrArray:: CAutoPtrArray](#cautoptrarray)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir oluşturucu sağlar ve akıllı işaretçiler depolayan bir koleksiyon sınıfı nesnesinin oluşturulmasına yardımcı olmak için [CAtlArray](../../atl/reference/catlarray-class.md) ve [Cautoptrelementnitelikleri](../../atl/reference/cautoptrelementtraits-class.md) ' nden türetilmiş yöntemler sunar.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cautoptrarraycautoptrarray"></a><a name="cautoptrarray"></a> CAutoPtrArray:: CAutoPtrArray

Oluşturucu.

```cpp
CAutoPtrArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Akıllı işaretçi dizisini başlatır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlArray sınıfı](../../atl/reference/catlarray-class.md)<br/>
[Cautoptrelementnitelikler sınıfı](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[CAutoPtrList sınıfı](../../atl/reference/cautoptrlist-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
