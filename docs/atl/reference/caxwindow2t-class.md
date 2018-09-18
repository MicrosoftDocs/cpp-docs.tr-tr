---
title: CAxWindow2T sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cfb82cfa21d5cc69e66d7980c4878e1659a7a79
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036234"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T sınıfı

Bu sınıf, bir ActiveX denetimini barındırır ve ayrıca lisanslı bir ActiveX denetimlerini barındırma desteği olan bir pencere yönlendirmeye yönelik yöntemleri sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>Parametreler

*Ttemel*<br/>
Sınıf `CAxWindowT` türetilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Oluşturur bir `CAxWindow2T` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAxWindow2T::Create](#create)|Bir konak penceresini oluşturur.|
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır, belirtilen pencerede barındırır ve denetiminden bir arabirim işaretçisi (veya işaretçiler) alır.|
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Pencere sınıfının adını alır. statik yöntem.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAxWindow2T::operator =](#operator_eq)|Varolan bir HWND atar `CAxWindow2T` nesne.|

## <a name="remarks"></a>Açıklamalar

`CAxWindow2T` ActiveX denetimi barındıran bir pencere yönlendirmeye yönelik yöntemleri sağlar. `CAxWindow2T` lisanslı bir ActiveX denetimlerini barındırma desteği de vardır. Barındırma tarafından sağlanan " **AtlAxWinLic80**", tarafından Sarmalanan `CAxWindow2T`.

Sınıf `CAxWindow2` özelleştirmesi uygulanan `CAxWindow2T` sınıfı. Bu özelleştirme olarak bildirilir:

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT` üyeleri bölümünde belgelenmiştir [CAxWindow](../../atl/reference/caxwindow-class.md).

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bu sınıfın üyeleri kullanan bir örnek.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="caxwindow2t"></a>  CAxWindow2T::CAxWindow2T

Oluşturur bir `CAxWindow2T` nesne.

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>Parametreler

*hWnd*<br/>
Var olan bir pencere tanıtıcısı.

##  <a name="create"></a>  CAxWindow2T::Create

Bir konak penceresini oluşturur.

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

`CAxWindow2T::Create` çağrıları [CWindow::Create](../../atl/reference/cwindow-class.md#create) LPCTSTR ile *lpstrWndClass* parametre denetimi barındırma sağlayan pencere sınıfını (`AtlAxWinLic80`).

Bkz: `CWindow::Create` parametreler ve dönüş değeri bir açıklaması.

**Not** değeri olarak 0 kullanılıyorsa *MenuOrID* parametresi 0U belirtilmelidir (Derleyici Hatası kaçınmak için varsayılan değer).

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CAxWindow2T::Create`.

##  <a name="createcontrollic"></a>  CAxWindow2T::CreateControlLic

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
Lisans anahtarı denetimi için; Nonlicensed denetimi oluşturma yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bkz: [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) kalan parametreler ve dönüş değeri bir açıklaması.

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CAxWindow2T::CreateControlLic`.

##  <a name="createcontrollicex"></a>  CAxWindow2T::CreateControlLicEx

Lisanslı bir ActiveX denetimi oluşturur, onu başlatır, belirtilen pencerede barındırır ve denetiminden bir arabirim işaretçisi (veya işaretçiler) alır.

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
Lisans anahtarı denetimi için; Nonlicensed denetimi oluşturma yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bkz: [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) kalan parametreler ve dönüş değeri bir açıklaması.

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CAxWindow2T::CreateControlLicEx`.

##  <a name="getwndclassname"></a>  CAxWindow2T::GetWndClassName

Pencere sınıfının adını alır.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Dönüş Değeri

Pencere sınıfının adını içeren bir dize işaretçisi (`AtlAxWinLic80`) destekli ve lisanslı nonlicensed ActiveX denetimleri barındırabilir.

##  <a name="operator_eq"></a>  CAxWindow2T::operator =

Varolan bir HWND atar `CAxWindow2T` nesne.

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*hWnd*<br/>
Var olan bir pencere tanıtıcısı.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Denetim kapsamı SSS](../../atl/atl-control-containment-faq.md)
