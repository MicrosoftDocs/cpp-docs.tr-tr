---
description: 'Daha fazla bilgi edinin: ıoleınplaceobjectwindowlessıl sınıfı'
title: Ioleınplaceobjectwindowlessıl sınıfı
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
ms.openlocfilehash: 927a973565949bbfc6331e4b4e62d7cb270c2107
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139392"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>Ioleınplaceobjectwindowlessıl sınıfı

Bu sınıf `IUnknown` , bir penceresiz denetimin pencere iletilerini almasını ve sürükle ve bırak işlemlerine katılmasını sağlayan yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IOleInPlaceObjectWindowlessImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ioleınplaceobjectwindowlessıl:: ContextSensitiveHelp](#contextsensitivehelp)|Bağlama duyarlı yardımı etkinleştirilir. ATL uygulama E_NOTIMPL döndürür.|
|[Ioleınplaceobjectwindowlessıl:: GetDropTarget](#getdroptarget)|`IDropTarget`Sürükleyip bırakmayı destekleyen, yerinde etkin ve penceresiz bir nesne için arabirim sağlar. ATL uygulama E_NOTIMPL döndürür.|
|[Ioleınplaceobjectwindowlessıl:: GetWindow](#getwindow)|Bir pencere tutamacı alır.|
|[Ioleınplaceobjectwindowlessıl:: InPlaceDeactivate](#inplacedeactivate)|Etkin bir yerinde denetimi devre dışı bırakır.|
|[Ioleınplaceobjectwindowlessıl:: OnWindowMessage](#onwindowmessage)|Kapsayıcıdan, yerinde etkin olan penceresiz bir denetime ileti gönderir.|
|[Ioleınplaceobjectwindowlessıl:: ReactivateAndUndo](#reactivateandundo)|Önceden devre dışı bırakılmış bir denetimi yeniden etkinleştirir. ATL uygulama E_NOTIMPL döndürür.|
|[Ioleınplaceobjectwindowlessıl:: SetObjectRects](#setobjectrects)|Yerinde denetimin hangi bölümünün görünür olduğunu gösterir.|
|[Ioleınplaceobjectwindowlessıl:: UIDeactivate](#uideactivate)|Yerinde etkinleştirmeyi destekleyen Kullanıcı arabirimini devre dışı bırakır ve kaldırır.|

## <a name="remarks"></a>Açıklamalar

[IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) arabirimi, yerinde denetimlerin yeniden etkinleştirmeyi ve devre dışı bırakmayı yönetir ve denetimin ne kadarının görünür olacağını belirler. [Ioleınplaceobjectpenceresiz](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) arabirimi, penceresiz bir denetimin pencere iletilerini almasına ve sürükle ve bırak işlemlerine katılmasına olanak sağlar. Sınıfı, `IOleInPlaceObjectWindowlessImpl` ve ' nin varsayılan bir uygulamasını sağlar `IOleInPlaceObject` `IOleInPlaceObjectWindowless` ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="ioleinplaceobjectwindowlessimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a> Ioleınplaceobjectwindowlessıl:: ContextSensitiveHelp

E_NOTIMPL döndürür.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleWindow:: ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) .

## <a name="ioleinplaceobjectwindowlessimplgetdroptarget"></a><a name="getdroptarget"></a> Ioleınplaceobjectwindowlessıl:: GetDropTarget

E_NOTIMPL döndürür.

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [ıoleınplaceobjectpenceresiz:: GetDropTarget](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget) .

## <a name="ioleinplaceobjectwindowlessimplgetwindow"></a><a name="getwindow"></a> Ioleınplaceobjectwindowlessıl:: GetWindow

Kapsayıcı, denetimin pencere tanıtıcısını almak için bu işlevi çağırır.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Açıklamalar

Bazı kapsayıcılar, şu anda pencereli olsa bile, penceresiz olan bir denetimle çalışmayacaktır. ATL 'nin uygulamasında, denetim sınıfının veri üyesi `m_bWasOnceWindowless` true ise işlev E_FAIL döndürür. Aksi takdirde, *PHWND* null değilse, `GetWindow` \* Denetim sınıfının veri üyesine *phwnd* 'i ayarlar `m_hWnd` ve s_ok döndürür.

Windows SDK için bkz. [IOleWindow:: GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) .

## <a name="ioleinplaceobjectwindowlessimplinplacedeactivate"></a><a name="inplacedeactivate"></a> Ioleınplaceobjectwindowlessıl:: InPlaceDeactivate

Yerinde etkin bir denetimi devre dışı bırakmak için kapsayıcı tarafından çağırılır.

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetimin durumuna bağlı olarak tam veya kısmi devre dışı bırakma gerçekleştirir. Gerekirse, denetimin kullanıcı arabirimi devre dışı bırakılır ve varsa denetimin penceresi yok edilir. Kapsayıcıya, denetimin artık etkin olmadığı bildirilir. `IOleInPlaceUIWindow`Kapsayıcı tarafından menü ve kenarlık alanı üzerinde anlaşma için kullanılan arabirim serbest bırakılır.

Windows SDK bkz. [IOleInPlaceObject:: InPlaceDeactivate devre dışı bırakma](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) .

## <a name="ioleinplaceobjectwindowlessimplonwindowmessage"></a><a name="onwindowmessage"></a> Ioleınplaceobjectwindowlessıl:: OnWindowMessage

Bir kapsayıcıdan, yerinde etkin olan penceresiz bir denetime ileti gönderir.

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [ıoleınplaceobjectpenceresiz:: OnWindowMessage](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage) .

## <a name="ioleinplaceobjectwindowlessimplreactivateandundo"></a><a name="reactivateandundo"></a> Ioleınplaceobjectwindowlessıl:: ReactivateAndUndo

E_NOTIMPL döndürür.

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>Açıklamalar

Bkz. Windows SDK [IOleInPlaceObject:: ReactivateAndUndo](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) .

## <a name="ioleinplaceobjectwindowlessimplsetobjectrects"></a><a name="setobjectrects"></a> Ioleınplaceobjectwindowlessıl:: SetObjectRects

Denetimin boyutunun ve/veya konumunun değiştiğini bildirmek için kapsayıcı tarafından çağırılır.

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>Açıklamalar

Denetimin `m_rcPos` veri üyesini ve denetim görüntüsünü güncelleştirir. Yalnızca kırpma bölgesini kesişten denetimin bir kısmı görüntülenir. Bir denetimin ekranı daha önce kırpılıyordu ancak kırpma kaldırılırsa, denetimin tam görünümünü yeniden çizmek için bu işlev çağrılabilir.

Windows SDK için bkz. [IOleInPlaceObject:: SetObjectRects](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) .

## <a name="ioleinplaceobjectwindowlessimpluideactivate"></a><a name="uideactivate"></a> Ioleınplaceobjectwindowlessıl:: UIDeactivate

Yerinde etkinleştirmeyi destekleyen denetimin kullanıcı arabirimini devre dışı bırakır ve kaldırır.

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>Açıklamalar

Denetim sınıfının veri üyesini `m_bUIActive` false olarak ayarlar. Bu işlevin ATL uygulamasının her zaman S_OK döndürmesi.

Windows SDK için bkz. [IOleInPlaceObject:: UIDeactivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate) .

## <a name="see-also"></a>Ayrıca bkz.

[CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
