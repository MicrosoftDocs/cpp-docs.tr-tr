---
title: ICommandPropertiesImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
ms.openlocfilehash: c6736eac040b2186ddb1b1dc1c5c3a5b6b957d20
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556159"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl Sınıfı

Bir uygulamasını sağlar [ICommandProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms723044(v=vs.85)) arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ICommandPropertiesImpl
   : public ICommandProperties, public CUtlProps<PropClass>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Türetilmiş sınıfınızın

*PropClass*<br/>
Özellikleri sınıfınıza.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetProperties](#getproperties)|Şu anda satır kümesi için istenen satır kümesi özelliği grubunda özelliklerinin listesini döndürür.|
|[SetProperties](#setproperties)|Satır kümesi özelliği grubunda özelliklerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu, komutları zorunludur. Uygulama tarafından tanımlanan statik işlev tarafından sağlanan [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) makrosu.

## <a name="getproperties"></a> Icommandpropertiesımpl::GetProperties

Komutun özellik eşlemesi kullanarak tüm istenen özellik kümeleri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Parametreler

Bkz: [ICommandProperties::GetProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms723119(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

## <a name="setproperties"></a> Icommandpropertiesımpl::SetProperties

Komut nesnesi için özelliklerini ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Parametreler

Bkz: [ICommandProperties::SetProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms711497(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)