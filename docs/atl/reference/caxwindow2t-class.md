---
title: CAxWindow2T Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
ms.openlocfilehash: 14080b624132979df533135bc1eef108dc793398
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318694"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T Sınıfı

Bu sınıf, ActiveX denetimi barındıran bir pencereyi işlemek için yöntemler sağlar ve lisanslı ActiveX denetimlerini barındırma desteğine de sahiptir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>Parametreler

*TBase*<br/>
`CAxWindowT` Türetilen sınıf.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Bir `CAxWindow2T` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAxWindow2T::Oluştur](#create)|Ana bilgisayar penceresi oluşturur.|
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Lisanslı activex denetimi oluşturur, başlatılmasını, belirtilen pencerede barındırır ve denetimden bir arabirim işaretçisi (veya işaretçisi) alır.|
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Pencere sınıfının adını alan statik yöntem.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAxWindow2T::operatör =](#operator_eq)|Varolan `CAxWindow2T` bir nesneye BIR HWND atar.|

## <a name="remarks"></a>Açıklamalar

`CAxWindow2T`ActiveX denetimi barındıran bir pencereyi işlemek için yöntemler sağlar. `CAxWindow2T`lisanslı ActiveX denetimlerini barındırma desteğine de sahiptir. Barındırma tarafından sağlanmaktadır " **AtlAxWinLic80**", `CAxWindow2T`hangi tarafından sarılır .

`CAxWindow2T` Sınıf, `CAxWindow2` sınıfın uzmanlık alanı olarak uygulanır. Bu uzmanlık şu şekilde beyan edilir:

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT`üyeler [CAxWindow](../../atl/reference/caxwindow-class.md)altında belgelenmiştir.

Bu sınıfın üyelerini kullanan bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="caxwindow2tcaxwindow2t"></a><a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T

Bir `CAxWindow2T` nesne inşa eder.

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Varolan bir pencerenin tutamacı.

## <a name="caxwindow2tcreate"></a><a name="create"></a>CAxWindow2T::Oluştur

Ana bilgisayar penceresi oluşturur.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="remarks"></a>Açıklamalar

`CAxWindow2T::Create`[cwindow çağırır::LPCTSTR](../../atl/reference/cwindow-class.md#create) *lpstrWndClass* parametre ile denetim barındırma sağlayan pencere`AtlAxWinLic80`sınıfına ayarlanmış ().

Parametrelerin ve iade değerinin açıklaması için bkz. `CWindow::Create`

**Not** *MenuOrID* parametresi için değer olarak 0 kullanılırsa, derleyici hatasını önlemek için 0U (varsayılan değer) olarak belirtilmelidir.

### <a name="example"></a>Örnek

Kullanan `CAxWindow2T::Create`bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="caxwindow2tcreatecontrollic"></a><a name="createcontrollic"></a>CAxWindow2T::CreateControlLic

Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.

```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>Parametreler

*bstrLicKey*<br/>
Denetim için lisans anahtarı; Lisanssız denetim oluşturuyorsa NULL.

### <a name="remarks"></a>Açıklamalar

Bkz. [CAxWindow::Kalan](../../atl/reference/caxwindow-class.md#createcontrol) parametrelerin ve iade değerinin açıklaması için Denetim Oluştur.

### <a name="example"></a>Örnek

Kullanan `CAxWindow2T::CreateControlLic`bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="caxwindow2tcreatecontrollicex"></a><a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx

Lisanslı activex denetimi oluşturur, başlatılmasını, belirtilen pencerede barındırır ve denetimden bir arabirim işaretçisi (veya işaretçisi) alır.

```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```

### <a name="parameters"></a>Parametreler

*bstrLicKey*<br/>
Denetim için lisans anahtarı; Lisanssız denetim oluşturuyorsa NULL.

### <a name="remarks"></a>Açıklamalar

Bkz. [CAxWindow::Kalan](../../atl/reference/caxwindow-class.md#createcontrolex) parametrelerin ve iade değerinin açıklaması için CreateControlEx.

### <a name="example"></a>Örnek

Kullanan `CAxWindow2T::CreateControlLicEx`bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="caxwindow2tgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow2T::GetWndClassName

Pencere sınıfının adını alır.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Dönüş Değeri

Lisanslı ve lisanssız ActiveX denetimlerini`AtlAxWinLic80`barındırabilen pencere sınıfının adını () içeren bir dize işaretçisi.

## <a name="caxwindow2toperator-"></a><a name="operator_eq"></a>CAxWindow2T::operatör =

Varolan `CAxWindow2T` bir nesneye BIR HWND atar.

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Varolan bir pencerenin tutamacı.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Kontrol Çevreleme SSS](../../atl/atl-control-containment-faq.md)
