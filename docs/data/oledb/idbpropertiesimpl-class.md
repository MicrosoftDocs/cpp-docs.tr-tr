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
- GetProperties
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
helpviewer_keywords:
- IDBPropertiesImpl class
- GetProperties method
- GetPropertyInfo method
- SetProperties method
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
ms.openlocfilehash: 2ce9f3fa18d2a17d499b65258cfda52783ce46c5
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556952"
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl Sınıfı

Bir uygulamasını sağlar `IDBProperties` arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE IDBPropertiesImpl
   : public IDBProperties, public CUtlProps<T>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IDBPropertiesImpl`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetProperties](#getproperties)|Veri kaynağı nesnesi veya başlatma özellik grubundaki üzerinde ayarlanmış olan özelliklerin değerlerini şu anda ayarlanmış veri kaynağı, veri kaynağı bilgilerini ve başlatma özelliği gruplarında özelliklerin değerlerini döndürür. Numaralandırıcı.|
|[GetPropertyInfo](#getpropertyinfo)|Sağlayıcı tarafından desteklenen tüm özellikleri hakkında bilgi döndürür.|
|[SetProperties](#setproperties)|Özellikleri veri kaynağı ve başlatma için veri kaynağı nesneleri, özellik gruplarını veya başlatma özelliği grubunda numaralandırıcılar için ayarlar.|

## <a name="remarks"></a>Açıklamalar

[IDBProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms719607(v=vs.85)) veri kaynağı nesneleri için zorunlu bir arabirim ve numaralandırıcılar için isteğe bağlı bir arabirim. Ancak, bir numaralandırıcı sunarsa [IDBInitialize](https://docs.microsoft.com/previous-versions/windows/desktop/ms713706(v=vs.85)), açığa çıkarmalıdır `IDBProperties`. `IDBPropertiesImpl` uygulayan `IDBProperties` tarafından tanımlanan statik bir işlevi kullanarak [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

## <a name="getproperties"></a> Idbpropertiesımpl::GetProperties

Veri kaynağı nesnesi veya başlatma özellik grubundaki üzerinde ayarlanmış olan özelliklerin değerlerini şu anda ayarlanmış veri kaynağı, veri kaynağı bilgilerini ve başlatma özelliği gruplarında özelliklerin değerlerini döndürür. Numaralandırıcı.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetProperties)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcProperties,
   DBPROPSET ** prgProperties);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IDBProperties::GetProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms714344(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

Bazı parametreler karşılık *OLE DB Programcının Başvurusu* açıklanan farklı adlar parametrelerinin `IDBProperties::GetProperties`:

|OLE DB Şablon parametreleri|*OLE DB Programcının Başvurusu* parametreleri|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*cPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|
|*pcProperties*|*pcPropertySets*|
|*prgProperties*|*prgPropertySets*|

### <a name="remarks"></a>Açıklamalar

Sağlayıcı başlatılır, bu yöntem DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO, özelliklerin değerlerini döndürür. şu anda veri kaynağı nesnesi üzerinde ayarlanan DBPROPSET_DBINIT özellik grupları. Sağlayıcı başlatılmamışsa, yalnızca DBPROPSET_DBINIT Grup Özellikleri döndürür.

## <a name="getpropertyinfo"></a> Idbpropertiesımpl::GetPropertyInfo

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

Bkz: [IDBProperties::GetPropertyInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms718175(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

Bazı parametreler karşılık *OLE DB Programcının Başvurusu* açıklanan farklı adlar parametrelerinin `IDBProperties::GetPropertyInfo`:

|OLE DB Şablon parametreleri|*OLE DB Programcının Başvurusu* parametreleri|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*cPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|

### <a name="remarks"></a>Açıklamalar

Kullanan [Idbınitializeımpl::m_pcutlpropınfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) bu işlevselliği uygulamak için.

## <a name="setproperties"></a> Idbpropertiesımpl::SetProperties

Özellikleri veri kaynağı ve başlatma için veri kaynağı nesneleri, özellik gruplarını veya başlatma özelliği grubunda numaralandırıcılar için ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IDBProperties::SetProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms723049(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Sağlayıcı başlatılır, bu yöntem DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO, özelliklerin değerlerini ayarlar DBPROPSET_DBINIT özellik grupları için veri kaynağı nesnesi. Sağlayıcı başlatılmamışsa, yalnızca DBPROPSET_DBINIT Grup özelliklerini ayarlar.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)