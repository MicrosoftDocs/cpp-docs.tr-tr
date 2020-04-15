---
title: CAxWindow Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
ms.openlocfilehash: 6f5629370bc1f821dac0a08cc76b5df1450f7a5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318730"
---
# <a name="caxwindow-class"></a>CAxWindow Sınıfı

Bu sınıf, ActiveX denetimi barındıran bir pencereyi işlemek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAxWindow : public CWindow
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Ekteki Kontrol](#attachcontrol)|Nesneye varolan bir ActiveX denetimini `CAxWindow` bağlar.|
|[CAxWindow](#caxwindow)|Bir `CAxWindow` nesne inşa eder.|
|[Createcontrol](#createcontrol)|ActiveX denetimi oluşturur, başlatılmasını sağlar ve `CAxWindow` pencerede barındırır.|
|[CreateControlEx](#createcontrolex)|ActiveX denetimi oluşturur ve denetimden bir arabirim işaretçisi (veya işaretçisi) alır.|
|[GetWndClassName](#getwndclassname)|(Statik) `CAxWindow` Nesnenin önceden tanımlanmış sınıf adını alır.|
|[SorguDenetimi](#querycontrol)|Barındırılan `IUnknown` ActiveX denetimini alır.|
|[QueryHost](#queryhost)|Nesnenin `IUnknown` işaretçisini `CAxWindow` alır.|
|[SetExternalDispatch](#setexternaldispatch)|Nesne tarafından kullanılan dış `CAxWindow` gönderme arabirimini ayarlar.|
|[SetExternalUIHandler](#setexternaluihandler)|Nesne tarafından `IDocHostUIHandler` kullanılan dış arabirimi ayarlar. `CAxWindow`|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Varolan `CAxWindow` bir nesneye BIR HWND atar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, ActiveX denetimi barındıran bir pencereyi işlemek için yöntemler sağlar. Barındırma tarafından sağlanmaktadır " **AtlAxWin80 ",** `CAxWindow`hangi tarafından sarılır .

`CAxWindowT` Sınıf, `CAxWindow` sınıfın uzmanlık alanı olarak uygulanır. Bu uzmanlık şu şekilde beyan edilir:

`typedef CAxWindowT<CWindow> CAxWindow;`

Taban sınıfı değiştirmeniz gerekiyorsa, yeni `CAxWindowT` taban sınıfı şablon bağımsız değişkeni olarak kullanabilir ve belirtebilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="caxwindowattachcontrol"></a><a name="attachcontrol"></a>CAxWindow::AttachControl

Biri zaten mevcut değilse yeni bir ana bilgisayar nesnesi oluşturur ve belirtilen denetimi ana bilgisayara bağlar.

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parametreler

*pKontrol*<br/>
[içinde] Denetimin işaretçisi. `IUnknown`

*ppUnkContainer*<br/>
[çıkış] Ana bilgisayar `IUnknown` `AxWin` (nesne) için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Eklenen denetim nesnesi aramadan `AttachControl`önce doğru bir şekilde başharfe alınmalıdır.

## <a name="caxwindowcaxwindow"></a><a name="caxwindow"></a>CAxWindow::CAxWindow

Varolan `CAxWindow` bir pencere nesnesi tutamacını kullanarak bir nesne oluşturuyor.

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Varolan bir pencere nesnesine bir tanıtıcı.

## <a name="caxwindowcreatecontrol"></a><a name="createcontrol"></a>CAxWindow::CreateControl

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

*Lpszname*<br/>
Denetimi oluşturmak için dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmelidir:

- Bir ProgID gibi`"MSCAL.Calendar.7"`

- Bir CLSID gibi`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- Gibi bir URL`"<https://www.microsoft.com>"`

- Aktif bir belgeye yapılan başvuru, örneğin`"file://\\\Documents\MyDoc.doc"`

- HTML gibi bir parçası`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML akışı olarak belirtilmek için HTML parçasından önce olmalıdır. Windows Mobile platformlarında yalnızca ProgID ve CLSID desteklenir. WINDOWS CE gömülü platformlar, CE IE desteği ile Windows Mobile dışında ProgID, CLSID, URL, etkin belgeye başvuru ve HTML parçası dahil olmak üzere her türlü desteği.

*pStream*<br/>
[içinde] Denetimin özelliklerini başlatmak için kullanılan bir akış için işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
[çıkış] Kapsayıcının `IUnknown` adresini alacak bir işaretçinin adresi. NULL olabilir.

*dwResID*<br/>
BIR HTML kaynağının kaynak kimliği. WebBrowser denetimi oluşturulur ve belirtilen kaynakla yüklenir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin ikinci sürümü kullanılırsa, bir HTML denetimi oluşturulur ve *dwResID*tarafından tanımlanan kaynağa bağlanır.

Bu yöntem, arama ile aynı sonucu verir:

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

Lisanslı activex denetimi oluşturmak, başlatmak ve barındırmak için [CAxWindow2T::CreateControlLic'e](../../atl/reference/caxwindow2t-class.md#createcontrollic) bakın.

### <a name="example"></a>Örnek

Kullanan `CreateControl`bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="caxwindowcreatecontrolex"></a><a name="createcontrolex"></a>CAxWindow::CreateControlEx

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

*Lpszname*<br/>
Denetimi oluşturmak için dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmelidir:

- Bir ProgID gibi`"MSCAL.Calendar.7"`

- Bir CLSID gibi`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- Gibi bir URL`"<https://www.microsoft.com>"`

- Aktif bir belgeye yapılan başvuru, örneğin`"file://\\\Documents\MyDoc.doc"`

- HTML gibi bir parçası`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML akışı olarak belirtilmek için HTML parçasından önce olmalıdır. Windows Mobile platformlarında yalnızca ProgID ve CLSID desteklenir. WINDOWS CE gömülü platformlar, CE IE desteği ile Windows Mobile dışında ProgID, CLSID, URL, etkin belgeye başvuru ve HTML parçası dahil olmak üzere her türlü desteği.

*pStream*<br/>
[içinde] Denetimin özelliklerini başlatmak için kullanılan bir akış için işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
[çıkış] Kapsayıcının `IUnknown` adresini alacak bir işaretçinin adresi. NULL olabilir.

*ppUnkKontrol*<br/>
[çıkış] Denetimin `IUnknown` adresini alacak bir işaretçinin adresi. NULL olabilir.

*iidSink*<br/>
[içinde] İçe çıkan nesne üzerinde giden bir arabirimin arabirim tanımlayıcısı. IID_NULL olabilir.

*punkSink*<br/>
[içinde] *iidSink* `IUnknown` tarafından belirtilen bulunan nesnenin bağlantı noktasına bağlanacak lavabo nesnesinin arabirimine bir işaretçi.

*dwResID*<br/>
[içinde] BIR HTML kaynağının kaynak kimliği. WebBrowser denetimi oluşturulur ve belirtilen kaynakla yüklenir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CAxWindow benzer::CreateControl](#createcontrol), ancak `CreateControlEx` bu yöntemin aksine, aynı zamanda yeni oluşturulan denetim için bir arabirim işaretçisi almak ve denetim tarafından ateşlenen olayları almak için bir olay lavabo kurmak sağlar.

Lisanslı activex denetimi oluşturmak, başlatmak ve barındırmak için [CAxWindow2T::CreateControlLicEx'e](../../atl/reference/caxwindow2t-class.md#createcontrollicex) bakın.

### <a name="example"></a>Örnek

Kullanan `CreateControlEx`bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="caxwindowgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow::GetWndClassName

Pencere sınıfının adını alır.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Dönüş Değeri

Lisanssız ActiveX denetimlerini barındırabilen pencere sınıfının adını içeren bir dize işaretçisi.

## <a name="caxwindowoperator-"></a><a name="operator_eq"></a>CAxWindow::operator =

Varolan `CAxWindow` bir nesneye BIR HWND atar.

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Varolan bir pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `CAxWindow` nesneye bir başvuru verir.

## <a name="caxwindowquerycontrol"></a><a name="querycontrol"></a>CAxWindow::QueryControl

Barındırılan denetimin belirtilen arabirimini alır.

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Denetimin arabiriminin IID'sini belirtir.

*ppUnk*<br/>
[çıkış] Denetimin arabirimine bir işaretçi. Bu yöntemin şablon sürümünde, ilişkili uUID içeren bir daktib arabirimi geçtiği sürece başvuru kimliğine gerek yoktur.

*S*<br/>
[içinde] Sorgulanan arabirim.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="caxwindowqueryhost"></a><a name="queryhost"></a>CAxWindow::QueryHost

Ana bilgisayar belirtilen arabirimini döndürür.

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Denetimin arabiriminin IID'sini belirtir.

*ppUnk*<br/>
[çıkış] Ana bilgisayardaki arabirime işaretçi. Bu yöntemin şablon sürümünde, ilişkili uUID içeren bir daktib arabirimi geçtiği sürece başvuru kimliğine gerek yoktur.

*S*<br/>
[içinde] Sorgulanan arabirim.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Ana bilgisayarın arabirimi, `AxWin`pencere barındırma kodunun altında yatan işlevsellik için .

## <a name="caxwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>CAxWindow::SetExternalDispatch

Nesne için dış gönderme `CAxWindow` arabirimini ayarlar.

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
[içinde] `IDispatch` Arabirime işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="caxwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>CAxWindow::SetExternalUIHandler

Nesne için harici [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) arabirimini `CAxWindow` ayarlar.

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>Parametreler

*pUIHandler*<br/>
[içinde] `IDocHostUIHandlerDispatch` Arabirime işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Dış `IDocHostUIHandlerDispatch` arabirim, `IDocHostUIHandlerDispatch` arabirim için ana bilgisayar sitesini sorgulayan denetimler tarafından kullanılır. WebBrowser denetimi bunu yapan bir denetimdir.

## <a name="see-also"></a>Ayrıca bkz.

[ATLCON Örneği](../../overview/visual-cpp-samples.md)<br/>
[CWindow Sınıfı](../../atl/reference/cwindow-class.md)<br/>
[Kompozit Kontrol Esasları](../../atl/atl-composite-control-fundamentals.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Kontrol Çevreleme SSS](../../atl/atl-control-containment-faq.md)
