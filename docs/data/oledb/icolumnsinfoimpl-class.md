---
title: Icolumnsınfoımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
- GetColumnInfo
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
dev_langs:
- C++
helpviewer_keywords:
- IColumnsInfoImpl class
- GetColumnInfo method
- MapColumnIDs method
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bde6a3947d7afa836d93387e80c9b7885b1bc15c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099414"
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl Sınıfı

Bir uygulamasını sağlar [IColumnsInfo](/previous-versions/windows/desktop/ms724541\(v=vs.85\)) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
### <a name="parameters"></a>Parametreler  

*T*<br/>
Sınıfınız, türetilen `IColumnsInfoImpl`.  

## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetColumnInfo](#getcolumninfo)|Çoğu tüketiciler tarafından gerekli sütun meta verileri döndürür.|  
|[Mapcolumnıds](#mapcolumnids)|Belirtilen sütun kimlikleri tarafından tanımlanan bir satır kümesindeki sütunların sıra sayıları dizisini döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  

Satır kümeleri ve komutları zorunlu bir arabirim. Sağlayıcınızın davranışını değiştirmek için `IColumnsInfo` uygulama, sağlayıcı sütun eşlemesini değiştirmek için ihtiyacınız.  

## <a name="getcolumninfo"></a> Icolumnsınfoımpl::GetColumnInfo

Çoğu tüketiciler tarafından gerekli sütun meta verileri döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD (GetColumnInfo)(DBORDINAL* pcColumns,  
   DBCOLUMNINFO** prgInfo,  
   OLECHAR** ppStringsBuffer);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  

## <a name="mapcolumnids"></a> Icolumnsınfoımpl::mapcolumnıds

Belirtilen sütun kimlikleri tarafından tanımlanan bir satır kümesindeki sütunların sıra sayıları dizisini döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD (MapColumnIDs)(DBORDINAL cColumnIDs,  
   const DBID rgColumnIDs[],  
   DBORDINAL rgColumns[]);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IColumnsInfo::MapColumnIDs](/previous-versions/windows/desktop/ms714200\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)