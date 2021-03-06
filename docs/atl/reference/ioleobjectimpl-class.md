---
description: 'Daha fazla bilgi edinin: IOleObjectImpl sınıfı'
title: IOleObjectImpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
ms.openlocfilehash: a8e9fd7dc370ee3f0861ab152061e4a0b96465ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158185"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl sınıfı

Bu sınıf, bir `IUnknown` kapsayıcının bir denetimle iletişim kurduğu Principal arabirimini uygular ve kullanır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IOleObjectImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IOleObjectImpl:: Advise](#advise)|Denetimle bir danışmanlık bağlantısı kurar.|
|[IOleObjectImpl:: Close](#close)|Denetim durumunu çalışır durumundan yüklendi olarak değiştirir.|
|[IOleObjectImpl::D fazla b](#doverb)|Denetime, numaralandırılmış eylemlerden birini gerçekleştirmesini söyler.|
|[IOleObjectImpl::D oVerbDiscardUndo](#doverbdiscardundo)|Denetime, çalıştığı tüm geri alma durumlarını atmasını söyler.|
|[IOleObjectImpl::D fazla Bhide](#doverbhide)|Denetime kullanıcı arabirimini görünümden kaldırmasını söyler.|
|[IOleObjectImpl::D oVerbInPlaceActivate](#doverbinplaceactivate)|Denetimi çalıştırır ve penceresini yükler, ancak denetimin kullanıcı arabirimini yüklemez.|
|[IOleObjectImpl::D fazla baç](#doverbopen)|Denetimin ayrı bir pencerede açık olarak düzenlenmesine neden olur.|
|[IOleObjectImpl::D fazla Bbirincil](#doverbprimary)|Kullanıcı denetimi çift tıkladığında belirtilen eylemi gerçekleştirir. Denetim, genellikle denetimi yerinde etkinleştirmek için eylemi tanımlar.|
|[IOleObjectImpl::D fazla bShow](#doverbshow)|Kullanıcıya yeni ekli bir denetim gösterir.|
|[IOleObjectImpl::D oVerbUIActivate](#doverbuiactivate)|Denetimi yerinde etkinleştirir ve denetimin menü ve araç çubukları gibi kullanıcı arabirimini gösterir.|
|[IOleObjectImpl:: Trmadmenlik](#enumadvise)|Denetimin danışmanlık bağlantılarını numaralandırır.|
|[IOleObjectImpl:: EnumVerbs](#enumverbs)|Denetim için eylemleri numaralandırır.|
|[IOleObjectImpl:: GetClientSite](#getclientsite)|Denetimin istemci sitesini alır.|
|[IOleObjectImpl:: GetClipboardData](#getclipboarddata)|Panodan verileri alır. ATL uygulama E_NOTIMPL döndürür.|
|[IOleObjectImpl:: GetExtent](#getextent)|Denetimin görüntüleme alanının kapsamını alır.|
|[IOleObjectImpl:: GetMiscStatus](#getmiscstatus)|Denetimin durumunu alır.|
|[IOleObjectImpl:: Getbilinen ad](#getmoniker)|Denetimin bilinen adını alır. ATL uygulama E_NOTIMPL döndürür.|
|[IOleObjectImpl:: GetUserClassID](#getuserclassid)|Denetimin sınıf tanımlayıcısını alır.|
|[IOleObjectImpl:: GetUserType](#getusertype)|Denetimin kullanıcı türü adını alır.|
|[IOleObjectImpl:: InitFromData](#initfromdata)|Seçili verilerden denetimi başlatır. ATL uygulama E_NOTIMPL döndürür.|
|[IOleObjectImpl:: IsUpToDate](#isuptodate)|Denetimin güncel olup olmadığını denetler. ATL uygulama S_OK döndürür.|
|[IOleObjectImpl:: OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Geri alma durumu atıldıktan sonra [DoVerbDiscardUndo](#doverbdiscardundo) tarafından çağırılır.|
|[IOleObjectImpl:: OnPostVerbHide](#onpostverbhide)|Denetim gizlendikten sonra [DoVerbHide](#doverbhide) tarafından çağırılır.|
|[IOleObjectImpl:: OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Denetim etkin olduktan sonra [Doverbinplaceactivate](#doverbinplaceactivate) tarafından çağırılır.|
|[IOleObjectImpl:: OnPostVerbOpen](#onpostverbopen)|Denetim ayrı bir pencerede düzenlenmek üzere açıldıktan sonra [DoVerbOpen](#doverbopen) tarafından çağırılır.|
|[IOleObjectImpl:: OnPostVerbShow](#onpostverbshow)|Denetim görünür yapıldıktan sonra [DoVerbShow](#doverbshow) tarafından çağırılır.|
|[IOleObjectImpl:: OnPostVerbUIActivate](#onpostverbuiactivate)|Denetimin kullanıcı arabirimi etkinleştirildikten sonra [Doverbuiactivate](#doverbuiactivate) tarafından çağırılır.|
|[IOleObjectImpl:: OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Geri alma durumu atılmadan önce [DoVerbDiscardUndo](#doverbdiscardundo) tarafından çağırılır.|
|[IOleObjectImpl:: OnPreVerbHide](#onpreverbhide)|Denetim gizlenmadan önce [DoVerbHide](#doverbhide) tarafından çağırılır.|
|[IOleObjectImpl:: OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Denetim etkinleştirilmeden önce [Doverbinplaceactivate](#doverbinplaceactivate) tarafından çağırılır.|
|[IOleObjectImpl:: OnPreVerbOpen](#onpreverbopen)|Denetim ayrı bir pencerede düzenlenmek üzere açılmadan önce [DoVerbOpen](#doverbopen) tarafından çağırılır.|
|[IOleObjectImpl:: OnPreVerbShow](#onpreverbshow)|Denetim görünür yapılmadan önce [DoVerbShow](#doverbshow) tarafından çağırılır.|
|[IOleObjectImpl:: OnPreVerbUIActivate](#onpreverbuiactivate)|Denetimin kullanıcı arabirimi etkinleştirilmeden önce [Doverbuiactivate](#doverbuiactivate) tarafından çağırılır.|
|[IOleObjectImpl:: SetClientSite](#setclientsite)|Denetime kapsayıcıda istemci sitesiyle ilgili olduğunu söyler.|
|[IOleObjectImpl:: SetColorScheme](#setcolorscheme)|Varsa, denetimin uygulamasına bir renk şeması önerir. ATL uygulama E_NOTIMPL döndürür.|
|[IOleObjectImpl:: SetExtent](#setextent)|Denetimin görüntüleme alanının kapsamını ayarlar.|
|[IOleObjectImpl:: SetHostNames](#sethostnames)|Denetime kapsayıcı uygulamasının ve kapsayıcı belgenin adlarını bildirir.|
|[IOleObjectImpl:: Setbilinen adı](#setmoniker)|Denetime adının ne olduğunu söyler. ATL uygulama E_NOTIMPL döndürür.|
|[IOleObjectImpl:: Unadvise](#unadvise)|Denetim ile bir danışmanlık bağlantısını siler.|
|[IOleObjectImpl:: Update](#update)|Denetimi güncelleştirir. ATL uygulama S_OK döndürür.|

## <a name="remarks"></a>Açıklamalar

[IOleObject](/windows/win32/api/oleidl/nn-oleidl-ioleobject) arabirimi, bir kapsayıcının bir denetimle iletişim kurduğu asıl arabirimdir. Sınıfı, `IOleObjectImpl` Bu arabirimin varsayılan bir uygulamasını sağlar ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="ioleobjectimpladvise"></a><a name="advise"></a> IOleObjectImpl:: Advise

Denetimle bir danışmanlık bağlantısı kurar.

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleObject:: Advise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) .

## <a name="ioleobjectimplclose"></a><a name="close"></a> IOleObjectImpl:: Close

Denetim durumunu çalışır durumundan yüklendi olarak değiştirir.

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>Açıklamalar

Denetimi devre dışı bırakır ve varsa Denetim penceresini yok eder. Denetim sınıfı veri üyesi [CComControlBase:: M_BREQUIRESSAVE](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) true Ise ve *dwSaveOption* parametresi OLECLOSE_SAVEIFDIRTY veya OLECLOSE_PROMPTSAVE ise, denetim özellikleri kapatılmadan önce kaydedilir.

[CComControlBase:: m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) ve [ccomcontrolbase:: m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) denetim sınıfı veri üyelerinde tutulan Işaretçiler ve [ccomcontrolbase:: m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase:: m_bWndLess](../../atl/reference/ccomcontrolbase-class.md#m_bwndless)ve [CCOMCONTROLBASE:: m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) veri üyeleri false olarak ayarlanmıştır.

Windows SDK için bkz. [IOleObject:: Close](/windows/win32/api/oleidl/nf-oleidl-ioleobject-close) .

## <a name="ioleobjectimpldoverb"></a><a name="doverb"></a> IOleObjectImpl::D fazla b

Denetime, numaralandırılmış eylemlerden birini gerçekleştirmesini söyler.

```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```

### <a name="remarks"></a>Açıklamalar

Değerine bağlı olarak `iVerb` , ATL `DoVerb` yardımcı işlevlerinden biri aşağıdaki gibi çağrılır:

|*ıverb* Deeri|DoVerb yardımcı işlevi çağrıldı|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[DoVerbDiscardUndo](#doverbdiscardundo)|
|OLEIVERB_HIDE|[DoVerbHide](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[DoVerbInPlaceActivate](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::D fazla Bproperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[DoVerbShow](#doverbshow)|
|OLEIVERB_UIACTIVATE|[DoVerbUIActivate](#doverbuiactivate)|

Bkz. [IOleObject::D fazla b](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK.

## <a name="ioleobjectimpldoverbdiscardundo"></a><a name="doverbdiscardundo"></a> IOleObjectImpl::D oVerbDiscardUndo

Denetime, çalıştığı tüm geri alma durumlarını atmasını söyler.

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
'ndaki Kapsayıcının denetimin çizmesini istediğini dikdörtgenin işaretçisi.

*hwndParent*<br/>
'ndaki Denetimi içeren pencerenin tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ioleobjectimpldoverbhide"></a><a name="doverbhide"></a> IOleObjectImpl::D fazla Bhide

Denetimin kullanıcı arabirimini devre dışı bırakır ve kaldırır ve denetimi gizler.

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
'ndaki Kapsayıcının denetimin çizmesini istediğini dikdörtgenin işaretçisi.

*hwndParent*<br/>
'ndaki Denetimi içeren pencerenin tanıtıcısı. ATL uygulamasında kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ioleobjectimpldoverbinplaceactivate"></a><a name="doverbinplaceactivate"></a> IOleObjectImpl::D oVerbInPlaceActivate

Denetimi çalıştırır ve penceresini yükler, ancak denetimin kullanıcı arabirimini yüklemez.

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
'ndaki Kapsayıcının denetimin çizmesini istediğini dikdörtgenin işaretçisi.

*hwndParent*<br/>
'ndaki Denetimi içeren pencerenin tanıtıcısı. ATL uygulamasında kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

[CComControlBase:: InPlaceActivate öğesini](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate)çağırarak denetimi yerinde etkinleştirir. Denetim sınıfının veri üyesi `m_bWindowOnly` true değilse, `DoVerbInPlaceActivate` önce denetimi penceresiz bir denetim olarak etkinleştirmeye çalışır (yalnızca kapsayıcı [ıoleınplacesitepenceresiz](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)' i destekliyorsa mümkündür). Bu başarısız olursa, işlev genişletilmiş özelliklerle denetimi etkinleştirmeye çalışır (yalnızca kapsayıcı [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)' ı destekliyorsa mümkündür). Bu başarısız olursa, işlev, genişletilmiş özellikler olmadan denetimi etkinleştirmeye çalışır (yalnızca kapsayıcı [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)' ı destekliyorsa mümkündür). Etkinleştirme başarılı olursa, işlev kapsayıcıyı denetimin etkinleştirildiğini bildirir.

## <a name="ioleobjectimpldoverbopen"></a><a name="doverbopen"></a> IOleObjectImpl::D fazla baç

Denetimin ayrı bir pencerede açık olarak düzenlenmesine neden olur.

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
'ndaki Kapsayıcının denetimin çizmesini istediğini dikdörtgenin işaretçisi.

*hwndParent*<br/>
'ndaki Denetimi içeren pencerenin tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ioleobjectimpldoverbprimary"></a><a name="doverbprimary"></a> IOleObjectImpl::D fazla Bbirincil

Kullanıcı denetimi çift tıkladığında gerçekleştirilecek eylemi tanımlar.

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
'ndaki Kapsayıcının denetimin çizmesini istediğini dikdörtgenin işaretçisi.

*hwndParent*<br/>
'ndaki Denetimi içeren pencerenin tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, özellik sayfalarını görüntüleyecek şekilde ayarlanır. Çift tıklama üzerinde farklı bir davranışı çağırmak için denetim sınıfınıza bunu geçersiz kılabilirsiniz; Örneğin, bir video oynayın veya yerinde etkin olun.

## <a name="ioleobjectimpldoverbshow"></a><a name="doverbshow"></a> IOleObjectImpl::D fazla bShow

Kapsayıcıya denetimi görünür hale getirir.

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
'ndaki Kapsayıcının denetimin çizmesini istediğini dikdörtgenin işaretçisi.

*hwndParent*<br/>
'ndaki Denetimi içeren pencerenin tanıtıcısı. ATL uygulamasında kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ioleobjectimpldoverbuiactivate"></a><a name="doverbuiactivate"></a> IOleObjectImpl::D oVerbUIActivate

Denetimin kullanıcı arabirimini etkinleştirir ve kapsayıcının menülerini, bileşik menüler tarafından değiştirilmekte olduğunu bildirir.

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
'ndaki Kapsayıcının denetimin çizmesini istediğini dikdörtgenin işaretçisi.

*hwndParent*<br/>
'ndaki Denetimi içeren pencerenin tanıtıcısı. ATL uygulamasında kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ioleobjectimplenumadvise"></a><a name="enumadvise"></a> IOleObjectImpl:: Trmadmenlik

Bu denetim için kayıtlı danışmanlık bağlantılarının bir listesini sağlar.

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleObject:: Trmadmenlik](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumadvise) .

## <a name="ioleobjectimplenumverbs"></a><a name="enumverbs"></a> IOleObjectImpl:: EnumVerbs

Çağırarak bu denetim için kayıtlı eylemlerin (fiiller) bir listesini sağlar `OleRegEnumVerbs` .

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>Açıklamalar

Projenizin. rgs dosyasına fiil ekleyebilirsiniz. Örneğin bkz. CIRCCTL. [Circ](../../overview/visual-cpp-samples.md) örneğinde RGS.

Windows SDK için bkz. [IOleObject:: EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs) .

## <a name="ioleobjectimplgetclientsite"></a><a name="getclientsite"></a> IOleObjectImpl:: GetClientSite

İşaretçiyi, *Ppclientsite* Içindeki [CComControlBase:: m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) denetim sınıfı veri üyesine koyar ve işaretçinin başvuru sayısını artırır.

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IOleObject:: GetClientSite](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclientsite) .

## <a name="ioleobjectimplgetclipboarddata"></a><a name="getclipboarddata"></a> IOleObjectImpl:: GetClipboardData

Panodan verileri alır.

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IOleObject:: GetClipboardData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) .

## <a name="ioleobjectimplgetextent"></a><a name="getextent"></a> IOleObjectImpl:: GetExtent

Çalışan bir denetimin görüntüleme boyutunu HIMETRIK birimlerde alır (birim başına 0,01 milimetre).

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Açıklamalar

Boyut, [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)denetim sınıfı veri üyesinde saklanır.

Windows SDK için bkz. [IOleObject:: GetExtent](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getextent) .

## <a name="ioleobjectimplgetmiscstatus"></a><a name="getmiscstatus"></a> IOleObjectImpl:: GetMiscStatus

Çağırarak Denetim için kayıtlı durum bilgilerine bir işaretçi döndürür `OleRegGetMiscStatus` .

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>Açıklamalar

Durum bilgileri, denetim ve sunum verileri tarafından desteklenen davranışları içerir. Projenizin. rgs dosyasına durum bilgilerini ekleyebilirsiniz.

Bkz. Windows SDK [IOleObject:: GetMiscStatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) .

## <a name="ioleobjectimplgetmoniker"></a><a name="getmoniker"></a> IOleObjectImpl:: Getbilinen ad

Denetimin bilinen adını alır.

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IOleObject:: Getbilinen ad](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmoniker) .

## <a name="ioleobjectimplgetuserclassid"></a><a name="getuserclassid"></a> IOleObjectImpl:: GetUserClassID

Denetimin sınıf tanımlayıcısını döndürür.

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK ' de [IOleObject:: GetUserClassID](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getuserclassid) öğesine bakın.

## <a name="ioleobjectimplgetusertype"></a><a name="getusertype"></a> IOleObjectImpl:: GetUserType

Çağırarak denetimin kullanıcı türü adını döndürür `OleRegGetUserType` .

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı türü adı, menüler ve iletişim kutuları gibi kullanıcı arabirimleri öğelerinde görüntülenmek üzere kullanılır. Projenizin. rgs dosyasındaki kullanıcı türü adını değiştirebilirsiniz.

Windows SDK bkz. [IOleObject:: GetUserType](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getusertype) .

## <a name="ioleobjectimplinitfromdata"></a><a name="initfromdata"></a> IOleObjectImpl:: InitFromData

Seçili verilerden denetimi başlatır.

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. Windows SDK [IOleObject:: InitFromData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) .

## <a name="ioleobjectimplisuptodate"></a><a name="isuptodate"></a> IOleObjectImpl:: IsUpToDate

Denetimin güncel olup olmadığını denetler.

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IOleObject:: IsUpToDate](/windows/win32/api/oleidl/nf-oleidl-ioleobject-isuptodate) .

## <a name="ioleobjectimplonpostverbdiscardundo"></a><a name="onpostverbdiscardundo"></a> IOleObjectImpl:: OnPostVerbDiscardUndo

Geri alma durumu atıldıktan sonra [DoVerbDiscardUndo](#doverbdiscardundo) tarafından çağırılır.

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Geri alma durumu atıldıktan sonra, yürütülmesi istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbhide"></a><a name="onpostverbhide"></a> IOleObjectImpl:: OnPostVerbHide

Denetim gizlendikten sonra [DoVerbHide](#doverbhide) tarafından çağırılır.

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim gizlendikten sonra, yürütülmesi istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbinplaceactivate"></a><a name="onpostverbinplaceactivate"></a> IOleObjectImpl:: OnPostVerbInPlaceActivate

Denetim etkin olduktan sonra [Doverbinplaceactivate](#doverbinplaceactivate) tarafından çağırılır.

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim etkinleştirildikten sonra, yürütülmesi istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbopen"></a><a name="onpostverbopen"></a> IOleObjectImpl:: OnPostVerbOpen

Denetim ayrı bir pencerede düzenlenmek üzere açıldıktan sonra [DoVerbOpen](#doverbopen) tarafından çağırılır.

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim ayrı bir pencerede düzenlenmek üzere açıldıktan sonra, yürütülmesini istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbshow"></a><a name="onpostverbshow"></a> IOleObjectImpl:: OnPostVerbShow

Denetim görünür yapıldıktan sonra [DoVerbShow](#doverbshow) tarafından çağırılır.

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim görünür yapıldıktan sonra, yürütülmesi istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbuiactivate"></a><a name="onpostverbuiactivate"></a> IOleObjectImpl:: OnPostVerbUIActivate

Denetimin kullanıcı arabirimi etkinleştirildikten sonra [Doverbuiactivate](#doverbuiactivate) tarafından çağırılır.

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin kullanıcı arabirimi etkinleştirildikten sonra, yürütülmesi istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbdiscardundo"></a><a name="onpreverbdiscardundo"></a> IOleObjectImpl:: OnPreVerbDiscardUndo

Geri alma durumu atılmadan önce [DoVerbDiscardUndo](#doverbdiscardundo) tarafından çağırılır.

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Geri alma durumunun atılmasına engel olmak için, HRESULT hatası döndürecek şekilde bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbhide"></a><a name="onpreverbhide"></a> IOleObjectImpl:: OnPreVerbHide

Denetim gizlenmadan önce [DoVerbHide](#doverbhide) tarafından çağırılır.

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin gizlenmasını engellemek için, HRESULT hatası döndürecek şekilde bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbinplaceactivate"></a><a name="onpreverbinplaceactivate"></a> IOleObjectImpl:: OnPreVerbInPlaceActivate

Denetim etkinleştirilmeden önce [Doverbinplaceactivate](#doverbinplaceactivate) tarafından çağırılır.

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin etkin olmasını engellemek için bu yöntemi HRESULT bir hata döndürecek şekilde geçersiz kılın.

## <a name="ioleobjectimplonpreverbopen"></a><a name="onpreverbopen"></a> IOleObjectImpl:: OnPreVerbOpen

Denetim ayrı bir pencerede düzenlenmek üzere açılmadan önce [DoVerbOpen](#doverbopen) tarafından çağırılır.

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin ayrı bir pencerede düzenlenmek üzere açılmasını engellemek için, HRESULT hatası döndürecek şekilde bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbshow"></a><a name="onpreverbshow"></a> IOleObjectImpl:: OnPreVerbShow

Denetim görünür yapılmadan önce [DoVerbShow](#doverbshow) tarafından çağırılır.

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin görünür yapılmasını engellemek için, HRESULT hatası döndürecek şekilde bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbuiactivate"></a><a name="onpreverbuiactivate"></a> IOleObjectImpl:: OnPreVerbUIActivate

Denetimin kullanıcı arabirimi etkinleştirilmeden önce [Doverbuiactivate](#doverbuiactivate) tarafından çağırılır.

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin kullanıcı arabiriminin etkinleştirilmesini engellemek için bu yöntemi bir HRESULT hatası döndürecek şekilde geçersiz kılın.

## <a name="ioleobjectimplsetclientsite"></a><a name="setclientsite"></a> IOleObjectImpl:: SetClientSite

Denetime kapsayıcıda istemci sitesiyle ilgili olduğunu söyler.

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>Açıklamalar

Yöntemi daha sonra S_OK döndürür.

Windows SDK bkz. [IOleObject:: SetClientSite](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setclientsite) .

## <a name="ioleobjectimplsetcolorscheme"></a><a name="setcolorscheme"></a> IOleObjectImpl:: SetColorScheme

Varsa, denetimin uygulamasına bir renk şeması önerir.

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IOleObject:: SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) .

## <a name="ioleobjectimplsetextent"></a><a name="setextent"></a> IOleObjectImpl:: SetExtent

Denetimin görüntüleme alanının kapsamını ayarlar.

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Açıklamalar

Aksi takdirde, `SetExtent` işaret edilen değeri, `psizel` [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)denetim sınıfı veri üyesinde depolar. Bu değer, HIMETRIK birimlerde (birim başına 0,01 milimetre).

Veri üyesi [CComControlBase:: M_BRESIZENATURAL](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) true ise, denetim sınıfı `SetExtent` `psizel` veri üyesi [ccomcontrolbase:: m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)içinde işaret edilen değeri de depolar.

Denetim sınıfı veri üyesi [CComControlBase:: M_BRECOMPOSEONRESIZE](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) true ise, `SetExtent` `SendOnDataChange` `SendOnViewChange` denetim boyutunun değiştiği öneri sahibine kayıtlı tüm danışmanlık havuzları ' nı çağırır ve bildirir.

Bkz. Windows SDK [IOleObject:: SetExtent](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setextent) .

## <a name="ioleobjectimplsethostnames"></a><a name="sethostnames"></a> IOleObjectImpl:: SetHostNames

Denetime kapsayıcı uygulamasının ve kapsayıcı belgenin adlarını bildirir.

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleObject:: SetHostNames](/windows/win32/api/oleidl/nf-oleidl-ioleobject-sethostnames) .

## <a name="ioleobjectimplsetmoniker"></a><a name="setmoniker"></a> IOleObjectImpl:: Setbilinen adı

Denetime adının ne olduğunu söyler.

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IOleObject:: Settakma](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setmoniker) adı.

## <a name="ioleobjectimplunadvise"></a><a name="unadvise"></a> IOleObjectImpl:: Unadvise

Denetim sınıfının veri üyesinde saklanan danışmanlık bağlantısını siler `m_spOleAdviseHolder` .

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleObject:: Unadvise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) .

## <a name="ioleobjectimplupdate"></a><a name="update"></a> IOleObjectImpl:: Update

Denetimi güncelleştirir.

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleObject:: Update](/windows/win32/api/oleidl/nf-oleidl-ioleobject-update) .

## <a name="see-also"></a>Ayrıca bkz.

[CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX denetimleri arabirimleri](/windows/win32/com/activex-controls-interfaces)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
