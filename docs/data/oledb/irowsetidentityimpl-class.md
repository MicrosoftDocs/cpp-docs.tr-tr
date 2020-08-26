---
title: IRowsetIdentityImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
ms.openlocfilehash: 48ed687ff67208109b5a2acf400d98491b4c769a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836149"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl Sınıfı

Satır kimliği için test sağlayan OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85)) arabirimini uygular.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T, class RowClass = CSimpleRow>
class ATL_NO_VTABLE IRowsetIdentityImpl
   : public IRowsetIdentity
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfından türetilmiş bir sınıf `IRowsetIdentityImpl` .

*RowClass*<br/>
İçin depolama birimi `HROW` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[IsSameRow](#issamerow)|Aynı satıra başvurduklarında, bunları görmek için iki satır tutamaçlarını karşılaştırır.|

## <a name="irowsetidentityimplissamerow"></a><a name="issamerow"></a> IRowsetIdentityImpl:: IsSameRow

Aynı satıra başvurduklarında, bunları görmek için iki satır tutamaçlarını karşılaştırır.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IRowsetIdentity:: IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) ' a bakın.

### <a name="remarks"></a>Açıklamalar

Satır tutamaçlarını karşılaştırmak için, bu yöntem `HROW` tutamaçları `RowClass` işaretçilerin üyelerine ve çağrılarına yayınlar `memcmp` .

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
