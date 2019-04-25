---
title: Ioleobjectımpl sınıfı
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
ms.openlocfilehash: 5a815023d340839068873c32f1477d33053b13b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274938"
---
# <a name="ioleobjectimpl-class"></a>Ioleobjectımpl sınıfı

Bu sınıfın uyguladığı `IUnknown` ve kapsayıcı bir denetimle iletişim asıl arabirimidir.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IOleObjectImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IOleObjectImpl::Advise](#advise)|Denetimi ile danışmanlık bir bağlantı kurar.|
|[IOleObjectImpl::Close](#close)|Denetim durumu için yüklenen çalışmasını değiştirir.|
|[IOleObjectImpl::DoVerb](#doverb)|Kendi numaralandırılmış eylemlerden birini gerçekleştirmek için Denetim söyler.|
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|Koruma herhangi bir geri alma durumu atmak denetim söyler.|
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Kullanıcı arabirimi görünümden kaldırmak için Denetim söyler.|
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|Denetimi çalıştırır ve kendi pencere yüklenir, ancak denetimin kullanıcı arabirimi yüklenmez.|
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|Ayrı bir pencerede açık olarak düzenlenen denetim neden olur.|
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|Kullanıcı denetimi tıklattığında belirtilen eylemi gerçekleştirir. Denetim genellikle yerinde denetimi etkinleştirmek için eylem tanımlar.|
|[IOleObjectImpl::DoVerbShow](#doverbshow)|Kullanıcı için yeni eklenen bir denetimi gösterir.|
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Yerinde denetimi etkinleştirir ve denetimin menüleri ve araç çubukları gibi kullanıcı arabirimi gösterilir.|
|[IOleObjectImpl::EnumAdvise](#enumadvise)|Denetimin danışmanlık bağlantıları numaralandırır.|
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Denetim için Eylemler numaralandırır.|
|[IOleObjectImpl::GetClientSite](#getclientsite)|Denetimin istemci site alır.|
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Panodan veri alır. ATL uygulamasını E_NOTIMPL döndürür.|
|[IOleObjectImpl::GetExtent](#getextent)|Denetimin görüntüleme alanı kapsamını alır.|
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Denetim durumunu alır.|
|[IOleObjectImpl::GetMoniker](#getmoniker)|Denetimin ad alır. ATL uygulamasını E_NOTIMPL döndürür.|
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Denetimin sınıf tanımlayıcısı alır.|
|[IOleObjectImpl::GetUserType](#getusertype)|Denetimin kullanıcı türü adını alır.|
|[IOleObjectImpl::InitFromData](#initfromdata)|Seçili veri denetiminden başlatır. ATL uygulamasını E_NOTIMPL döndürür.|
|[IOleObjectImpl::IsUpToDate](#isuptodate)|Denetim güncel olup olmadığını denetler. ATL uygulamasını S_OK döndürür.|
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Çağıran [DoVerbDiscardUndo](#doverbdiscardundo) sonra geri alma durumunu göz ardı edilir.|
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|Çağıran [DoVerbHide](#doverbhide) sonra denetimi gizlenir.|
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Çağıran [DoVerbInPlaceActivate](#doverbinplaceactivate) yerinde denetimi etkinleştirildikten sonra.|
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Çağıran [DoVerbOpen](#doverbopen) denetim ayrı bir pencerede düzenlenmek üzere açıldıktan sonra.|
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Çağıran [DoVerbShow](#doverbshow) denetimin görünür yapıldıktan sonra.|
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|Çağıran [DoVerbUIActivate](#doverbuiactivate) denetimin kullanıcı arabirimi etkinleştirildikten sonra.|
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Çağıran [DoVerbDiscardUndo](#doverbdiscardundo) önce geri alma durumunu göz ardı edilir.|
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Çağıran [DoVerbHide](#doverbhide) önce denetimi gizlenir.|
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Çağıran [DoVerbInPlaceActivate](#doverbinplaceactivate) denetim yerinde etkinleştirilmeden önce.|
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Çağıran [DoVerbOpen](#doverbopen) denetim ayrı bir pencerede düzenleme için açılmış. önce.|
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|Çağıran [DoVerbShow](#doverbshow) önce denetimin görünür duruma getirildi.|
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|Çağıran [DoVerbUIActivate](#doverbuiactivate) önce denetimin kullanıcı arabirimi etkinleştirildi.|
|[IOleObjectImpl::SetClientSite](#setclientsite)|Kendi istemci sitesi kapsayıcısında hakkında denetim söyler.|
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|Bir renk şeması varsa denetimin uygulamaya önerir. ATL uygulamasını E_NOTIMPL döndürür.|
|[IOleObjectImpl::SetExtent](#setextent)|Denetimin görüntüleme alanı kapsamını belirler.|
|[IOleObjectImpl::SetHostNames](#sethostnames)|Denetim kapsayıcılı bir uygulama ve kapsayıcı belge adlarını bildirir.|
|[IOleObjectImpl::SetMoniker](#setmoniker)|Denetimin ne takma adı olduğunu söyler. ATL uygulamasını E_NOTIMPL döndürür.|
|[IOleObjectImpl::Unadvise](#unadvise)|Danışmanlık bir bağlantı denetimi ile siler.|
|[IOleObjectImpl::Update](#update)|Denetim güncelleştirir. ATL uygulamasını S_OK döndürür.|

## <a name="remarks"></a>Açıklamalar

[IOleObject](/windows/desktop/api/oleidl/nn-oleidl-ioleobject) kapsayıcı bir denetimle iletişim asıl arabirimi arabirimidir. Sınıf `IOleObjectImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="advise"></a>  IOleObjectImpl::Advise

Denetimi ile danışmanlık bir bağlantı kurar.

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::Advise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-advise) Windows SDK içinde.

##  <a name="close"></a>  IOleObjectImpl::Close

Denetim durumu için yüklenen çalışmasını değiştirir.

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>Açıklamalar

Denetimin devre dışı bırakır ve varsa Denetim penceresini yok eder. Denetimin veri üyesi sınıfı, [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) true'dur ve *dwSaveOption* parametre OLECLOSE_SAVEIFDIRTY ya da OLECLOSE_PROMPTSAVE ve denetim özellikleri kapatmadan önce kaydedildi.

Denetim sınıf veri üyeleri işaretçileri tutulan [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) ve [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) serbest bırakılır ve veri üyeleri [CComControlBase:: m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), ve [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) FALSE olarak ayarlayın.

Bkz: [IOleObject::Close](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-close) Windows SDK içinde.

##  <a name="doverb"></a>  IOleObjectImpl::DoVerb

Kendi numaralandırılmış eylemlerden birini gerçekleştirmek için Denetim söyler.

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

Değerine bağlı olarak `iVerb`, ATL birini `DoVerb` yardımcı işlevleri gibi çağrılır:

|*iVerb* değeri|Çağrılan DoVerb yardımcı işlev|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[DoVerbDiscardUndo](#doverbdiscardundo)|
|OLEIVERB_HIDE|[DoVerbHide](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[DoVerbInPlaceActivate](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[DoVerbShow](#doverbshow)|
|OLEIVERB_UIACTIVATE|[DoVerbUIActivate](#doverbuiactivate)|

Bkz: [Rpc_e_serverfault](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK içinde.

##  <a name="doverbdiscardundo"></a>  IOleObjectImpl::DoVerbDiscardUndo

Koruma herhangi bir geri alma durumu atmak denetim söyler.

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[in] Kapsayıcı dikdörtgen işaretçisi denetimin içine çizin istiyor.

*hwndParent*<br/>
[in] Denetimi içeren pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

##  <a name="doverbhide"></a>  IOleObjectImpl::DoVerbHide

Devre dışı bırakır ve denetimin kullanıcı arabirimi kaldırır ve denetimini gizler.

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[in] Kapsayıcı dikdörtgen işaretçisi denetimin içine çizin istiyor.

*hwndParent*<br/>
[in] Denetimi içeren pencere tanıtıcısı. ATL uygulamasında kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

##  <a name="doverbinplaceactivate"></a>  IOleObjectImpl::DoVerbInPlaceActivate

Denetimi çalıştırır ve kendi pencere yüklenir, ancak denetimin kullanıcı arabirimi yüklenmez.

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[in] Kapsayıcı dikdörtgen işaretçisi denetimin içine çizin istiyor.

*hwndParent*<br/>
[in] Denetimi içeren pencere tanıtıcısı. ATL uygulamasında kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetimin yerinde çağırarak etkinleştirir [CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Sürece denetim sınıfın veri üyesi `m_bWindowOnly` TRUE ise `DoVerbInPlaceActivate` önce çalışır denetimi penceresiz denetime olarak etkinleştirmek (yalnızca kapsayıcı destekliyorsa, olası [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless)). Bu başarısız olursa, işlev denetimin genişletilmiş özellikleri ile etkinleştirmeyi dener (yalnızca kapsayıcı destekliyorsa, olası [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex)). İşlev başarısız olursa, hiçbir genişletilmiş özellik denetimiyle etkinleştirmek çalışır (yalnızca kapsayıcı destekliyorsa, olası [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite)). Etkinleştirme başarılı olursa, işlev kapsayıcı denetimi etkinleştirildi bildirir.

##  <a name="doverbopen"></a>  IOleObjectImpl::DoVerbOpen

Ayrı bir pencerede açık olarak düzenlenen denetim neden olur.

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[in] Kapsayıcı dikdörtgen işaretçisi denetimin içine çizin istiyor.

*hwndParent*<br/>
[in] Denetimi içeren pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

##  <a name="doverbprimary"></a>  IOleObjectImpl::DoVerbPrimary

Kullanıcı denetimi tıklattığında gerçekleştirilecek eylemi tanımlar.

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[in] Kapsayıcı dikdörtgen işaretçisi denetimin içine çizin istiyor.

*hwndParent*<br/>
[in] Denetimi içeren pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Özellik sayfaları görüntülemek için varsayılan olarak ayarlayın. Bu, farklı bir davranış çift tıklatıldığında çağrılacak denetim sınıfınızdaki kılabilirsiniz; Örneğin, bir videoyu oynatabilir veya yerinde etkin gidin.

##  <a name="doverbshow"></a>  IOleObjectImpl::DoVerbShow

Denetimi görünür hale getirmek için kapsayıcı söyler.

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[in] Kapsayıcı dikdörtgen işaretçisi denetimin içine çizin istiyor.

*hwndParent*<br/>
[in] Denetimi içeren pencere tanıtıcısı. ATL uygulamasında kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="doverbuiactivate"></a>  IOleObjectImpl::DoVerbUIActivate

Denetimin kullanıcı arabirimini etkinleştirir ve kapsayıcının menülerini bileşik menüleri değiştirilmektedir bildirir.

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
[in] Kapsayıcı dikdörtgen işaretçisi denetimin içine çizin istiyor.

*hwndParent*<br/>
[in] Denetimi içeren pencere tanıtıcısı. ATL uygulamasında kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="enumadvise"></a>  IOleObjectImpl::EnumAdvise

Bu denetim için kayıtlı danışmanlık bağlantıları numaralandırmasını sağlar.

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::EnumAdvise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumadvise) Windows SDK içinde.

##  <a name="enumverbs"></a>  IOleObjectImpl::EnumVerbs

Çağırarak kayıtlı eylemlerin (fiiller) Bu denetim için bir numaralandırma sağlayan `OleRegEnumVerbs`.

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>Açıklamalar

Fiiller projenizin .rgs dosyasına ekleyebilirsiniz. Örneğin, CIRCCTL bakın. RGS içinde [DAİ](../../overview/visual-cpp-samples.md) örnek.

Bkz: [IOleObject::EnumVerbs](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumverbs) Windows SDK içinde.

##  <a name="getclientsite"></a>  IOleObjectImpl::GetClientSite

Denetim sınıfı veri üyesi işaretçi koyar [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) içine *ppClientSite* ve işaretçi başvuru sayısını artırır.

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::GetClientSite](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getclientsite) Windows SDK içinde.

##  <a name="getclipboarddata"></a>  IOleObjectImpl::GetClipboardData

Panodan veri alır.

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::GetClipboardData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) Windows SDK içinde.

##  <a name="getextent"></a>  IOleObjectImpl::GetExtent

Çalışan bir denetimin görüntü boyutunu HIMETRIC biriminde (her birim 0,01 milimetre) alır.

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Açıklamalar

Boyutu denetim sınıfı veri üyesi içinde depolanan [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).

Bkz: [IOleObject::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getextent) Windows SDK içinde.

##  <a name="getmiscstatus"></a>  IOleObjectImpl::GetMiscStatus

Çağırarak denetimi için kaydedilmiş durum bilgisi için bir işaretçi döndürür `OleRegGetMiscStatus`.

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>Açıklamalar

Durum bilgileri denetim ve sunu verileri tarafından desteklenen davranışlar içerir. Durum bilgisi projenizin .rgs dosyasına ekleyebilirsiniz.

Bkz: [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) Windows SDK içinde.

##  <a name="getmoniker"></a>  IOleObjectImpl::GetMoniker

Denetimin ad alır.

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::GetMoniker](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmoniker) Windows SDK içinde.

##  <a name="getuserclassid"></a>  IOleObjectImpl::GetUserClassID

Denetimin sınıf tanımlayıcısı döndürür.

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::GetUserClassID](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getuserclassid) Windows SDK içinde.

##  <a name="getusertype"></a>  IOleObjectImpl::GetUserType

Denetimin kullanıcı türü adı çağırarak döndürür `OleRegGetUserType`.

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı türü adı, menüler ve iletişim kutuları gibi kullanıcı arabirim öğeleri görüntülemek için kullanılır. Projenizin .rgs dosyasındaki kullanıcı türü adını değiştirebilirsiniz.

Bkz: [IOleObject::GetUserType](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getusertype) Windows SDK içinde.

##  <a name="initfromdata"></a>  IOleObjectImpl::InitFromData

Seçili veri denetiminden başlatır.

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::InitFromData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-initfromdata) Windows SDK içinde.

##  <a name="isuptodate"></a>  IOleObjectImpl::IsUpToDate

Denetim güncel olup olmadığını denetler.

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::IsUpToDate](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-isuptodate) Windows SDK içinde.

##  <a name="onpostverbdiscardundo"></a>  IOleObjectImpl::OnPostVerbDiscardUndo

Çağıran [DoVerbDiscardUndo](#doverbdiscardundo) sonra geri alma durumunu göz ardı edilir.

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Geri alma durumunu göz ardı edilir sonra yürütülen istediğiniz kodu bu yöntemi yok sayın.

##  <a name="onpostverbhide"></a>  IOleObjectImpl::OnPostVerbHide

Çağıran [DoVerbHide](#doverbhide) sonra denetimi gizlenir.

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin gizli sonra yürütülen istediğiniz kodu bu yöntemi yok sayın.

##  <a name="onpostverbinplaceactivate"></a>  IOleObjectImpl::OnPostVerbInPlaceActivate

Çağıran [DoVerbInPlaceActivate](#doverbinplaceactivate) yerinde denetimi etkinleştirildikten sonra.

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim yerinde etkinleştirildikten sonra yürütülen istediğiniz kodu bu yöntemi yok sayın.

##  <a name="onpostverbopen"></a>  IOleObjectImpl::OnPostVerbOpen

Çağıran [DoVerbOpen](#doverbopen) denetim ayrı bir pencerede düzenlenmek üzere açıldıktan sonra.

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim, ayrı bir pencerede düzenlenmek üzere açıldıktan sonra yürütülen istediğiniz kodu bu yöntemi yok sayın.

##  <a name="onpostverbshow"></a>  IOleObjectImpl::OnPostVerbShow

Çağıran [DoVerbShow](#doverbshow) denetimin görünür yapıldıktan sonra.

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin görünür yapıldıktan sonra yürütülen istediğiniz kodu bu yöntemi yok sayın.

##  <a name="onpostverbuiactivate"></a>  IOleObjectImpl::OnPostVerbUIActivate

Çağıran [DoVerbUIActivate](#doverbuiactivate) denetimin kullanıcı arabirimi etkinleştirildikten sonra.

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin kullanıcı arabirimi etkinleştirildikten sonra yürütülen istediğiniz kodu bu yöntemi yok sayın.

##  <a name="onpreverbdiscardundo"></a>  IOleObjectImpl::OnPreVerbDiscardUndo

Çağıran [DoVerbDiscardUndo](#doverbdiscardundo) önce geri alma durumunu göz ardı edilir.

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Geri alma durumunu göz ardı önlemek için bir hata HRESULT döndürmek için bu yöntemi yok sayın.

##  <a name="onpreverbhide"></a>  IOleObjectImpl::OnPreVerbHide

Çağıran [DoVerbHide](#doverbhide) önce denetimi gizlenir.

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim gizlenmelerini önlemek için bir hata HRESULT döndürmek için bu yöntemi yok sayın.

##  <a name="onpreverbinplaceactivate"></a>  IOleObjectImpl::OnPreVerbInPlaceActivate

Çağıran [DoVerbInPlaceActivate](#doverbinplaceactivate) denetim yerinde etkinleştirilmeden önce.

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Yerinde etkinleştirilmiş denetim önlemek için bir hata HRESULT döndürmek için bu yöntemi yok sayın.

##  <a name="onpreverbopen"></a>  IOleObjectImpl::OnPreVerbOpen

Çağıran [DoVerbOpen](#doverbopen) denetim ayrı bir pencerede düzenleme için açılmış. önce.

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim için ayrı bir pencerede düzenleme açılmasını önlemek için bir hata HRESULT döndürmek için bu yöntemi yok sayın.

##  <a name="onpreverbshow"></a>  IOleObjectImpl::OnPreVerbShow

Çağıran [DoVerbShow](#doverbshow) önce denetimin görünür duruma getirildi.

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimi görünür hale önlemek için bir hata HRESULT döndürmek için bu yöntemi yok sayın.

##  <a name="onpreverbuiactivate"></a>  IOleObjectImpl::OnPreVerbUIActivate

Çağıran [DoVerbUIActivate](#doverbuiactivate) önce denetimin kullanıcı arabirimi etkinleştirildi.

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Etkinleştirilmekte olan kullanıcı arabirimi denetim önlemek için bir hata HRESULT döndürmek için bu yöntemi yok sayın.

##  <a name="setclientsite"></a>  IOleObjectImpl::SetClientSite

Kendi istemci sitesi kapsayıcısında hakkında denetim söyler.

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>Açıklamalar

Yöntemi ardından S_OK döndürür.

Bkz: [IOleObject::SetClientSite](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setclientsite) Windows SDK içinde.

##  <a name="setcolorscheme"></a>  IOleObjectImpl::SetColorScheme

Bir renk şeması varsa denetimin uygulamaya önerir.

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) Windows SDK içinde.

##  <a name="setextent"></a>  IOleObjectImpl::SetExtent

Denetimin görüntüleme alanı kapsamını belirler.

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Açıklamalar

Aksi takdirde, `SetExtent` işaret ettiği değer depolar `psizel` denetim sınıfı veri üyesi içinde [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent). Bu değer, HIMETRIC birimindeki (her birim 0,01 milimetre) olur.

Denetim sınıfı veri üyesi, [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) TRUE ise `SetExtent` işaret ettiği değer de depolar `psizel` denetim sınıfı veri üyesi içinde [CComControlBase::m_sizeNatural ](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).

Denetimin veri üyesi sınıfı, [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) TRUE ise `SetExtent` çağrıları `SendOnDataChange` ve `SendOnViewChange` denetimi boyutuna sahip öneri sahibi ile kayıtlı tüm danışmanlık havuzlarını bildirmek için değiştirildi.

Bkz: [IOleObject::SetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setextent) Windows SDK içinde.

##  <a name="sethostnames"></a>  IOleObjectImpl::SetHostNames

Denetim kapsayıcılı bir uygulama ve kapsayıcı belge adlarını bildirir.

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::SetHostNames](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-sethostnames) Windows SDK içinde.

##  <a name="setmoniker"></a>  IOleObjectImpl::SetMoniker

Denetimin ne takma adı olduğunu söyler.

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::SetMoniker](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setmoniker) Windows SDK içinde.

##  <a name="unadvise"></a>  IOleObjectImpl::Unadvise

Denetim sınıfının depolanan danışmanlık bağlantısını siler `m_spOleAdviseHolder` veri üyesi.

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::Unadvise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-unadvise) Windows SDK içinde.

##  <a name="update"></a>  IOleObjectImpl::Update

Denetim güncelleştirir.

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleObject::Update](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-update) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Arabirimleri ActiveX denetimleri](/windows/desktop/com/activex-controls-interfaces)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
