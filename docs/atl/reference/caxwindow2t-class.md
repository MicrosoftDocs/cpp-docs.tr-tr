---
title: CAxWindow2T sınıfı
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
ms.openlocfilehash: 0d5991dcbf79d1c2415594636a09908586d1dc2f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417994"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T sınıfı

Bu sınıf, ActiveX denetimi barındıran bir pencerenin işlenmesine yönelik yöntemler sağlar ve ayrıca lisanslı ActiveX denetimlerini barındırmak için destek içerir.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>Parametreler

*TBase*<br/>
`CAxWindowT` türetildiği sınıf.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` nesnesi oluşturur.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAxWindow2T:: Create](#create)|Bir konak penceresi oluşturur.|
|[CAxWindow2T:: Createcontrollik](#createcontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|
|[CAxWindow2T:: CreateControlLicEx](#createcontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır, belirtilen pencerede barındırır ve denetimden bir arabirim işaretçisi (veya işaretçiler) alır.|
|[CAxWindow2T:: GetWndClassName](#getwndclassname)|Pencere sınıfının adını alan statik yöntem.|

### <a name="public-operators"></a>Genel İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAxWindow2T:: operator =](#operator_eq)|Varolan bir `CAxWindow2T` nesnesine bir HWND atar.|

## <a name="remarks"></a>Açıklamalar

`CAxWindow2T`, ActiveX denetimi barındıran bir pencereyi işlemek için yöntemler sağlar. `CAxWindow2T`, lisanslı ActiveX denetimlerini barındırmak için de destek içerir. Barındırma, `CAxWindow2T`tarafından Sarmalanan " **AtlAxWinLic80**" tarafından sağlanır.

Sınıf `CAxWindow2`, `CAxWindow2T` sınıfının özelleştirmesi olarak uygulanır. Bu özelleşme şöyle bildirilmiştir:

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT` Üyeler [CAxWindow](../../atl/reference/caxwindow-class.md)altında belgelenmiştir.

Bu sınıfın üyelerini kullanan bir örnek için bkz. [atl AXHost kullanılarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T

`CAxWindow2T` nesnesi oluşturur.

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Mevcut pencerenin bir tutamacı.

##  <a name="create"></a>CAxWindow2T:: Create

Bir konak penceresi oluşturur.

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

`CAxWindow2T::Create`, LPCTSTR *Lpstrwndclass* parametresi ile denetim barındırma (`AtlAxWinLic80`) sağlayan pencere sınıfına ayarlanmış [CWindow:: Create](../../atl/reference/cwindow-class.md#create) yöntemini çağırır.

Parametrelerin açıklaması ve dönüş değeri için bkz. `CWindow::Create`.

**Göz önünde** Eğer, *MenuOrID* parametresinin değeri olarak kullanılırsa, bir derleyici hatasından kaçınmak Için 0u (varsayılan değer) olarak belirtilmelidir.

### <a name="example"></a>Örnek

`CAxWindow2T::Create`kullanan bir örnek için [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bölümüne bakın.

##  <a name="createcontrollic"></a>CAxWindow2T:: Createcontrollik

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
Denetim için lisans anahtarı; Lisanslı olmayan bir denetim oluşturulmışsa NULL.

### <a name="remarks"></a>Açıklamalar

Kalan parametrelerin ve dönüş değerinin açıklaması için bkz. [CAxWindow:: CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) .

### <a name="example"></a>Örnek

`CAxWindow2T::CreateControlLic`kullanan bir örnek için [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bölümüne bakın.

##  <a name="createcontrollicex"></a>CAxWindow2T:: CreateControlLicEx

Lisanslı bir ActiveX denetimi oluşturur, onu başlatır, belirtilen pencerede barındırır ve denetimden bir arabirim işaretçisi (veya işaretçiler) alır.

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
Denetim için lisans anahtarı; Lisanslı olmayan bir denetim oluşturulmışsa NULL.

### <a name="remarks"></a>Açıklamalar

Kalan parametrelerin ve dönüş değerinin açıklaması için bkz. [CAxWindow:: CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) .

### <a name="example"></a>Örnek

`CAxWindow2T::CreateControlLicEx`kullanan bir örnek için [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bölümüne bakın.

##  <a name="getwndclassname"></a>CAxWindow2T:: GetWndClassName

Pencere sınıfının adını alır.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Dönüş Değeri

Lisanslı ve lisanslı olmayan ActiveX denetimlerini barındırasağlayan pencere sınıfının (`AtlAxWinLic80`) adını içeren bir dize işaretçisi.

##  <a name="operator_eq"></a>CAxWindow2T:: operator =

Varolan bir `CAxWindow2T` nesnesine bir HWND atar.

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Mevcut pencerenin bir tutamacı.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Denetim kapsama hakkında SSS](../../atl/atl-control-containment-faq.md)
