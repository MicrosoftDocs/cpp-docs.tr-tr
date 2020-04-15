---
title: IOleObjectImpl Sınıfı
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
ms.openlocfilehash: 86d82aea2e92eb99903284abe4ac03478369616c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326518"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl Sınıfı

Bu sınıf, `IUnknown` bir kapsayıcının denetimle iletişim kurduğu temel arabirimi uygular ve bu arabirimdir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IOleObjectImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IOleObjectImpl::Tavsiye](#advise)|Denetimle bir danışma bağlantısı kurar.|
|[IOleObjectImpl::Kapat](#close)|Denetim durumunun çalışmadan yüklenmiş olarak değiştirilmesi.|
|[IOleObjectImpl::DoVerb](#doverb)|Denetime numaralandırılmış eylemlerinden birini gerçekleştirmesini söyler.|
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|Denetime, koruduğu geri alma durumunu atmasını söyler.|
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Denetime kullanıcı arabirimini görünümden kaldırmasını söyler.|
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|Denetimi çalıştırıyor ve penceresini yükler, ancak denetimin kullanıcı arabirimini yüklemez.|
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|Denetimin ayrı bir pencerede açık düzenlenmesine neden olur.|
|[IOleObjectImpl::DoFiilBirincil](#doverbprimary)|Kullanıcı denetimi çift tıklattığında belirtilen eylemi gerçekleştirir. Denetim, genellikle denetimyerinde etkinleştirmek için eylemi tanımlar.|
|[IOleObjectImpl::DoVerbShow](#doverbshow)|Kullanıcıya yeni eklenen denetimi gösterir.|
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Denetimyerinde etkinleştirir ve menüler ve araç çubukları gibi denetimin kullanıcı arabirimini gösterir.|
|[IOleObjectImpl::EnumAdvise](#enumadvise)|Denetimin danışma bağlantılarını oyalar.|
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Denetim için eylemleri sayısallandırır.|
|[IOleObjectImpl::GetClientSite](#getclientsite)|Denetimin istemci sitesini alır.|
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Pano'dan veri alır. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleObjectImpl::GetExtent](#getextent)|Denetimin görüntü alanının kapsamını alır.|
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Denetimin durumunu alır.|
|[IOleObjectImpl::GetMoniker](#getmoniker)|Kontrolün lakabını alır. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Denetimin sınıf tanımlayıcısını alır.|
|[IOleObjectImpl::GetUserType](#getusertype)|Denetimin kullanıcı türü adını alır.|
|[IOleObjectImpl::InitFromData](#initfromdata)|Seçili verilerden denetimi başlatma. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleObjectImpl::IsUpToDate](#isuptodate)|Denetimin güncel olup olmadığını denetler. ATL uygulaması S_OK döndürür.|
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Geri alalı durum atıldıktan sonra [DoVerbDiscardUndo](#doverbdiscardundo) tarafından çağrılır.|
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|Denetim gizlendikten sonra [DoVerbHide](#doverbhide) tarafından çağrılır.|
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Kontrol yerinde etkinleştirildikten sonra [DoVerbInPlaceActivate](#doverbinplaceactivate) tarafından çağrılır.|
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Denetim ayrı bir pencerede düzenleme için açıldıktan sonra [DoVerbOpen](#doverbopen) tarafından çağrılır.|
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Denetim görünür hale getirildikten sonra [DoVerbShow](#doverbshow) tarafından çağrılır.|
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|Denetimin kullanıcı arabirimi etkinleştirildikten sonra [DoVerbUIActivate](#doverbuiactivate) tarafından çağrılır.|
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Geri alalı durum atılmadan önce [DoVerbDiscardUndo](#doverbdiscardundo) tarafından çağrılır.|
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Denetim gizlenmeden önce [DoVerbHide](#doverbhide) tarafından çağrılır.|
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Denetim yerinde etkinleştirilmeden önce [DoVerbInPlaceActivate](#doverbinplaceactivate) tarafından çağrılır.|
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Denetim ayrı bir pencerede düzenleme için açılmadan önce [DoVerbOpen](#doverbopen) tarafından çağrılır.|
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|Denetim görünür hale getirilmeden önce [DoVerbShow](#doverbshow) tarafından çağrılır.|
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|Denetimin kullanıcı arabirimi etkinleştirilmeden önce [DoVerbUIActivate](#doverbuiactivate) tarafından çağrılır.|
|[IOleObjectImpl::SetClientSite](#setclientsite)|Kapsayıcıdaki istemci sitesi hakkındaki denetimi bildirir.|
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|Varsa, denetimin uygulamasına bir renk düzeni önerir. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleObjectImpl::SetExtent](#setextent)|Denetimin görüntü alanının kapsamını ayarlar.|
|[IOleObjectImpl::SetHostNames](#sethostnames)|Denetime kapsayıcı uygulamasının ve kapsayıcı belgesinin adlarını söyler.|
|[IOleObjectImpl::SetMoniker](#setmoniker)|Kontrole lakabının ne olduğunu söyler. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleObjectImpl::Tavsiye siz](#unadvise)|Denetimle ilgili bir danışma bağlantısını siler.|
|[IOleObjectImpl::Güncelleme](#update)|Denetimi güncelleştirir. ATL uygulaması S_OK döndürür.|

## <a name="remarks"></a>Açıklamalar

[IOleObject](/windows/win32/api/oleidl/nn-oleidl-ioleobject) arabirimi, bir kapsayıcının denetimle iletişim kurduğu temel arabirimdir. Sınıf `IOleObjectImpl` bu arabirimin varsayılan bir `IUnknown` uygulamasını sağlar ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="ioleobjectimpladvise"></a><a name="advise"></a>IOleObjectImpl::Tavsiye

Denetimle bir danışma bağlantısı kurar.

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) SDK'da tavsiye de bulunun.

## <a name="ioleobjectimplclose"></a><a name="close"></a>IOleObjectImpl::Kapat

Denetim durumunun çalışmadan yüklenmiş olarak değiştirilmesi.

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>Açıklamalar

Denetimi devre dışı bırakır ve varsa denetim penceresini yok eder. Denetim sınıfı veri üyesi [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) TRUE ise ve *dwSaveOption* parametresi OLECLOSE_SAVEIFDIRTY veya OLECLOSE_PROMPTSAVE ise, denetim özellikleri kapanmadan önce kaydedilir.

Kontrol sınıfı veri üyeleri [CComControlBase düzenlenen işaretçiler::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) ve [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) serbest bırakılır ve veri üyeleri [CComControlBase::m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), ve [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) FALSE olarak ayarlanır.

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-close) SDK'da kapatın.

## <a name="ioleobjectimpldoverb"></a><a name="doverb"></a>IOleObjectImpl::DoVerb

Denetime numaralandırılmış eylemlerinden birini gerçekleştirmesini söyler.

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

`iVerb`Değerine bağlı olarak, ATL `DoVerb` yardımcı işlevlerinden biri aşağıdaki gibi adlandırılır:

|*iFiil* Değer|DoVerb yardımcı işlevi denir|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[DoVerbDiscardUndo](#doverbdiscardundo)|
|OLEIVERB_HIDE|[DoVerbHide](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[DoVerbinPlaceActivate](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[DoVerbShow](#doverbshow)|
|OLEIVERB_UIACTIVATE|[DoVerbuiactivate](#doverbuiactivate)|

Bkz. [IOleObject::DWindows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) SDK'daki oVerb.

## <a name="ioleobjectimpldoverbdiscardundo"></a><a name="doverbdiscardundo"></a>IOleObjectImpl::DoVerbDiscardUndo

Denetime, koruduğu geri alma durumunu atmasını söyler.

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[içinde] Dikdörtgen işaretçisi kapsayıcı içine çekmek için denetim istiyor.

*hwndParent*<br/>
[içinde] Denetimi içeren pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ioleobjectimpldoverbhide"></a><a name="doverbhide"></a>IOleObjectImpl::DoVerbHide

Denetimi devre dışı bırakır ve kaldırır ve denetimi gizler.

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[içinde] Dikdörtgen işaretçisi kapsayıcı içine çekmek için denetim istiyor.

*hwndParent*<br/>
[içinde] Denetimi içeren pencerenin tutamacı. ATL uygulamasında kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ioleobjectimpldoverbinplaceactivate"></a><a name="doverbinplaceactivate"></a>IOleObjectImpl::DoVerbInPlaceActivate

Denetimi çalıştırıyor ve penceresini yükler, ancak denetimin kullanıcı arabirimini yüklemez.

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[içinde] Dikdörtgen işaretçisi kapsayıcı içine çekmek için denetim istiyor.

*hwndParent*<br/>
[içinde] Denetimi içeren pencerenin tutamacı. ATL uygulamasında kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

[CComControlBase::InPlaceActivate'i](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate)arayarak denetimi yerinde etkinleştirir. Denetim sınıfının veri üyesi `m_bWindowOnly` TRUE `DoVerbInPlaceActivate` olmadığı sürece, ilk önce denetimi penceresiz bir denetim olarak etkinleştirmeye çalışır (yalnızca kapsayıcı [IOleInPlaceSiteWindowless'ı](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)destekliyorsa mümkündür). Bu başarısız olursa, işlev denetimi genişletilmiş özelliklerle etkinleştirmeye çalışır (yalnızca kapsayıcı [IOleInPlaceSiteEx'i](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)destekliyorsa mümkündür). Bu başarısız olursa, işlev denetimi genişletilmiş özelliklere sahip olmadan etkinleştirmeye çalışır (yalnızca kapsayıcı [IOleInPlaceSite'yi](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)destekliyorsa mümkündür). Etkinleştirme başarılı olursa, işlev denetimin etkinleştirildiğini kapsayıcıyı bildirir.

## <a name="ioleobjectimpldoverbopen"></a><a name="doverbopen"></a>IOleObjectImpl::DoVerbOpen

Denetimin ayrı bir pencerede açık düzenlenmesine neden olur.

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[içinde] Dikdörtgen işaretçisi kapsayıcı içine çekmek için denetim istiyor.

*hwndParent*<br/>
[içinde] Denetimi içeren pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="ioleobjectimpldoverbprimary"></a><a name="doverbprimary"></a>IOleObjectImpl::DoFiilBirincil

Kullanıcı denetimi çift tıklattığında yapılan eylemi tanımlar.

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[içinde] Dikdörtgen işaretçisi kapsayıcı içine çekmek için denetim istiyor.

*hwndParent*<br/>
[içinde] Denetimi içeren pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, özellik sayfalarını görüntülemek için ayarlayın. Çift tıklatmada farklı bir davranış çağırmak için denetim sınıfınızda bunu geçersiz kılabilirsiniz; örneğin, bir video oynatma veya etkin bir şekilde yerinde hareket edin.

## <a name="ioleobjectimpldoverbshow"></a><a name="doverbshow"></a>IOleObjectImpl::DoVerbShow

Denetimi görünür hale getirmek için kapsayıcıya söyler.

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[içinde] Dikdörtgen işaretçisi kapsayıcı içine çekmek için denetim istiyor.

*hwndParent*<br/>
[içinde] Denetimi içeren pencerenin tutamacı. ATL uygulamasında kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ioleobjectimpldoverbuiactivate"></a><a name="doverbuiactivate"></a>IOleObjectImpl::DoVerbUIActivate

Denetimin kullanıcı arabirimini etkinleştirir ve kapsayıcıya menülerinin bileşik menülerle değiştirildiğini haber vetir.

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[içinde] Dikdörtgen işaretçisi kapsayıcı içine çekmek için denetim istiyor.

*hwndParent*<br/>
[içinde] Denetimi içeren pencerenin tutamacı. ATL uygulamasında kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ioleobjectimplenumadvise"></a><a name="enumadvise"></a>IOleObjectImpl::EnumAdvise

Bu denetim için kayıtlı danışma bağlantılarının numaralandırması sağlar.

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumadvise) SDK'da EnumAdvise.

## <a name="ioleobjectimplenumverbs"></a><a name="enumverbs"></a>IOleObjectImpl::EnumVerbs

Bu denetim için kayıtlı eylemlerin (fiillerin) numaralandırması' nı . `OleRegEnumVerbs`

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>Açıklamalar

Projenizin .rgs dosyasına fiiller ekleyebilirsiniz. Örneğin, bkz. [CIRC](../../overview/visual-cpp-samples.md) örneğinde RGS.

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs) SDK'daki EnumVerbs.

## <a name="ioleobjectimplgetclientsite"></a><a name="getclientsite"></a>IOleObjectImpl::GetClientSite

İşaretçiyi denetim sınıfı veri üyesi [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) *ppClientSite'ye* koyar ve işaretçideki başvuru sayısını artım.

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclientsite) SDK'da Müşteri Sitesi Alın.

## <a name="ioleobjectimplgetclipboarddata"></a><a name="getclipboarddata"></a>IOleObjectImpl::GetClipboardData

Pano'dan veri alır.

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) SDK'daki GetClipboardData.

## <a name="ioleobjectimplgetextent"></a><a name="getextent"></a>IOleObjectImpl::GetExtent

HIMETRIC birimlerinde (birim başına 0,01 milimetre) çalışan bir denetimin ekran boyutunu alır.

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Açıklamalar

Boyutu denetim sınıfı veri üyesi [CComControlBase saklanır::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getextent) SDK'da GetExtent.

## <a name="ioleobjectimplgetmiscstatus"></a><a name="getmiscstatus"></a>IOleObjectImpl::GetMiscStatus

Bir işaretçiyi çağırarak denetim için `OleRegGetMiscStatus`kayıtlı durum bilgilerine döndürür.

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>Açıklamalar

Durum bilgileri, denetim ve sunu verileri tarafından desteklenen davranışları içerir. Projenizin .rgs dosyasına durum bilgilerini ekleyebilirsiniz.

Bkz. [IOleObject::Windows SDK'daki GetMiscStatus.](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus)

## <a name="ioleobjectimplgetmoniker"></a><a name="getmoniker"></a>IOleObjectImpl::GetMoniker

Kontrolün lakabını alır.

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows SDK'daki GetMoniker.](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmoniker)

## <a name="ioleobjectimplgetuserclassid"></a><a name="getuserclassid"></a>IOleObjectImpl::GetUserClassID

Denetimin sınıf tanımlayıcısını döndürür.

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getuserclassid) SDK'da Kullanıcı ClassID'i alın.

## <a name="ioleobjectimplgetusertype"></a><a name="getusertype"></a>IOleObjectImpl::GetUserType

'yi arayarak `OleRegGetUserType`denetimin kullanıcı türü adını verir.

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı türü adı, menüler ve iletişim kutuları gibi kullanıcı arabirimlerinde görüntülenmek için kullanılır. Projenizin .rgs dosyasındaki kullanıcı türü adını değiştirebilirsiniz.

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getusertype) SDK'da Kullanıcı Tipi' ni alın.

## <a name="ioleobjectimplinitfromdata"></a><a name="initfromdata"></a>IOleObjectImpl::InitFromData

Seçili verilerden denetimi başlatma.

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) SDK'daki InitFromData.

## <a name="ioleobjectimplisuptodate"></a><a name="isuptodate"></a>IOleObjectImpl::IsUpToDate

Denetimin güncel olup olmadığını denetler.

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-isuptodate) SDK'da IsUpToDate.

## <a name="ioleobjectimplonpostverbdiscardundo"></a><a name="onpostverbdiscardundo"></a>IOleObjectImpl::OnPostVerbDiscardUndo

Geri alalı durum atıldıktan sonra [DoVerbDiscardUndo](#doverbdiscardundo) tarafından çağrılır.

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Geri alma durumu atıldıktan sonra yürütülmesini istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbhide"></a><a name="onpostverbhide"></a>IOleObjectImpl::OnPostVerbHide

Denetim gizlendikten sonra [DoVerbHide](#doverbhide) tarafından çağrılır.

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim gizli olduktan sonra yürütülmesini istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbinplaceactivate"></a><a name="onpostverbinplaceactivate"></a>IOleObjectImpl::OnPostVerbInPlaceActivate

Kontrol yerinde etkinleştirildikten sonra [DoVerbInPlaceActivate](#doverbinplaceactivate) tarafından çağrılır.

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim yerinde etkinleştirildikten sonra yürütülmesini istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbopen"></a><a name="onpostverbopen"></a>IOleObjectImpl::OnPostVerbOpen

Denetim ayrı bir pencerede düzenleme için açıldıktan sonra [DoVerbOpen](#doverbopen) tarafından çağrılır.

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim ayrı bir pencerede düzenleme için açıldıktan sonra yürütülmesini istediğiniz kod ile bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbshow"></a><a name="onpostverbshow"></a>IOleObjectImpl::OnPostVerbShow

Denetim görünür hale getirildikten sonra [DoVerbShow](#doverbshow) tarafından çağrılır.

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim görünür hale getirildikten sonra yürütülmesini istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpostverbuiactivate"></a><a name="onpostverbuiactivate"></a>IOleObjectImpl::OnPostVerbUIActivate

Denetimin kullanıcı arabirimi etkinleştirildikten sonra [DoVerbUIActivate](#doverbuiactivate) tarafından çağrılır.

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin kullanıcı arabirimi etkinleştirildikten sonra yürütülmesini istediğiniz kodla bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbdiscardundo"></a><a name="onpreverbdiscardundo"></a>IOleObjectImpl::OnPreVerbDiscardUndo

Geri alalı durum atılmadan önce [DoVerbDiscardUndo](#doverbdiscardundo) tarafından çağrılır.

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Geri alma durumunun atılmasını önlemek için, hata HRESULT'ı döndürmek için bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbhide"></a><a name="onpreverbhide"></a>IOleObjectImpl::OnPreVerbHide

Denetim gizlenmeden önce [DoVerbHide](#doverbhide) tarafından çağrılır.

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin gizlenmesini önlemek için, hata HRESULT döndürmek için bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbinplaceactivate"></a><a name="onpreverbinplaceactivate"></a>IOleObjectImpl::OnPreVerbInPlaceActivate

Denetim yerinde etkinleştirilmeden önce [DoVerbInPlaceActivate](#doverbinplaceactivate) tarafından çağrılır.

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin yerinde etkinleştirilmesini önlemek için, hata HRESULT'ı döndürmek için bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbopen"></a><a name="onpreverbopen"></a>IOleObjectImpl::OnPreVerbOpen

Denetim ayrı bir pencerede düzenleme için açılmadan önce [DoVerbOpen](#doverbopen) tarafından çağrılır.

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin ayrı bir pencerede düzenleme için açılmasını önlemek için, hata HRESULT döndürmek için bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbshow"></a><a name="onpreverbshow"></a>IOleObjectImpl::OnPreVerbShow

Denetim görünür hale getirilmeden önce [DoVerbShow](#doverbshow) tarafından çağrılır.

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin görünür olmasını önlemek için, hata HRESULT'ı döndürmek için bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplonpreverbuiactivate"></a><a name="onpreverbuiactivate"></a>IOleObjectImpl::OnPreVerbUIActivate

Denetimin kullanıcı arabirimi etkinleştirilmeden önce [DoVerbUIActivate](#doverbuiactivate) tarafından çağrılır.

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin kullanıcı arabiriminin etkinleştirilmesini önlemek için, hata HRESULT döndürmek için bu yöntemi geçersiz kılın.

## <a name="ioleobjectimplsetclientsite"></a><a name="setclientsite"></a>IOleObjectImpl::SetClientSite

Kapsayıcıdaki istemci sitesi hakkındaki denetimi bildirir.

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>Açıklamalar

Yöntem daha sonra S_OK döndürür.

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setclientsite) SDK'da SetClientSite.

## <a name="ioleobjectimplsetcolorscheme"></a><a name="setcolorscheme"></a>IOleObjectImpl::SetColorScheme

Varsa, denetimin uygulamasına bir renk düzeni önerir.

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) SDK'da ColorScheme'ı ayarlayın.

## <a name="ioleobjectimplsetextent"></a><a name="setextent"></a>IOleObjectImpl::SetExtent

Denetimin görüntü alanının kapsamını ayarlar.

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Açıklamalar

Aksi `SetExtent` takdirde, denetim sınıfı `psizel` veri üyesi CComControlBase tarafından işaret değeri depolar::m_sizeExtent . [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent) Bu değer HIMETRIC birimlerindedir (birim başına 0,01 milimetre).

Denetim sınıfı veri üyesi [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) `SetExtent` DOĞRU ise, aynı `psizel` zamanda denetim sınıfı veri üyesi CComControlBase işaret değeri depolar::m_sizeNatural . [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)

Kontrol sınıfı veri üyesi [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) `SetExtent` DOĞRU `SendOnDataChange` `SendOnViewChange` ise, aramaları ve kontrol boyutu değişti tavsiye sahibi ile kayıtlı tüm danışma lavabolar bildirmek için.

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setextent) SDK'da Ayar Kapsamı.

## <a name="ioleobjectimplsethostnames"></a><a name="sethostnames"></a>IOleObjectImpl::SetHostNames

Denetime kapsayıcı uygulamasının ve kapsayıcı belgesinin adlarını söyler.

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-sethostnames) SDK'daki SetHostNames.

## <a name="ioleobjectimplsetmoniker"></a><a name="setmoniker"></a>IOleObjectImpl::SetMoniker

Kontrole lakabının ne olduğunu söyler.

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows SDK'daki SetMoniker.](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setmoniker)

## <a name="ioleobjectimplunadvise"></a><a name="unadvise"></a>IOleObjectImpl::Tavsiye siz

Denetim sınıfının `m_spOleAdviseHolder` veri üyesinde depolanan danışma bağlantısını siler.

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) SDK'da tavsiye edilmemiş.

## <a name="ioleobjectimplupdate"></a><a name="update"></a>IOleObjectImpl::Güncelleme

Denetimi güncelleştirir.

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleobject-update) SDK'da güncelleştir.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX Arayüzleri Kontrol Eder](/windows/win32/com/activex-controls-interfaces)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
