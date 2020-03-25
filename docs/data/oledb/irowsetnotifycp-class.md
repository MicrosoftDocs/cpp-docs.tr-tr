---
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
ms.openlocfilehash: fa85bc7947b3b446ec7c6d3fdb0d7b62d308fb53
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210333"
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

*Şı*<br/>
`IRowsetNotifyCP`türetilen bir sınıf.

*Reentrance Teventsync*<br/>
Yeniden girişi destekleyen bir mutex sınıfı (varsayılan değer `CComSharedMutex`). Mutex, bir iş parçacığının bir kaynağa karşılıklı olarak erişilmesini sağlayan bir eşitleme nesnesidir.

*piıd*<br/>
Bir `IRowsetNotify` bağlantı noktası arabirimi için arabirim KIMLIK işaretçisi (`IID*`). Varsayılan değer: `&__uuidof(IRowsetNotify)`.

*DynamicUnkArray*<br/>
İstemci havuzu arabirimlerine `IUnknown` işaretçilerin dinamik olarak ayrılmış dizisi olan [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)türünde bir dizi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Fire_OnFieldChange](#onfieldchange)|Bir sütunun değerinde bir değişikliğin tüketicisini bilgilendirir.|
|[Fire_OnRowChange](#onrowchange)|Tüketiciye, satırları etkileyen bir değişiklik olduğunu bildirir.|
|[Fire_OnRowsetChange](#onrowsetchange)|Tüketiciye tüm satır kümesini etkileyen bir değişiklik olduğunu bildirir.|

## <a name="remarks"></a>Açıklamalar

`IRowsetNotifyCP`, bağlantı noktasındaki dinleyicileri, satır kümesinin içeriklerindeki değişikliklere `IID_IRowsetNotify` için yayın işlevleri uygular.

Tüketicinin bildirimleri işleyebilmesi için, [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) kullanarak tüketicide ("havuz" olarak da bilinir) `IRowsetNotify` Ayrıca uygulamanız ve kaydetmeniz gerektiğini unutmayın. Bkz. tüketici üzerinde bağlantı noktası arabirimini uygulamayla ilgili [Bildirimler alma](../../data/oledb/receiving-notifications.md) .

Bildirimleri uygulamayla ilgili ayrıntılı bilgi için, [güncelleştirilebilir bir sağlayıcı oluşturma](../../data/oledb/creating-an-updatable-provider.md)konusunda "bildirimleri destekleme" bölümüne bakın.

## <a name="irowsetnotifycpfire_onfieldchange"></a><a name="onfieldchange"></a>IRowsetNotifyCP:: Fire_OnFieldChange

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

## <a name="irowsetnotifycpfire_onrowchange"></a><a name="onrowchange"></a>IRowsetNotifyCP:: Fire_OnRowChange

Satırları etkileyen bir değişikliğin tüketicilerini bilgilendirmek için `IID_IRowsetNotify` bağlantı noktasındaki tüm dinleyicilerine [OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) olayını yayınlar.

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

## <a name="irowsetnotifycpfire_onrowsetchange"></a><a name="onrowsetchange"></a>IRowsetNotifyCP:: Fire_OnRowsetChange

Tüm satır kümesini etkileyen bir değişikliğin tüketicilerini bilgilendirmek için `IID_IRowsetNotify` bağlantı noktasındaki tüm dinleyicilerine bir [OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) olayı yayınlar.

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
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Bildirimler (COM)](/windows/win32/com/notifications)<br/>
[BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)<br/>
[END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)<br/>
[CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)<br/>
[Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)
