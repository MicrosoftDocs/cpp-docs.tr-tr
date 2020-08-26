---
title: IColumnsInfoImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl::GetColumnInfo
- ATL.IColumnsInfoImpl.GetColumnInfo
- ATL::IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl::GetColumnInfo
- IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl.GetColumnInfo
- IColumnsInfoImpl<T>::MapColumnIDs
- MapColumnIDs
- ATL::IColumnsInfoImpl::MapColumnIDs
- IColumnsInfoImpl.MapColumnIDs
- ATL::IColumnsInfoImpl<T>::MapColumnIDs
- IColumnsInfoImpl::MapColumnIDs
- ATL.IColumnsInfoImpl<T>.MapColumnIDs
- ATL.IColumnsInfoImpl.MapColumnIDs
helpviewer_keywords:
- IColumnsInfoImpl class
- GetColumnInfo method
- MapColumnIDs method
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
ms.openlocfilehash: 05e902e09c51012bd456751fb701ce2508a2fc16
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845607"
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl Sınıfı

[IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T>
class ATL_NO_VTABLE IColumnsInfoImpl :
   public IColumnsInfo,
   public CDBIDOps
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IColumnsInfoImpl` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[GetColumnInfo](#getcolumninfo)|Çoğu tüketiciden gereken sütun meta verilerini döndürür.|
|[MapColumnIDs](#mapcolumnids)|Belirtilen sütun kimlikleri tarafından tanımlanan bir satır kümesindeki sütunların sıra sayılarını dizisini döndürür.|

## <a name="remarks"></a>Açıklamalar

Satır kümelerinde ve komutlarda zorunlu arabirim. Sağlayıcınızın uygulamasının davranışını değiştirmek için `IColumnsInfo` sağlayıcı sütun haritasını değiştirmeniz gerekir.

## <a name="icolumnsinfoimplgetcolumninfo"></a><a name="getcolumninfo"></a> IColumnsInfoImpl:: GetColumnInfo

Çoğu tüketiciden gereken sütun meta verilerini döndürür.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD (GetColumnInfo)(DBORDINAL* pcColumns,
   DBCOLUMNINFO** prgInfo,
   OLECHAR** ppStringsBuffer);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) bölümüne bakın.

## <a name="icolumnsinfoimplmapcolumnids"></a><a name="mapcolumnids"></a> IColumnsInfoImpl:: MapColumnIDs

Belirtilen sütun kimlikleri tarafından tanımlanan bir satır kümesindeki sütunların sıra sayılarını dizisini döndürür.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD (MapColumnIDs)(DBORDINAL cColumnIDs,
   const DBID rgColumnIDs[],
   DBORDINAL rgColumns[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IColumnsInfo:: MapColumnIDs](/previous-versions/windows/desktop/ms714200(v=vs.85)) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
