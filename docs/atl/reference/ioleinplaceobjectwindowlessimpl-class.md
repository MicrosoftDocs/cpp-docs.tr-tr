---
title: IOleInPlaceObjectWindowlessImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
ms.openlocfilehash: b0438692161f38445eb7cbed54edcc8a0ba8c0d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326573"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl Sınıfı

Bu sınıf, `IUnknown` pencere iletileri almak ve sürükle ve bırak işlemlerine katılmak için penceresiz bir denetim sağlayan yöntemler uygular ve sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IOleInPlaceObjectWindowlessImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|İçeriğe duyarlı yardımı sağlar. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Sürükle `IDropTarget` ve bırak'ı destekleyen yerinde etkin, penceresiz bir nesne için arabirimi sağlar. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Pencere kolu alır.|
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Etkin bir yerinde denetimi devre dışı bırakır.|
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Kapsayıcıdan etkin olan penceresiz denetime bir ileti gönderir.|
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Daha önce devre dışı bırakılmış bir denetimi yeniden etkinleştirir. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Yerinde denetimin hangi bölümünün görünür olduğunu gösterir.|
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Yerinde etkinleştirme destekleyen kullanıcı arabirimini devre dışı bırakır ve kaldırır.|

## <a name="remarks"></a>Açıklamalar

[IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) arabirimi yerinde denetimlerin yeniden etkinleştirilmesi ve devre dışı bırakılmasını yönetir ve denetimin ne kadarının görünür olması gerektiğini belirler. [IOleInPlaceObjectWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) arabirimi pencere iletileri almak ve sürükle-bırak işlemlerine katılmak için penceresiz bir denetim sağlar. Sınıf `IOleInPlaceObjectWindowlessImpl` varsayılan bir `IOleInPlaceObject` uygulama `IOleInPlaceObjectWindowless` sağlar `IUnknown` ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="ioleinplaceobjectwindowlessimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp

E_NOTIMPL döndürür.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleWindow::ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) windows SDK içinde.

## <a name="ioleinplaceobjectwindowlessimplgetdroptarget"></a><a name="getdroptarget"></a>IOleInPlaceObjectWindowlessImpl::GetDropTarget

E_NOTIMPL döndürür.

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleInPlaceObjectWindowless::GetDropTarget](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget) windows SDK içinde.

## <a name="ioleinplaceobjectwindowlessimplgetwindow"></a><a name="getwindow"></a>IOleInPlaceObjectWindowlessImpl::GetWindow

Kapsayıcı, denetimin pencere tutamacını almak için bu işlevi çağırır.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Açıklamalar

Bazı kapsayıcılar, şu anda pencereli olsa bile penceresiz olan bir denetimle çalışmaz. ATL'nin uygulamasında, denetim sınıfının veri `m_bWasOnceWindowless` üyesi TRUE ise, işlev E_FAIL döndürür. Aksi takdirde, *phwnd* NULL `GetWindow` \* değilse, *phwnd'yi* denetim `m_hWnd` sınıfının veri üyesine ayarlar ve S_OK döndürür.

Bkz. [IOleWindow::Windows](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) SDK'daki GetWindow.

## <a name="ioleinplaceobjectwindowlessimplinplacedeactivate"></a><a name="inplacedeactivate"></a>IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate

Yerinde etkin denetimi devre dışı bırakmak için kapsayıcı tarafından çağrılır.

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetimin durumuna bağlı olarak tam veya kısmi bir devre dışı bırakma gerçekleştirir. Gerekirse, denetimin kullanıcı arabirimi devre dışı bırakılır ve varsa denetimin penceresi yok edilir. Kapsayıcı, denetimin artık etkin olmadığı bildirilir. Menüler `IOleInPlaceUIWindow` ve kenarlık alanı müzakere kapsayıcı tarafından kullanılan arabirim serbest bırakılır.

Bkz. [IOleInPlaceObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) SDK'da InPlaceDeactivate.

## <a name="ioleinplaceobjectwindowlessimplonwindowmessage"></a><a name="onwindowmessage"></a>IOleInPlaceObjectWindowlessImpl::OnWindowMessage

Bir kapsayıcıdan yerinde etkin olan penceresiz denetime bir ileti gönderir.

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleInPlaceObjectWindowless::Windows](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage) SDK'da OnWindowMessage.

## <a name="ioleinplaceobjectwindowlessimplreactivateandundo"></a><a name="reactivateandundo"></a>IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo

E_NOTIMPL döndürür.

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleInPlaceObject::Windows SDK'da ReactivateAndUndo.](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo)

## <a name="ioleinplaceobjectwindowlessimplsetobjectrects"></a><a name="setobjectrects"></a>IOleInPlaceObjectWindowlessImpl::SetObjectRects

Denetimi boyutunun ve/veya konumunun değiştiğini bildirmek için kapsayıcı tarafından çağrılır.

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>Açıklamalar

Denetimin `m_rcPos` veri üyesini ve denetim ekranını güncelleştirir. Denetimin yalnızca klip bölgesiyle kesişen bölümü görüntülenir. Denetimin ekranı daha önce kırpılmış ancak kırpma kaldırılmışsa, denetimin tam görünümünü yeniden çizmek için bu işlev çağrılabilir.

Bkz. [IOleInPlaceObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) SDK'da Nesne Düzeltmeleri Ayarlayın.

## <a name="ioleinplaceobjectwindowlessimpluideactivate"></a><a name="uideactivate"></a>IOleInPlaceObjectWindowlessImpl::UIDeactivate

Denetimin yerinde etkinleştirmeyi destekleyen kullanıcı arabirimini devre dışı bırakır ve kaldırır.

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>Açıklamalar

Denetim sınıfının veri üyesini `m_bUIActive` FALSE olarak ayarlar. Bu işlevin ATL uygulaması her zaman S_OK döndürür.

Bkz. [IOleInPlaceObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate) SDK'da Etkinleştirilmesi.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
