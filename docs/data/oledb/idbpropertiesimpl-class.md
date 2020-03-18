---
title: IDBPropertiesImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
- IDBPropertiesImpl.SetProperties
- IDBPropertiesImpl::SetProperties
helpviewer_keywords:
- IDBPropertiesImpl class
- GetProperties method
- GetPropertyInfo method
- SetProperties method
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
ms.openlocfilehash: 77f70c8b0bc602da6840bec38565c4441644c6d0
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443713"
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl Sınıfı

`IDBProperties` arabirimi için bir uygulama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE IDBPropertiesImpl
   : public IDBProperties, public CUtlProps<T>
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `IDBPropertiesImpl`türetilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetProperties](#getproperties)|Veri kaynağı nesnesinde ayarlanmış olan özelliklerin değerlerini, veri kaynağı bilgilerini ve şu anda şu anda ayarlanmış olan başlangıç özelliği grubundaki özelliklerin değerlerini döndürür. sının.|
|[GetPropertyInfo](#getpropertyinfo)|Sağlayıcı tarafından desteklenen tüm özelliklerle ilgili bilgileri döndürür.|
|[SetProperties](#setproperties)|Numaralandırıcı için veri kaynağı ve başlatma özelliği gruplarındaki, veri kaynağı nesneleri veya başlatma özelliği grubu özelliklerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

[IDBProperties](/previous-versions/windows/desktop/ms719607(v=vs.85)) , veri kaynağı nesneleri için zorunlu bir arabirimdir ve Numaralandırıcılar için isteğe bağlı bir arabirim. Ancak, bir Numaralandırıcı bir sayacı ortaya [alıyorsa, `IDBProperties`](/previous-versions/windows/desktop/ms713706(v=vs.85))kullanıma sunmalıdır. `IDBPropertiesImpl`, [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)tarafından tanımlanan statik işlevi kullanarak `IDBProperties` uygular.

## <a name="getproperties"></a>IDBPropertiesImpl:: GetProperties

Veri kaynağı nesnesinde ayarlanmış olan özelliklerin değerlerini, veri kaynağı bilgilerini ve şu anda şu anda ayarlanmış olan başlangıç özelliği grubundaki özelliklerin değerlerini döndürür. sının.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetProperties)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcProperties,
   DBPROPSET ** prgProperties);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IDBProperties:: GetProperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) bölümüne bakın.

Bazı parametreler, `IDBProperties::GetProperties`açıklanan farklı adların *OLE DB Programcı Başvuru* parametrelerine karşılık gelir:

|OLE DB şablon parametreleri|*OLE DB Programcı Başvuru* parametreleri|
|--------------------------------|------------------------------------------------|
|*cPropertySets 'ler*|*CPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|
|*pcProperties*|*pcPropertySets*|
|*prgProperties*|*prgPropertySets*|

### <a name="remarks"></a>Açıklamalar

Sağlayıcı başlatılmışsa, bu yöntem, veri kaynağı nesnesinde ayarlanmış olan DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO DBPROPSET_DBINIT Özellik gruplarındaki özelliklerin değerlerini döndürür. Sağlayıcı başlatılmamışsa, yalnızca DBPROPSET_DBINIT grubu özellikleri döndürür.

## <a name="getpropertyinfo"></a>IDBPropertiesImpl:: GetPropertyInfo

Veri kaynağı tarafından desteklenen özellik bilgilerini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcPropertyInfoSets,
   DBPROPINFOSET ** prgPropertyInfoSets,
   OLECHAR ** ppDescBuffer);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IDBProperties:: GetPropertyInfo](/previous-versions/windows/desktop/ms718175(v=vs.85)) bölümüne bakın.

Bazı parametreler, `IDBProperties::GetPropertyInfo`açıklanan farklı adların *OLE DB Programcı Başvuru* parametrelerine karşılık gelir:

|OLE DB şablon parametreleri|*OLE DB Programcı Başvuru* parametreleri|
|--------------------------------|------------------------------------------------|
|*cPropertySets 'ler*|*CPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|

### <a name="remarks"></a>Açıklamalar

Bu işlevselliği uygulamak için [IDBInitializeImpl:: m_pCUtlPropInfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) kullanır.

## <a name="setproperties"></a>IDBPropertiesImpl:: SetProperties

Numaralandırıcı için veri kaynağı ve başlatma özelliği gruplarındaki, veri kaynağı nesneleri veya başlatma özelliği grubu özelliklerini ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IDBProperties:: SetProperties](/previous-versions/windows/desktop/ms723049(v=vs.85)) bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Sağlayıcı başlatılmışsa, bu yöntem veri kaynağı nesnesi için DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO DBPROPSET_DBINIT Özellik gruplarındaki özelliklerin değerlerini ayarlar. Sağlayıcı başlatılmamışsa, yalnızca DBPROPSET_DBINIT grubu özelliklerini ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)