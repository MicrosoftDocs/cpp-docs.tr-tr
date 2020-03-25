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
ms.openlocfilehash: 0b36e4f85b855f162e11d96f8fef296c6c07597f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210307"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl Sınıfı

[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ISessionPropertiesImpl :
   public ISessionProperties,
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `ISessionPropertiesImpl`türetilir.

*PropClass*<br/>
Varsayılan olarak *T*olarak kullanılacak kullanıcı tanımlı bir özellik sınıfı.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetProperties](#getproperties)|Oturumda ayarlanmış olan Session Özellik grubundaki özelliklerin listesini döndürür.|
|[SetProperties](#setproperties)|Oturum özellik grubundaki özellikleri ayarlar.|

## <a name="remarks"></a>Açıklamalar

Oturumlardaki zorunlu arabirim. Bu sınıf, [özellik kümesi eşlemesi](../../data/oledb/begin-propset-map.md)tarafından tanımlanan statik bir işlevi çağırarak oturum özelliklerini uygular. Özellik kümesi eşlemesi, oturum sınıfınıza belirtilmelidir.

## <a name="isessionpropertiesimplgetproperties"></a><a name="getproperties"></a>ISessionPropertiesImpl:: GetProperties

Oturumda ayarlanmış olan `DBPROPSET_SESSION` özellik grubundaki özelliklerin listesini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ISessionProperties:: GetProperties](/previous-versions/windows/desktop/ms723643(v=vs.85)) bölümüne bakın.

## <a name="isessionpropertiesimplsetproperties"></a><a name="setproperties"></a>ISessionPropertiesImpl:: SetProperties

`DBPROPSET_SESSION` özellik grubundaki özellikleri ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ISessionProperties:: SetProperties](/previous-versions/windows/desktop/ms714405(v=vs.85)) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
