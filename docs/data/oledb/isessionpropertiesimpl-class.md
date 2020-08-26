---
title: ISessionPropertiesImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- ISessionPropertiesImpl.SetProperties
- ISessionPropertiesImpl::SetProperties
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
ms.openlocfilehash: 57a94ccd8ee3871742e9c8360c56381f85053380
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844840"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl Sınıfı

[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ISessionPropertiesImpl :
   public ISessionProperties,
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `ISessionPropertiesImpl` .

*PropClass*<br/>
Varsayılan olarak *T*olarak kullanılacak kullanıcı tanımlı bir özellik sınıfı.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

| Ad | Açıklama |
|-|-|
|[GetProperties](#getproperties)|Oturumda ayarlanmış olan Session Özellik grubundaki özelliklerin listesini döndürür.|
|[SetProperties](#setproperties)|Oturum özellik grubundaki özellikleri ayarlar.|

## <a name="remarks"></a>Açıklamalar

Oturumlardaki zorunlu arabirim. Bu sınıf, [özellik kümesi eşlemesi](../../data/oledb/begin-propset-map.md)tarafından tanımlanan statik bir işlevi çağırarak oturum özelliklerini uygular. Özellik kümesi eşlemesi, oturum sınıfınıza belirtilmelidir.

## <a name="isessionpropertiesimplgetproperties"></a><a name="getproperties"></a> ISessionPropertiesImpl:: GetProperties

`DBPROPSET_SESSION`Oturumda ayarlanmış olan özellik grubundaki özelliklerin listesini döndürür.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ISessionProperties:: GetProperties](/previous-versions/windows/desktop/ms723643(v=vs.85)) bölümüne bakın.

## <a name="isessionpropertiesimplsetproperties"></a><a name="setproperties"></a> ISessionPropertiesImpl:: SetProperties

Özellik grubundaki özellikleri ayarlar `DBPROPSET_SESSION` .

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ISessionProperties:: SetProperties](/previous-versions/windows/desktop/ms714405(v=vs.85)) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
