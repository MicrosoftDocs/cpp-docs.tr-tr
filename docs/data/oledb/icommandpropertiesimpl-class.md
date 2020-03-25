---
title: ICommandPropertiesImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
ms.openlocfilehash: cbf2e6d7241d019a00132c10638993d60d78beac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210814"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl Sınıfı

[Iomtionproperties](/previous-versions/windows/desktop/ms723044(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ICommandPropertiesImpl
   : public ICommandProperties, public CUtlProps<PropClass>
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfından türetilmiş

*PropClass*<br/>
Özellikler sınıfınız.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetProperties](#getproperties)|Satır kümesi için şu anda istenen satır kümesi özellik grubundaki özelliklerin listesini döndürür.|
|[SetProperties](#setproperties)|Satır kümesi özellik grubundaki özellikleri ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu, komutlarda zorunludur. Uygulama, [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) makrosu tarafından tanımlanan statik bir işlev tarafından sağlanır.

## <a name="icommandpropertiesimplgetproperties"></a><a name="getproperties"></a>ICommandPropertiesImpl:: GetProperties

Komutun Özellik eşlemesini kullanarak istenen tüm özellik kümelerini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ICommandText:: GetProperties](/previous-versions/windows/desktop/ms723119(v=vs.85)) bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

## <a name="icommandpropertiesimplsetproperties"></a><a name="setproperties"></a>ICommandPropertiesImpl:: SetProperties

Komut nesnesi için özellikleri ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ICommandText:: SetProperties](/previous-versions/windows/desktop/ms711497(v=vs.85)) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
