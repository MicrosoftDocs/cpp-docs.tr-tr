---
description: Daha fazla bilgi için bkz. IRowsetNotifyCP sınıfı
title: IRowsetNotifyCP Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- IRowsetNotifyCP class
- Fire_OnFieldChange method
- Fire_OnRowChange method
- Fire_OnRowsetChange method
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
ms.openlocfilehash: 70e759ed19c366f7e85511170439c24f319c5cd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317278"
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP Sınıfı

Bağlantı noktası arabirimi [ırowsetnotıfy](/previous-versions/windows/desktop/ms712959(v=vs.85))için sağlayıcı sitesini uygular.

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
Sınıfından türetilmiş bir sınıf `IRowsetNotifyCP` .

*Reentrance Teventsync*<br/>
Yeniden girişi destekleyen bir mutex sınıfı (varsayılan değer `CComSharedMutex` ). Mutex, bir iş parçacığının bir kaynağa karşılıklı olarak erişilmesini sağlayan bir eşitleme nesnesidir.

*piıd*<br/>
`IID*`Bağlantı noktası arabirimi için ARABIRIM kimlik işaretçisi () `IRowsetNotify` . `&__uuidof(IRowsetNotify)` varsayılan değerdir.

*DynamicUnkArray*<br/>
İstemci havuzu arabirimlerine yönelik bir dizi işaretçilerin dinamik olarak ayrılmış dizisi olan [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)türünde bir dizi `IUnknown` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[Fire_OnFieldChange](#onfieldchange)|Bir sütunun değerinde bir değişikliğin tüketicisini bilgilendirir.|
|[Fire_OnRowChange](#onrowchange)|Tüketiciye, satırları etkileyen bir değişiklik olduğunu bildirir.|
|[Fire_OnRowsetChange](#onrowsetchange)|Tüketiciye tüm satır kümesini etkileyen bir değişiklik olduğunu bildirir.|

## <a name="remarks"></a>Açıklamalar

`IRowsetNotifyCP``IID_IRowsetNotify`, satır kümesinin içeriğinde yapılan değişikliklerin bağlantı noktasındaki dinleyicileri bildirmek için yayın işlevlerini uygular.

`IRowsetNotify`Tüketicinin bildirimleri işleyebilmesi için, [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) kullanarak tüketiciyi ("havuz" olarak da bilinir) da uygulamanız ve kaydettirmeniz gerektiğini unutmayın. Bkz. tüketici üzerinde bağlantı noktası arabirimini uygulamayla ilgili [Bildirimler alma](../../data/oledb/receiving-notifications.md) .

Bildirimleri uygulamayla ilgili ayrıntılı bilgi için, [güncelleştirilebilir bir sağlayıcı oluşturma](../../data/oledb/creating-an-updatable-provider.md)konusunda "bildirimleri destekleme" bölümüne bakın.

## <a name="irowsetnotifycpfire_onfieldchange"></a><a name="onfieldchange"></a> IRowsetNotifyCP:: Fire_OnFieldChange

Bir sütunun değerindeki bir değişikliğin tüketicilerini bilgilendirmek için [OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) olayını yayınlar.

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

*OLE DB Programcı başvurusunda* [IRowsetNotify:: OnFieldChange öğesine](/previous-versions/windows/desktop/ms715961(v=vs.85)) bakın.

## <a name="irowsetnotifycpfire_onrowchange"></a><a name="onrowchange"></a> IRowsetNotifyCP:: Fire_OnRowChange

, Satırları etkileyen bir değişikliği tüketicilere bildirmek için bağlantı noktasındaki tüm dinleyicilerle [OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) olayını yayınlar `IID_IRowsetNotify` .

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

*OLE DB Programcı başvurusunda* [IRowsetNotify:: OnRowChange öğesine](/previous-versions/windows/desktop/ms722694(v=vs.85)) bakın.

## <a name="irowsetnotifycpfire_onrowsetchange"></a><a name="onrowsetchange"></a> IRowsetNotifyCP:: Fire_OnRowsetChange

Tüm satır kümesini etkileyen bir değişikliği tüketicilere bildirmek için bağlantı noktasındaki tüm dinleyicilerle [OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) olayını yayınlar `IID_IRowsetNotify` .

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IRowsetNotify:: OnRowsetChange öğesine](/previous-versions/windows/desktop/ms722669(v=vs.85)) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Bildirimler (COM)](/windows/win32/com/notifications)<br/>
[BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)<br/>
[END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)<br/>
[CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)<br/>
[Güncelleştirilebilir sağlayıcı oluşturma](../../data/oledb/creating-an-updatable-provider.md)
