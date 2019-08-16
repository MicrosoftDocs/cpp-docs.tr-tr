---
title: IViewObjectExImpl sınıfı
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
ms.openlocfilehash: 3aead41f317d175eac9dcb094aa2070d82dc6185
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495496"
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl sınıfı

Bu sınıf, `IUnknown` ' i uygular ve [IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)ve [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) arabirimlerinin varsayılan uygulamalarını sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IViewObjectExImpl
   : public IViewObjectEx
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız, öğesinden `IViewObjectExImpl`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IViewObjectExImpl::D RAW](#draw)|Bir cihaz bağlamına denetimin gösterimini çizer.|
|[IViewObjectExImpl:: Freeze](#freeze)|Bir denetimin çizilmiş gösterimini dondurur, böylece bir `Unfreeze`. ATL uygulama E_NOTIMPL döndürür.|
|[IViewObjectExImpl:: getadmen](#getadvise)|Varsa, denetimde var olan bir danışmanlık havuz bağlantısını alır.|
|[IViewObjectExImpl:: GetColorSet](#getcolorset)|Çizim için denetim tarafından kullanılan mantıksal paleti döndürür. ATL uygulama E_NOTIMPL döndürür.|
|[IViewObjectExImpl:: GetExtent](#getextent)|Denetim sınıfı veri üyesi [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)' dan, denetimin görüntüleme boyutunu himetrik birimlerde (birim başına 0,01 milimetre ölçüm) alır.|
|[IViewObjectExImpl:: GetNaturalExtent](#getnaturalextent)|Kullanıcı onu yeniden boyutlandırdığından kullanılacak nesne için kapsayıcıdan boyutlandırma ipuçları sağlar.|
|[IViewObjectExImpl:: GetRect](#getrect)|İstenen çizim açısını açıklayan bir dikdörtgen döndürür. ATL uygulama E_NOTIMPL döndürür.|
|[IViewObjectExImpl:: GetViewStatus](#getviewstatus)|Nesnenin geçirgenliği ve hangi çizim yönlerinin desteklendiği hakkında bilgi döndürür.|
|[IViewObjectExImpl:: QueryHitPoint](#queryhitpoint)|Belirtilen noktanın belirtilen dikdörtgende olup olmadığını denetler ve ' de `pHitResult`bir [hitresult](/windows/win32/api/ocidl/ne-ocidl-hitresult) değeri döndürür.|
|[IViewObjectExImpl:: QueryHitRect](#queryhitrect)|Denetimin görüntüleme dikdörtgeninin, belirtilen konum dikdörtgenindeki herhangi bir nokta ile eşleşip eşleşmediğini denetler ve içinde `pHitResult`bir hitresult değeri döndürür.|
|[IViewObjectExImpl:: setadmen](#setadvise)|Denetim ve öneri havuzu arasında bir bağlantı kurar, böylece havuz denetimin görünümündeki değişiklikler hakkında bildirim alabilir.|
|[IViewObjectExImpl:: çöz](#unfreeze)|Denetimin çizilen gösteriminin dondurunur. ATL uygulama E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)ve [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) arabirimleri, bir denetimin kendisini doğrudan görüntülemesini ve denetim görüntüsüne değişiklik kapsayıcısına bildirimde bulunan bir öneri havuzu oluşturup yönetmesini sağlar. `IViewObjectEx` Arabirim, titreşimsiz çizim, dikdörtgensel olmayan ve saydam denetimler ve isabet testi gibi genişletilmiş denetim özellikleri için destek sağlar (örneğin, bir fare tıklaması denetimin göz önünde bulundurulması için ne kadar yakın olması gerekir). Sınıfı `IViewObjectExImpl` , bu arabirimlerin varsayılan bir uygulamasını sağlar ve hata `IUnknown` ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

##  <a name="draw"></a>IViewObjectExImpl::D RAW

Bir cihaz bağlamına denetimin gösterimini çizer.

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

Bu yöntem, `CComControl::OnDrawAdvanced` içindeki denetim `OnDraw` sınıfınızın yöntemine karşılık gelen öğesini çağırır. ATL `OnDraw` Denetim Sihirbazı ile denetiminizi oluştururken denetim sınıfınıza bir yöntem otomatik olarak eklenir. Sihirbazın varsayılan `OnDraw` etiketi "ATL 3,0" etiketiyle bir dikdörtgen çizer.

Bkz. [IViewObject::D raw](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw) Windows SDK.

##  <a name="freeze"></a>IViewObjectExImpl:: Freeze

Bir denetimin çizilmiş gösterimini dondurur, böylece bir `Unfreeze`. ATL uygulama E_NOTIMPL döndürür.

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IViewObject:: Freeze](/windows/win32/api/oleidl/nf-oleidl-iviewobject-freeze) bölümüne bakın.

##  <a name="getadvise"></a>IViewObjectExImpl:: getadmen

Varsa, denetimde var olan bir danışmanlık havuz bağlantısını alır.

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>Açıklamalar

Danışmanlık havuzu, [CComControlBase:: m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)denetim sınıfı veri üyesinde depolanır.

Windows SDK, bkz. [IViewObject:: Getadmen1](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getadvise) .

##  <a name="getcolorset"></a>IViewObjectExImpl:: GetColorSet

Çizim için denetim tarafından kullanılan mantıksal paleti döndürür. ATL uygulama E_NOTIMPL döndürür.

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

Windows SDK [IViewObject:: GetColorSet](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getcolorset) bölümüne bakın.

##  <a name="getextent"></a>IViewObjectExImpl:: GetExtent

Denetim sınıfı veri üyesi [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)' dan, denetimin görüntüleme boyutunu himetrik birimlerde (birim başına 0,01 milimetre ölçüm) alır.

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IViewObject2:: GetExtent](/windows/win32/api/oleidl/nf-oleidl-iviewobject2-getextent) .

##  <a name="getnaturalextent"></a>IViewObjectExImpl:: GetNaturalExtent

Kullanıcı onu yeniden boyutlandırdığından kullanılacak nesne için kapsayıcıdan boyutlandırma ipuçları sağlar.

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

DVASPECT_CONTENT ve *pExtentInfo-> dwExtentMode* DVEXTENT_CONTENT ise, * `psizel` değerini denetim sınıfının veri üyesi [CComControlBase:: m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)olarak ayarlar. `dwAspect` Aksi takdirde, HRESULT hatası döndürür.

Windows SDK bkz. [IViewObjectEx:: GetNaturalExtent](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) .

##  <a name="getrect"></a>IViewObjectExImpl:: GetRect

İstenen çizim açısını açıklayan bir dikdörtgen döndürür. ATL uygulama E_NOTIMPL döndürür.

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IViewObjectEx:: GetRect](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getrect) öğesine bakın.

##  <a name="getviewstatus"></a>IViewObjectExImpl:: GetViewStatus

Nesnenin geçirgenliği ve hangi çizim yönlerinin desteklendiği hakkında bilgi döndürür.

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, ATL, `pdwStatus` denetimin VIEWSTATUS_OPAQUE desteklediğini göstermek için ayarlanır (olası değerler [viewstatus](/windows/win32/api/ocidl/ne-ocidl-viewstatus) numaralandırmasında bulunur).

Windows SDK bkz. [IViewObjectEx:: GetViewStatus](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus) .

##  <a name="queryhitpoint"></a>IViewObjectExImpl:: QueryHitPoint

Belirtilen noktanın belirtilen dikdörtgende olup olmadığını denetler ve ' de `pHitResult`bir [hitresult](/windows/win32/api/ocidl/ne-ocidl-hitresult) değeri döndürür.

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

Eşitse DVASPECT_CONTENT, yöntemi s_ok döndürür. [](/windows/win32/api/wtypes/ne-wtypes-dvaspect) `dwAspect` Aksi takdirde, yöntemi E_FAıL döndürür.

Windows SDK [IViewObjectEx:: QueryHitPoint](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint) öğesine bakın.

##  <a name="queryhitrect"></a>IViewObjectExImpl:: QueryHitRect

Denetimin görüntüleme dikdörtgeninin, belirtilen konum dikdörtgenindeki herhangi bir nokta ile eşleşip eşleşmediğini denetler ve içinde `pHitResult`bir [hitresult](/windows/win32/api/ocidl/ne-ocidl-hitresult) değeri döndürür.

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

Eşitse DVASPECT_CONTENT, yöntemi s_ok döndürür. [](/windows/win32/api/wtypes/ne-wtypes-dvaspect) `dwAspect` Aksi takdirde, yöntemi E_FAıL döndürür.

Windows SDK [IViewObjectEx:: QueryHitRect](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) öğesine bakın.

##  <a name="setadvise"></a>IViewObjectExImpl:: setadmen

Denetim ve öneri havuzu arasında bir bağlantı kurar, böylece havuz denetimin görünümündeki değişiklikler hakkında bildirim alabilir.

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>Açıklamalar

Öneri havuzunda [ıvısesink](/windows/win32/api/objidl/nn-objidl-iadvisesink) arabirimine yönelik Işaretçi, [CComControlBase:: m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink)denetim sınıfı veri üyesinde saklanır.

Windows SDK, bkz. [IViewObject:: Setadmenlik](/windows/win32/api/oleidl/nf-oleidl-iviewobject-setadvise) .

##  <a name="unfreeze"></a>IViewObjectExImpl:: çöz

Denetimin çizilen gösteriminin dondurunur. ATL uygulama E_NOTIMPL döndürür.

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IViewObject:: çöz](/windows/win32/api/oleidl/nf-oleidl-iviewobject-unfreeze) ' ü inceleyin.

##  <a name="closehandle"></a>IWorkerThreadClient:: CloseHandle

Bu nesneyle ilişkili tanıtıcıyı kapatmak için bu yöntemi uygulayın.

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>Parametreler

*hHandle*<br/>
Kapatılacak tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tanıtıcı daha önce bu nesneyle bir [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)çağrısıyla ilişkilendirildi.

### <a name="example"></a>Örnek

Aşağıdaki kod, ' nin `IWorkerThreadClient::CloseHandle`basit bir uygulamasını gösterir.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

##  <a name="execute"></a>IWorkerThreadClient:: Execute

Bu nesneyle ilişkili tanıtıcı sinyal geldiğinde kodu yürütmek için bu yöntemi uygulayın.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Parametreler

*dwParam*<br/>
Kullanıcı parametresi.

*hObject*<br/>
Sinyali verilmiş olan tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tanıtıcı ve DWORD/işaretçi, daha önce bu nesneyle bir [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)çağrısıyla ilişkilendirildi.

### <a name="example"></a>Örnek

Aşağıdaki kod, ' nin `IWorkerThreadClient::Execute`basit bir uygulamasını gösterir.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX denetimleri arabirimleri](/windows/win32/com/activex-controls-interfaces)<br/>
[Öğretici](../../atl/active-template-library-atl-tutorial.md)<br/>
[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
