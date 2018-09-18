---
title: IRowsetNotifyCP sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetNotifyCP
- Fire_OnFieldChange
- ATL::IRowsetNotifyCP::Fire_OnFieldChange
- ATL.IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP::Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
- Fire_OnRowsetChange
- IRowsetNotifyCP::Fire_OnRowsetChange
- IRowsetNotifyCP.Fire_OnRowsetChange
- ATL::IRowsetNotifyCP::Fire_OnRowsetChange
- ATL.IRowsetNotifyCP.Fire_OnRowsetChange
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyCP class
- Fire_OnFieldChange method
- Fire_OnRowChange method
- Fire_OnRowsetChange method
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 15e00f27c5ad5d5312928bda8f73304a8417a6bc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071828"
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP Sınıfı

Sağlayıcı sitesi için bağlantı noktası arabirimi uygulayan [IRowsetNotify](/previous-versions/windows/desktop/ms712959\(v=vs.85\)).  
  
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
  
### <a name="parameters"></a>Parametreler  

*T*<br/>
Öğesinden türetilen bir sınıf `IRowsetNotifyCP`.  
  
*ReentrantEventSync*<br/>
Yeniden giriş destekleyen bir mutex sınıfı (varsayılan değer `CComSharedMutex`). Bir mutex bir iş parçacığı bir kaynağa karşılıklı olarak dışlama erişimine izin veren bir eşitleme nesnesi olan.  
  
*piid*<br/>
Bir arabirim kimliği işaretçisi (`IID*`) için bir `IRowsetNotify` bağlantı noktası arabirimi. Varsayılan değer `&__uuidof(IRowsetNotify)` şeklindedir.  
  
*DynamicUnkArray*<br/>
Türünde bir dizi [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), dinamik olarak ayrılan dizi olduğu `IUnknown` istemci işaretçileri havuz arabirimleri. 

## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldb.h   
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Fire_OnFieldChange](#onfieldchange)|Bir sütunun değerini değişiklik tüketicisinin bildirir.|  
|[Fire_OnRowChange](#onrowchange)|Satırları etkileyen bir değişiklik tüketicisinin bildirir.|  
|[Fire_OnRowsetChange](#onrowsetchange)|Tüm satır kümesini etkileyen bir değişiklik tüketicisinin bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  

`IRowsetNotifyCP` uygular bağlantı noktası üzerinde dinleyici bildirmek için işlevleri yayın `IID_IRowsetNotify` değişiklik kümesi içeriği.  
  
Ayrıca uygulama ve kaydetme gerekir unutmayın `IRowsetNotify` kullanarak tüketici (diğer adıyla "havuz") [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) tüketici bildirimleri işleyebilmeniz. Bkz: [bildirimleri alma](../../data/oledb/receiving-notifications.md) tüketici üzerinde bağlantı noktası arabirimini uygulayan hakkında.  
  
Bildirimleri uygulama ile ilgili ayrıntılı bilgi için bkz: "Destek bildirimleri" [güncelleştirilebilir sağlayıcı oluşturma](../../data/oledb/creating-an-updatable-provider.md).  

## <a name="onfieldchange"></a> IRowsetNotifyCP::fire_onfieldchange

Yayınlar bir [OnFieldChange](/previous-versions/windows/desktop/ms715961\(v=vs.85\)) olay tüketicileri bir sütun değerine değişikliği bildirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Fire_OnFieldChange(IRowset* pRowset,  
   HROW hRow,  
   DBORDINAL cColumns,  
   DBORDINAL* rgColumns,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*. 

## <a name="onrowchange"></a> IRowsetNotifyCP::fire_onrowchange

Yayınlar bir [OnRowChange](/previous-versions/windows/desktop/ms722694\(v=vs.85\)) tüm dinleyici bağlantı noktası üzerinde olaya `IID_IRowsetNotify` satırları etkileyen bir değişiklik tüketicilerinin bildirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Fire_OnRowChange(IRowset* pRowset,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  

## <a name="onrowsetchange"></a> IRowsetNotifyCP::fire_onrowsetchange

Yayınlar bir [OnRowsetChange](/previous-versions/windows/desktop/ms722669\(v=vs.85\)) tüm dinleyici bağlantı noktası üzerinde olaya `IID_IRowsetNotify` tüm satır kümesini etkileyen bir değişiklik tüketicilerinin bildirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Bildirimler (COM)](/windows/desktop/com/notifications)<br/>
[BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)<br/>
[END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)<br/>
[CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)<br/>
[Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)