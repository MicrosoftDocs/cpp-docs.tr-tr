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
ms.openlocfilehash: 39aa3f5e89746d48057e0e8efe6fe62b1c2d8921
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210879"
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl Sınıfı

[IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE IColumnsInfoImpl :
   public IColumnsInfo,
   public CDBIDOps
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `IColumnsInfoImpl`türetilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|Çoğu tüketiciden gereken sütun meta verilerini döndürür.|
|[MapColumnIDs](#mapcolumnids)|Belirtilen sütun kimlikleri tarafından tanımlanan bir satır kümesindeki sütunların sıra sayılarını dizisini döndürür.|

## <a name="remarks"></a>Açıklamalar

Satır kümelerinde ve komutlarda zorunlu arabirim. Sağlayıcınızın `IColumnsInfo` uygulamasının davranışını değiştirmek için sağlayıcı sütun haritasını değiştirmeniz gerekir.

## <a name="icolumnsinfoimplgetcolumninfo"></a><a name="getcolumninfo"></a>IColumnsInfoImpl:: GetColumnInfo

Çoğu tüketiciden gereken sütun meta verilerini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetColumnInfo)(DBORDINAL* pcColumns,
   DBCOLUMNINFO** prgInfo,
   OLECHAR** ppStringsBuffer);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) bölümüne bakın.

## <a name="icolumnsinfoimplmapcolumnids"></a><a name="mapcolumnids"></a>IColumnsInfoImpl:: MapColumnIDs

Belirtilen sütun kimlikleri tarafından tanımlanan bir satır kümesindeki sütunların sıra sayılarını dizisini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (MapColumnIDs)(DBORDINAL cColumnIDs,
   const DBID rgColumnIDs[],
   DBORDINAL rgColumns[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IColumnsInfo:: MapColumnIDs](/previous-versions/windows/desktop/ms714200(v=vs.85)) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
