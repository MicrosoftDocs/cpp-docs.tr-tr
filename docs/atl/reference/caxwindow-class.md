---
title: CAxWindow sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0eda5fc385f094bd7a18bff521250453ebb66c84
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757942"
---
# <a name="caxwindow-class"></a>CAxWindow sınıfı

Bu sınıf, bir ActiveX denetimi barındırma pencere yönlendirmeye yönelik yöntemleri sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAxWindow : public CWindow
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AttachControl](#attachcontrol)|Varolan bir ActiveX denetimini ekler `CAxWindow` nesne.|
|[CAxWindow](#caxwindow)|Oluşturur bir `CAxWindow` nesne.|
|[CreateControl](#createcontrol)|Bir ActiveX denetimi oluşturur, onu başlatır ve onu barındıran `CAxWindow` penceresi.|
|[CreateControlEx](#createcontrolex)|Bir ActiveX denetimi oluşturur ve denetimi bir arabirim işaretçisi (veya işaretçiler) alır.|
|[GetWndClassName](#getwndclassname)|(Statik) Önceden tanımlanmış sınıf adını alır. `CAxWindow` nesne.|
|[QueryControl](#querycontrol)|Alır `IUnknown` barındırılan ActiveX denetimi.|
|[QueryHost](#queryhost)|Alır `IUnknown` işaretçisinin `CAxWindow` nesne.|
|[SetExternalDispatch](#setexternaldispatch)|Tarafından kullanılan dış gönderme arabirimi ayarlar `CAxWindow` nesne.|
|[SetExternalUIHandler](#setexternaluihandler)|Dış ayarlar `IDocHostUIHandler` tarafından kullanılan arabirimi `CAxWindow` nesne.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Varolan bir HWND atar `CAxWindow` nesne.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir ActiveX denetimi barındıran bir pencere yönlendirmeye yönelik yöntemleri sağlar. Barındırma tarafından sağlanan " **AtlAxWin80"**, tarafından Sarmalanan `CAxWindow`.

Sınıf `CAxWindow` özelleştirmesi uygulanan `CAxWindowT` sınıfı. Bu özelleştirme olarak bildirilir:

`typedef CAxWindowT<CWindow> CAxWindow;`

Temel sınıf değiştirmeniz gerekiyorsa, kullanabileceğiniz `CAxWindowT` ve yeni temel sınıfın şablon bağımsız değişken belirtin.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="attachcontrol"></a>  CAxWindow::AttachControl

Zaten mevcut değilse ve belirtilen denetim konağa ekler, yeni bir ana bilgisayar nesnesi oluşturur.

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parametreler

*pControl*  
[in] Bir işaretçi `IUnknown` denetimi.

*ppUnkContainer*  
[out] Bir işaretçi `IUnknown` konağın ( `AxWin` nesne).

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

İliştirilmekte olan denetim nesne doğru çağırmadan önce başlatılmalıdır `AttachControl`.

##  <a name="caxwindow"></a>  CAxWindow::CAxWindow

Oluşturur bir `CAxWindow` var olan bir pencere nesnesi işleci kullanılarak nesne.

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*hWnd*  
Var olan bir pencere nesnesi için bir tanıtıcı.

##  <a name="createcontrol"></a>  CAxWindow::CreateControl

Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.

```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*  
Denetimi oluşturmak için bir dize işaretçisi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:

- Bir ProgID gibi "MSCAL. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID

- Gibi bir URL "http://www.microsoft.com"

- Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"

- HTML gibi bir parçasını "MSHTML:\<HTML >\<GÖVDESİ > metin satırı budur\</BODY >\</HTML >"

   > [!NOTE]
   > "MSHTML:" MSHTML stream olacak şekilde atanır böylece HTML parçasını gelmelidir. ProgID ve CLSID yalnızca Windows mobil platformlarda desteklenir. Windows CE Platform katıştırılmış, Windows Mobile CE IE destek desteğiyle dışında ProgID dahil olmak üzere tüm CLSID, URL, başvuru türleri etkin belge ve HTML parçasını.

*pStream*  
[in] Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. NULL olabilir.

*ppUnkContainer*  
[out] Adresi alacak bir işaretçi `IUnknown` kapsayıcının. NULL olabilir.

*dwResID*  
Bir HTML kaynağının kaynak kimliği. WebBrowser denetimi oluşturulur ve belirtilen kaynak yüklendi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Dosyanın ikinci sürümü, bu yöntem kullandıysanız, bir HTML denetimini oluşturulur ve tarafından tanımlanan kaynağa bağlı *dwResID*.

Bu yöntem çağrıldığında aynı sonucu verir:

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

Bkz: [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) oluşturmak, başlatmak ve lisanslı bir ActiveX denetimi barındırma.

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CreateControl`.

##  <a name="createcontrolex"></a>  CAxWindow::CreateControlEx

Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.

```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*  
Denetimi oluşturmak için bir dize işaretçisi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:

- Bir ProgID gibi "MSCAL. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID

- Gibi bir URL "http://www.microsoft.com"

- Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"

- HTML gibi bir parçasını "MSHTML:\<HTML >\<GÖVDESİ > metin satırı budur\</BODY >\</HTML >"

   > [!NOTE]
   > "MSHTML:" MSHTML stream olacak şekilde atanır böylece HTML parçasını gelmelidir. ProgID ve CLSID yalnızca Windows mobil platformlarda desteklenir. Windows CE Platform katıştırılmış, Windows Mobile CE IE destek desteğiyle dışında ProgID dahil olmak üzere tüm CLSID, URL, başvuru türleri etkin belge ve HTML parçasını.

*pStream*  
[in] Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. NULL olabilir.

*ppUnkContainer*  
[out] Adresi alacak bir işaretçi `IUnknown` kapsayıcının. NULL olabilir.

*ppUnkControl*  
[out] Adresi alacak bir işaretçi `IUnknown` denetimi. NULL olabilir.

*iidSink*  
[in] Kapsanan nesne üzerinde giden bir arabirim arabirimi tanımlayıcısı. IID_NULL olabilir.

*punkSink*  
[in] Bir işaretçi `IUnknown` arabirimi tarafından belirtilen kapsanan nesne üzerindeki bağlantı noktasına bağlı havuz nesnenin *iidSink*.

*dwResID*  
[in] Bir HTML kaynağının kaynak kimliği. WebBrowser denetimi oluşturulur ve belirtilen kaynak yüklendi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem benzer [CAxWindow::CreateControl](#createcontrol), ancak bu yöntem aksine `CreateControlEx` de yeni oluşturulan denetime bir arabirim işaretçisi alır ve denetimi tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak sağlar.

Bkz: [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) oluşturmak, başlatmak ve lisanslı bir ActiveX denetimi barındırma.

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CreateControlEx`.

##  <a name="getwndclassname"></a>  CAxWindow::GetWndClassName

Pencere sınıfının adını alır.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Dönüş Değeri

ActiveX denetimlerini nonlicensed barındırabilir pencere sınıfının adını içeren bir dize işaretçisi.

##  <a name="operator_eq"></a>  CAxWindow::operator =

Varolan bir HWND atar `CAxWindow` nesne.

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*hWnd*  
Var olan bir pencere için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir başvuru döndürür `CAxWindow` nesne.

##  <a name="querycontrol"></a>  CAxWindow::QueryControl

Belirtilen barındırılan denetim arabiriminin alır.

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>Parametreler

*IID*  
[in] Denetimin arabirimi Laboratuvardaki belirtir.

*ppUnk*  
[out] Denetimin bir arabirim işaretçisi. Bu yöntem şablon sürümünü gerek yoktur başvuru kimliği için belirlenmiş bir arabirim ile ilişkili bir UUID geçirilen sürece.

*Q*  
[in] İçin sorgulanan arabirim.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="queryhost"></a>  CAxWindow::QueryHost

Ana bilgisayarın belirtilen arabirim döndürür.

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>Parametreler

*IID*  
[in] Denetimin arabirimi Laboratuvardaki belirtir.

*ppUnk*  
[out] Konak üzerindeki arabirim işaretçisi. Bu yöntem şablon sürümünü gerek yoktur başvuru kimliği için belirlenmiş bir arabirim ile ilişkili bir UUID geçirilen sürece.

*Q*  
[in] İçin sorgulanan arabirim.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Konağın arabirimi tarafından uygulanan penceresi barındırma kodu temel işlevselliğini erişime `AxWin`.

##  <a name="setexternaldispatch"></a>  CAxWindow::SetExternalDispatch

Dış gönderme arabirimi ayarlar `CAxWindow` nesne.

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*  
[in] Bir işaretçi bir `IDispatch` arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="setexternaluihandler"></a>  CAxWindow::SetExternalUIHandler

Dış ayarlar [Idochostuıhandlerdispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) için arabirim `CAxWindow` nesne.

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>Parametreler

*pUIHandler*  
[in] Bir işaretçi bir `IDocHostUIHandlerDispatch` arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Dış `IDocHostUIHandlerDispatch` arabirimi ana bilgisayarın site için sorgu denetimler tarafından kullanılır `IDocHostUIHandlerDispatch` arabirimi. WebBrowser denetimi bunu yapan bir denetimdir.

## <a name="see-also"></a>Ayrıca Bkz.

[ATLCON örnek](../../visual-cpp-samples.md)   
[CWindow sınıfı](../../atl/reference/cwindow-class.md)   
[Bileşik Denetim temelleri](../../atl/atl-composite-control-fundamentals.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)   
[Denetim kapsamı SSS](../../atl/atl-control-containment-faq.md)

