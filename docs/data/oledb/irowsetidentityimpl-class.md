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
ms.openlocfilehash: 3e8c976fcb23bf41d88d88be3887db4dde52379d
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446318"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl Sınıfı

Satır kimliği için test sağlayan OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85)) arabirimini uygular.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class RowClass = CSimpleRow>
class ATL_NO_VTABLE IRowsetIdentityImpl
   : public IRowsetIdentity
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
`IRowsetIdentityImpl`türetilen bir sınıf.

*RowClass*<br/>
`HROW`için depolama birimi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[IsSameRow](#issamerow)|Aynı satıra başvurduklarında, bunları görmek için iki satır tutamaçlarını karşılaştırır.|

## <a name="issamerow"></a>IRowsetIdentityImpl:: IsSameRow

Aynı satıra başvurduklarında, bunları görmek için iki satır tutamaçlarını karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IRowsetIdentity:: IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) ' a bakın.

### <a name="remarks"></a>Açıklamalar

Satır tutamaçlarını karşılaştırmak için, bu yöntem `HROW` tutamaçlarını `RowClass` üyelerine yayınlar ve işaretçiler üzerinde `memcmp` çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)