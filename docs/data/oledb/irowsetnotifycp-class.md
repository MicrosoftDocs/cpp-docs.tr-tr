---
title: "IRowsetNotifyCP sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRowsetNotifyCP
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyCP class
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a43825ee3fa676ce07dcd3bc4e121abd400ef322
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP Sınıfı
Sağlayıcı site bağlantı noktası arabirimi uygulayan [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class ReentrantEventSync = CComSharedMutex>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray>,  
   public ReentrantEventSync  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğesinden türetilmiş bir sınıf `IRowsetNotifyCP`.  
  
 `ReentrantEventSync`  
 Yeniden giriş destekleyen bir mutex sınıfı (varsayılan **CComSharedMutex**). Bir mutex bir iş parçacığı birbirini dışlayan bir kaynağa erişim izni veren bir eşitleme nesnesidir.  
  
 `piid`  
 Arabirim kimliği işaretçisi (**IID\***) için bir **IRowsetNotify** bağlantı noktası arabirimi. Varsayılan değer **& __uuidof(IRowsetNotify)**.  
  
 `DynamicUnkArray`  
 Türünde bir dizi [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), dinamik olarak ayrılan bir dizi olduğu **IUnknown** istemci işaretçiler havuzu arabirimleri.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Fire_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|Bir sütunun değeri bir değişiklik tüketici bildirir.|  
|[Fire_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|Satırları etkileyen bir değişiklik tüketici bildirir.|  
|[Fire_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|Tüm satır etkileyen bir değişiklik tüketici bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IRowsetNotifyCP` Implements yayın dinleyicileri bağlantı noktasında bildirmek amacıyla işlevleri **IID_IRowsetNotify** satır içeriğini değişiklikler.  
  
 Ayrıca uygulama ve kaydetmeniz gerekir unutmayın `IRowsetNotify` kullanarak tüketici (olarak da bilinen "havuz") üzerinde [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) böylece tüketici bildirimleri işleyebilir. Bkz: [bildirimleri alma](../../data/oledb/receiving-notifications.md) tüketici üzerinde bağlantı noktası arabirimi uygulama hakkında.  
  
 Bildirimleri uygulama konusunda ayrıntılı bilgi için bkz: "Bildirimleri destekleme" [güncelleştirilebilir sağlayıcı oluşturma](../../data/oledb/creating-an-updatable-provider.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Bildirimleri (COM)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)   
 [END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)   
 [CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)   
 [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)