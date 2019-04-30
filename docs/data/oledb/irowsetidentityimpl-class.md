---
title: IRowsetIdentityImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IsSameRow
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
ms.openlocfilehash: 51f8d7e832476619ccec277c9d73791041d146a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390847"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl Sınıfı

OLE DB uygulayan [IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85)) satır kimliği için test sağlayan arabirim.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class RowClass = CSimpleRow>
class ATL_NO_VTABLE IRowsetIdentityImpl
   : public IRowsetIdentity
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Öğesinden türetilen bir sınıf `IRowsetIdentityImpl`.

*RowClass*<br/>
Depolama birimi için `HROW`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Issamerow](#issamerow)|Bunlar aynı satıra başvurmak için iki satır işleyicilerini karşılaştırır.|

## <a name="issamerow"></a> Irowsetıdentityımpl::ıssamerow

Bunlar aynı satıra başvurmak için iki satır işleyicilerini karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Satır işleyicilerini karşılaştırmak için bu yöntem bıraktığı `HROW` için işleme `RowClass` üyeleri ve çağrıları `memcmp` işaretçileri.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)