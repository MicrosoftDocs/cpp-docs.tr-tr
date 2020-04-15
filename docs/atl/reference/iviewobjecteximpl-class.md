---
title: IViewObjectExImpl Sınıfı
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
ms.openlocfilehash: 59c5657dcd892544f7e790b52325cb9ecba0dd56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326338"
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl Sınıfı

Bu [sınıf, IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2) `IUnknown` ve [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) arabirimlerinin varsayılan uygulamalarını uygular ve sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IViewObjectExImpl
   : public IViewObjectEx
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IViewObjectExImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IViewObjectExImpl::Draw](#draw)|Denetimin bir temsilini aygıt bağlamına çizer.|
|[IViewObjectExImpl::Dondur](#freeze)|Bir denetimin çizilmiş temsilini dondurur, böylece `Unfreeze`bir . ATL uygulaması E_NOTIMPL döndürür.|
|[IViewObjectExImpl::GetAdvise](#getadvise)|Varsa, denetimde varolan bir danışma lavabosu bağlantısını alır.|
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Çizim için denetim tarafından kullanılan mantıksal paleti döndürür. ATL uygulaması E_NOTIMPL döndürür.|
|[IViewObjectExImpl::GetExtent](#getextent)|HiMETRIC birimlerindeki (birim başına 0,01 milimetre) denetimin görüntü boyutunu kontrol sınıfı veri üyesi [CComControlBase::m_sizeExtent'dan](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)alır.|
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Kullanıcı yeniden boyutlandırırken nesnenin kullanması için kapsayıcıdan boyutlandırma ipuçları sağlar.|
|[IViewObjectExImpl::GetRect](#getrect)|İstenen çizim yönünü açıklayan bir dikdörtgen döndürür. ATL uygulaması E_NOTIMPL döndürür.|
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Nesnenin donukluğu ve hangi çizim yönlerinin desteklendirilmesi hakkında bilgi verir.|
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Belirtilen nokta belirtilen dikdörtgende olup olmadığını denetler ve `pHitResult` [hitresult](/windows/win32/api/ocidl/ne-ocidl-hitresult) değerini .|
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Denetimin ekran dikdörtgeninin belirtilen konum dikdörtgenindeki herhangi bir noktayla çakışıp `pHitResult`örtüşmediğini denetler ve 'deki HITRESULT değerini döndürür.|
|[IViewObjectExImpl::SetAdvise](#setadvise)|Denetim ve tavsiye lavabosu arasında bir bağlantı kurar, böylece lavabo denetimin görünümündeki değişikliklerhakkında bilgilendirilebilir.|
|[IViewObjectExImpl::Çözülme](#unfreeze)|Denetimin çizilmiş temsilini çözer. ATL uygulaması E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2), ve [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) arayüzleri bir denetimin kendisini doğrudan görüntülemesini ve denetim ekranındaki değişiklikleri kapsayıcıya bildirmek için bir tavsiye lavabosu oluşturmasına ve yönetmesine olanak tanır. Arabirim, `IViewObjectEx` titremeiçermeyen çizim, dikdörtgen olmayan ve saydam denetimler ve isabet testi (örneğin, bir fare tıklamasının denetimde ne kadar yakın olması gerektiği) gibi genişletilmiş denetim özellikleri için destek sağlar. Sınıf `IViewObjectExImpl` hata ayıklama oluştururda dökümü `IUnknown` aygıtına bilgi göndererek bu arabirimlerin varsayılan bir uygulama sağlar ve uygular.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="iviewobjecteximpldraw"></a><a name="draw"></a>IViewObjectExImpl::Draw

Denetimin bir temsilini aygıt bağlamına çizer.

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

Bu yöntem, `CComControl::OnDrawAdvanced` sırayla denetim sınıfının `OnDraw` yöntemi çağırır çağırır. ATL Denetim Sihirbazı ile denetiminizi oluşturduğunuzda bir `OnDraw` yöntem otomatik olarak denetim sınıfınıza eklenir. Sihirbazın varsayılanı `OnDraw` "ATL 3.0" etiketiyle bir dikdörtgen çizer.

Bkz. [IViewObject::DWindows](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw) SDK'da tevkif edin.

## <a name="iviewobjecteximplfreeze"></a><a name="freeze"></a>IViewObjectExImpl::Dondur

Bir denetimin çizilmiş temsilini dondurur, böylece `Unfreeze`bir . ATL uygulaması E_NOTIMPL döndürür.

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IViewObject::Windows](/windows/win32/api/oleidl/nf-oleidl-iviewobject-freeze) SDK'da dondurun.

## <a name="iviewobjecteximplgetadvise"></a><a name="getadvise"></a>IViewObjectExImpl::GetAdvise

Varsa, denetimde varolan bir danışma lavabosu bağlantısını alır.

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>Açıklamalar

Danışma lavabo denetim sınıfı veri üyesi [CComControlBase saklanır::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).

Bkz. [IViewObject::Windows](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getadvise) SDK'da GetAdvise.

## <a name="iviewobjecteximplgetcolorset"></a><a name="getcolorset"></a>IViewObjectExImpl::GetColorSet

Çizim için denetim tarafından kullanılan mantıksal paleti döndürür. ATL uygulaması E_NOTIMPL döndürür.

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

Bkz. [IViewObject::Windows](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getcolorset) SDK'da ColorSet'i alın.

## <a name="iviewobjecteximplgetextent"></a><a name="getextent"></a>IViewObjectExImpl::GetExtent

HiMETRIC birimlerindeki (birim başına 0,01 milimetre) denetimin görüntü boyutunu kontrol sınıfı veri üyesi [CComControlBase::m_sizeExtent'dan](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)alır.

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IViewObject2::Windows](/windows/win32/api/oleidl/nf-oleidl-iviewobject2-getextent) SDK'da GetExtent.

## <a name="iviewobjecteximplgetnaturalextent"></a><a name="getnaturalextent"></a>IViewObjectExImpl::GetNaturalExtent

Kullanıcı yeniden boyutlandırırken nesnenin kullanması için kapsayıcıdan boyutlandırma ipuçları sağlar.

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

eğer `dwAspect` DVASPECT_CONTENT ve *pExtentInfo->dwExtentMode* DVEXTENT_CONTENT `psizel` ise, * denetim sınıfının veri üyesi [CComControlBase ayarlar::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). Aksi takdirde, bir hata HRESULT döndürür.

Bkz. [IViewObjectEx::Windows](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) SDK'da Doğal Olarak Alın.

## <a name="iviewobjecteximplgetrect"></a><a name="getrect"></a>IViewObjectExImpl::GetRect

İstenen çizim yönünü açıklayan bir dikdörtgen döndürür. ATL uygulaması E_NOTIMPL döndürür.

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IViewObjectEx::Windows](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getrect) SDK'da GetRect.

## <a name="iviewobjecteximplgetviewstatus"></a><a name="getviewstatus"></a>IViewObjectExImpl::GetViewStatus

Nesnenin donukluğu ve hangi çizim yönlerinin desteklendirilmesi hakkında bilgi verir.

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, ATL denetimin VIEWSTATUS_OPAQUE desteklediğini belirtmek için ayarlar `pdwStatus` (olası değerler [VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus) numaralandırmasındadır).

Bkz. Windows SDK'daki [IViewObjectEx::GetViewStatus.](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus)

## <a name="iviewobjecteximplqueryhitpoint"></a><a name="queryhitpoint"></a>IViewObjectExImpl::QueryHitPoint

Belirtilen nokta belirtilen dikdörtgende olup olmadığını denetler ve `pHitResult` [hitresult](/windows/win32/api/ocidl/ne-ocidl-hitresult) değerini .

```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Açıklamalar

Değer HITRESULT_HIT veya HITRESULT_OUTSIDE olabilir.

`dwAspect` [DVASPECT_CONTENT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)eşitse, yöntem S_OK döndürür. Aksi takdirde, yöntem E_FAIL döndürür.

Bkz. Windows SDK'da [IViewObjectEx::QueryHitPoint.](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint)

## <a name="iviewobjecteximplqueryhitrect"></a><a name="queryhitrect"></a>IViewObjectExImpl::QueryHitRect

Denetimin ekran dikdörtgeninin belirtilen konum dikdörtgenindeki herhangi bir noktayla çakışıp `pHitResult`örtüşmediğini denetler ve 'deki [HITRESULT](/windows/win32/api/ocidl/ne-ocidl-hitresult) değerini döndürür.

```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Açıklamalar

Değer HITRESULT_HIT veya HITRESULT_OUTSIDE olabilir.

`dwAspect` [DVASPECT_CONTENT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)eşitse, yöntem S_OK döndürür. Aksi takdirde, yöntem E_FAIL döndürür.

Bkz. [IViewObjectEx::QueryHitRect](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) Windows SDK içinde.

## <a name="iviewobjecteximplsetadvise"></a><a name="setadvise"></a>IViewObjectExImpl::SetAdvise

Denetim ve tavsiye lavabosu arasında bir bağlantı kurar, böylece lavabo denetimin görünümündeki değişikliklerhakkında bilgilendirilebilir.

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>Açıklamalar

Tavsiye lavabo üzerinde [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) arabirimi için işaretçi kontrol sınıfı veri üyesi [CComControlBase saklanır::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).

Bkz. [IViewObject::Windows](/windows/win32/api/oleidl/nf-oleidl-iviewobject-setadvise) SDK'da SetAdvise.

## <a name="iviewobjecteximplunfreeze"></a><a name="unfreeze"></a>IViewObjectExImpl::Çözülme

Denetimin çizilmiş temsilini çözer. ATL uygulaması E_NOTIMPL döndürür.

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IViewObject::Windows](/windows/win32/api/oleidl/nf-oleidl-iviewobject-unfreeze) SDK'da çözme.

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a>IWorkerThreadClient::CloseHandle

Bu nesneyle ilişkili tanıtıcıyı kapatmak için bu yöntemi uygulayın.

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>Parametreler

*hHandle*<br/>
Tutamacı kapatılmalı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada bir hata HRESULT'ı döndürün.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tutamaç daha önce CWorkerThread bir çağrı ile bu nesne ile [ilişkili::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Örnek

Aşağıdaki kod basit bir `IWorkerThreadClient::CloseHandle`uygulama gösterir.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a>IWorkerThreadClient::Çalıştır

Bu nesneyle ilişkili tanıtıcı sinyal olduğunda kodu yürütmek için bu yöntemi uygulayın.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Parametreler

*dwParam*<br/>
Kullanıcı parametresi.

*hObject*<br/>
Sinyal verilen kulp.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada bir hata HRESULT'ı döndürün.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tutamaç ve DWORD/işaretçisi daha önce Bu nesneyle [CWorkerThread:AddHandle'a](../../atl/reference/cworkerthread-class.md#addhandle)yapılan bir çağrıyla ilişkilendirildi.

### <a name="example"></a>Örnek

Aşağıdaki kod basit bir `IWorkerThreadClient::Execute`uygulama gösterir.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX Arayüzleri Kontrol Eder](/windows/win32/com/activex-controls-interfaces)<br/>
[Öğretici](../../atl/active-template-library-atl-tutorial.md)<br/>
[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
