---
title: Irowsetınfoımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
- ATL.IRowsetInfoImpl.GetProperties
- IRowsetInfoImpl.GetProperties
- ATL::IRowsetInfoImpl::GetProperties
- IRowsetInfoImpl::GetProperties
- GetProperties
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
dev_langs:
- C++
helpviewer_keywords:
- IRowsetInfoImpl class
- GetProperties method
- GetReferencedRowset method
- GetSpecification method
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac05cdb93ff87e40c41a59ce466d81aa7bcb5e92
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053480"
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl Sınıfı

Bir uygulamasını sağlar [IRowsetInfo](/previous-versions/windows/desktop/ms724541) arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE IRowsetInfoImpl :
   public IRowsetInfo,  
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IRowsetInfoImpl`.

*PropClass*<br/>
Varsayılan olarak bir kullanıcı tarafından tanımlanabilen özellik sınıfı *T*.

## <a name="requirements"></a>Gereksinimler

**Başlık:** altdb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetProperties](#getproperties)|Geçerli ayarları kümesi tarafından desteklenen tüm özellikleri döndürür.|
|[GetReferencedRowset](#getreferencedrowset)|Bir yer işareti uygulandığı satır kümesi için bir arabirim işaretçisini döndürür.|
|[GetSpecification](#getspecification)|Bu satır kümesini oluşturan nesnede (komut veya oturumu) bir arabirim işaretçisini döndürür.|

## <a name="remarks"></a>Açıklamalar

Satır kümeleri üzerinde zorunlu bir arabirim. Kullanarak satır kümesi özelliklerini bu sınıfın uyguladığı [özellik kümesi eşlemesini](../../data/oledb/begin-propset-map.md) komut Sınıfınız içinde tanımlanan. Satır kümesi sınıfı komut sınıf özelliği kullanılmasını ayarlar görünse de, bir komut veya oturum nesnesi oluşturulduğunda satır kümesi kendi çalışma zamanı özellikleri kopyası ile sağlanır.

## <a name="getproperties"></a> Irowsetınfoımpl::GetProperties

Özellikler için geçerli ayarları döndürür `DBPROPSET_ROWSET` grubu.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetProperties )(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG* pcPropertySets,
   DBPROPSET** prgPropertySets);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowsetInfo::GetProperties](/previous-versions/windows/desktop/ms719611) içinde *OLE DB Programcının Başvurusu*.

## <a name="getreferencedrowset"></a> Irowsetınfoımpl::getreferencedrowset

Bir yer işareti uygulandığı satır kümesi için bir arabirim işaretçisini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetReferencedRowset )(DBORDINAL iOrdinal,
   REFIID riid,
   IUnknown** ppReferencedRowset);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowsetInfo::GetReferencedRowset](/previous-versions/windows/desktop/ms721145) içinde *OLE DB Programcının Başvurusu*. *İOrdinal* parametresi, bir yer işareti sütunu olmalıdır.

## <a name="getspecification"></a> Irowsetınfoımpl::getspecification

Bu satır kümesini oluşturan nesnede (komut veya oturumu) bir arabirim işaretçisini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetSpecification )(REFIID riid,
   IUnknown** ppSpecification);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowsetInfo::GetSpecification](/previous-versions/windows/desktop/ms716746) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi kullanmak [Igetdatasourceımpl](../../data/oledb/igetdatasourceimpl-class.md) veri kaynağı nesnesinden özellikleri alınamadı.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)