---
title: Iviewobjectexımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
ms.openlocfilehash: 4ed7a7e4a6070ba52c54c4dace687111cf7d33d8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301941"
---
# <a name="iviewobjecteximpl-class"></a>Iviewobjectexımpl sınıfı

Bu sınıfın uyguladığı `IUnknown` ve varsayılan uygulamalarını sağlar [IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2), ve [IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex) arabirimleri.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IViewObjectExImpl
   : public IViewObjectEx
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IViewObjectExImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IViewObjectExImpl::Draw](#draw)|Bir cihaz bağlamı denetime gösterimini çizer.|
|[IViewObjectExImpl::Freeze](#freeze)|Bir denetim çizilen gösterimini kadar değişmez şekilde donuyor bir `Unfreeze`. ATL uygulamasını E_NOTIMPL döndürür.|
|[IViewObjectExImpl::GetAdvise](#getadvise)|Varsa mevcut bir danışmanlık havuz bağlantı denetimi alır.|
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Çizim için denetim tarafından kullanılan mantıksal paletini döndürür. ATL uygulamasını E_NOTIMPL döndürür.|
|[IViewObjectExImpl::GetExtent](#getextent)|Denetim sınıfı veri üyesi denetimin görüntü boyutunu HIMETRIC biriminde (her birim 0,01 milimetre) alır [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).|
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Kullanıcı objeyi nesne için kapsayıcıdan boyutlandırma ipuçları sağlar.|
|[IViewObjectExImpl::GetRect](#getrect)|Bir istenen çizimin görünüş bilgisini tarif ederken bir dikdörtgen döndürür. ATL uygulamasını E_NOTIMPL döndürür.|
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Nesne ve hangi çizim görünümlerinin desteklendiği geçirgenlik hakkında bilgi döndürür.|
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Belirtilen nokta içinde belirtilen dikdörtgen döndürür olmadığını denetler ve bir [HITRESULT](/windows/desktop/api/ocidl/ne-ocidl-taghitresult) değerini `pHitResult`.|
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Denetimin görünen dikdörtgen çakışıyor herhangi bir noktasında belirtilen konuma dikdörtgen bir HITRESULT değerini döndürür olup olmadığını denetler ve `pHitResult`.|
|[IViewObjectExImpl::SetAdvise](#setadvise)|Havuz denetim görünümünde değişiklikleri hakkında bilgilendirilebilirsiniz için Denetim ve bir öneri havuz arasında bir bağlantı kurar.|
|[IViewObjectExImpl::Unfreeze](#unfreeze)|Denetim çizilen gösterimini canlandırır. ATL uygulamasını E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2), ve [IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex) arabirimleri kendisini doğrudan görüntülemek ve oluşturmak ve bildirmek için bir öneri havuz yönetmek bir denetimini etkinleştirme kapsayıcı değişiklik denetimi görüntülenir. `IViewObjectEx` Arabirimi titreşimsiz çizim, dikdörtgen olmayan ve saydam denetimleri ve (örneğin, ne kadar yakın bir fare tıklaması denetimi olarak kabul edilmesi için olmalıdır) isabet sınaması gibi genişletilmiş denetim özellikleri için destek sağlar. Sınıf `IViewObjectExImpl` uygular ve bu arabirimler bir varsayılan uygulamayı sağlar `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="draw"></a>  IViewObjectExImpl::Draw

Bir cihaz bağlamı denetime gösterimini çizer.

```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı `CComControl::OnDrawAdvanced` denetim sınıfınızın sırayla çağıran `OnDraw` yöntemi. Bir `OnDraw` ATL denetimi Sihirbazı'yla denetiminizi oluşturduğunuzda yöntemi denetim sınıfınıza otomatik olarak eklenir. Sihirbazın varsayılan `OnDraw` "ATL 3.0" etiketli bir dikdörtgen çizer.

Bkz: [IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw) Windows SDK içinde.

##  <a name="freeze"></a>  IViewObjectExImpl::Freeze

Bir denetim çizilen gösterimini kadar değişmez şekilde donuyor bir `Unfreeze`. ATL uygulamasını E_NOTIMPL döndürür.

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IViewObject::Freeze](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-freeze) Windows SDK içinde.

##  <a name="getadvise"></a>  IViewObjectExImpl::GetAdvise

Varsa mevcut bir danışmanlık havuz bağlantı denetimi alır.

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>Açıklamalar

Danışmanlık havuz denetim sınıfı veri üyesi içinde depolanan [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).

Bkz: [IViewObject::GetAdvise](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-getadvise) Windows SDK içinde.

##  <a name="getcolorset"></a>  IViewObjectExImpl::GetColorSet

Çizim için denetim tarafından kullanılan mantıksal paletini döndürür. ATL uygulamasını E_NOTIMPL döndürür.

```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IViewObject::GetColorSet](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-getcolorset) Windows SDK içinde.

##  <a name="getextent"></a>  IViewObjectExImpl::GetExtent

Denetim sınıfı veri üyesi denetimin görüntü boyutunu HIMETRIC biriminde (her birim 0,01 milimetre) alır [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IViewObject2::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-iviewobject2-getextent) Windows SDK içinde.

##  <a name="getnaturalextent"></a>  IViewObjectExImpl::GetNaturalExtent

Kullanıcı objeyi nesne için kapsayıcıdan boyutlandırma ipuçları sağlar.

```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```

### <a name="remarks"></a>Açıklamalar

Varsa `dwAspect` DVASPECT_ICON olduğu ve *pExtentInfo dwExtentMode ->* DVEXTENT_CONTENT ise, ayarlar * `psizel` denetim sınıfın veri üyesinin [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). Aksi takdirde bir hata HRESULT döndürür.

Bkz: [IViewObjectEx::GetNaturalExtent](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) Windows SDK içinde.

##  <a name="getrect"></a>  IViewObjectExImpl::GetRect

Bir istenen çizimin görünüş bilgisini tarif ederken bir dikdörtgen döndürür. ATL uygulamasını E_NOTIMPL döndürür.

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IViewObjectEx::GetRect](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getrect) Windows SDK içinde.

##  <a name="getviewstatus"></a>  IViewObjectExImpl::GetViewStatus

Nesne ve hangi çizim görünümlerinin desteklendiği geçirgenlik hakkında bilgi döndürür.

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, ATL ayarlar `pdwStatus` denetimi VIEWSTATUS_OPAQUE desteklediğini belirtmek için (olası değerler [VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) sabit listesi).

Bkz: [IViewObjectEx::GetViewStatus](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus) Windows SDK içinde.

##  <a name="queryhitpoint"></a>  IViewObjectExImpl::QueryHitPoint

Belirtilen nokta içinde belirtilen dikdörtgen döndürür olmadığını denetler ve bir [HITRESULT](/windows/desktop/api/ocidl/ne-ocidl-taghitresult) değerini `pHitResult`.

```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Açıklamalar

Değer HITRESULT_HIT ya da HITRESULT_OUTSIDE olabilir.

Varsa `dwAspect` eşittir [DVASPECT_ICON](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), yöntem S_OK döndürür. Aksi takdirde E_FAIL yöntemi döndürür.

Bkz: [IViewObjectEx::QueryHitPoint](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint) Windows SDK içinde.

##  <a name="queryhitrect"></a>  IViewObjectExImpl::QueryHitRect

Denetimin görünen dikdörtgen çakışıyor belirtilen konuma dikdörtgenin içindeki herhangi bir noktasını döndürür olup olmadığını denetler ve bir [HITRESULT](/windows/desktop/api/ocidl/ne-ocidl-taghitresult) değerini `pHitResult`.

```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Açıklamalar

Değer HITRESULT_HIT ya da HITRESULT_OUTSIDE olabilir.

Varsa `dwAspect` eşittir [DVASPECT_ICON](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), yöntem S_OK döndürür. Aksi takdirde E_FAIL yöntemi döndürür.

Bkz: [IViewObjectEx::QueryHitRect](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) Windows SDK içinde.

##  <a name="setadvise"></a>  IViewObjectExImpl::SetAdvise

Havuz denetim görünümünde değişiklikleri hakkında bilgilendirilebilirsiniz için Denetim ve bir öneri havuz arasında bir bağlantı kurar.

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>Açıklamalar

İşaretçi [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) öneri havuz arabirimi denetim sınıfı veri üyesi depolanan [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).

Bkz: [IViewObject::SetAdvise](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-setadvise) Windows SDK içinde.

##  <a name="unfreeze"></a>  IViewObjectExImpl::Unfreeze

Denetim çizilen gösterimini canlandırır. ATL uygulamasını E_NOTIMPL döndürür.

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IViewObject::Unfreeze](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-unfreeze) Windows SDK içinde.

##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle

Bu nesneyle ilişkili tanıtıcı kapatmak için bu yöntemi uygular.

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>Parametreler

*hHandle*<br/>
Kapatılması tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarı veya başarısızlık durumunda bir hata HRESULT S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tanıtıcı bir çağrı tarafından bu nesne ile daha önce ilişkili [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Örnek

Aşağıdaki kod basit bir uygulamasını gösterir `IWorkerThreadClient::CloseHandle`.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

##  <a name="execute"></a>  IWorkerThreadClient::Execute

Bu nesneyle ilişkili tanıtıcı sinyal olur olduğunda kod yürütmek için bu yöntemi uygular.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Parametreler

*dwParam*<br/>
Kullanıcı parametresi.

*hObject*<br/>
Sinyal haline tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarı veya başarısızlık durumunda bir hata HRESULT S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı ve DWORD/işaretçi bu yönteme bir çağrı tarafından bu nesne ile daha önce ilişkili [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Örnek

Aşağıdaki kod basit bir uygulamasını gösterir `IWorkerThreadClient::Execute`.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Arabirimleri ActiveX denetimleri](/windows/desktop/com/activex-controls-interfaces)<br/>
[Öğretici](../../atl/active-template-library-atl-tutorial.md)<br/>
[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
