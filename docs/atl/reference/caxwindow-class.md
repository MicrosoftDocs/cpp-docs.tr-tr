---
title: CAxWindow sınıfı
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
ms.openlocfilehash: 6f5c178090a970906209e41da9298be61a61c639
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927852"
---
# <a name="caxwindow-class"></a>CAxWindow sınıfı

Bu sınıf, bir ActiveX denetimi barındıran pencereyi işlemek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAxWindow : public CWindow
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AttachControl](#attachcontrol)|`CAxWindow` Nesnesine var olan bir ActiveX denetimini ekler.|
|[CAxWindow](#caxwindow)|Bir `CAxWindow` nesnesi oluşturur.|
|[CreateControl](#createcontrol)|Bir ActiveX denetimi oluşturur, onu başlatır ve `CAxWindow` pencerede barındırır.|
|[CreateControlEx](#createcontrolex)|Bir ActiveX denetimi oluşturur ve denetimden bir arabirim işaretçisi (veya işaretçiler) alır.|
|[GetWndClassName](#getwndclassname)|Se `CAxWindow` Nesnenin önceden tanımlanmış sınıf adını alır.|
|[QueryControl](#querycontrol)|`IUnknown` Barındırılan ActiveX denetiminin öğesini alır.|
|[QueryHost](#queryhost)|`CAxWindow` Nesnenin `IUnknown` işaretçisini alır.|
|[SetExternalDispatch](#setexternaldispatch)|`CAxWindow` Nesne tarafından kullanılan dış dağıtım arabirimini ayarlar.|
|[Setexternaluıhandler](#setexternaluihandler)|Nesne tarafından kullanılan `IDocHostUIHandler` dış arabirimi ayarlar. `CAxWindow`|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Varolan `CAxWindow` bir nesneye HWND atar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, ActiveX denetimi barındıran bir pencereyi işlemek için yöntemler sağlar. Barındırma, tarafından `CAxWindow`Sarmalanan " **AtlAxWin80"** tarafından sağlanır.

Sınıf `CAxWindow` ,`CAxWindowT` sınıfının bir özelleştirmesi olarak uygulanır. Bu özelleşme şöyle bildirilmiştir:

`typedef CAxWindowT<CWindow> CAxWindow;`

Temel sınıfı değiştirmeniz gerekiyorsa, yeni temel sınıfı şablon bağımsız değişkeni olarak `CAxWindowT` kullanabilir ve belirtebilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="attachcontrol"></a>CAxWindow:: AttachControl

Henüz yoksa yeni bir ana bilgisayar nesnesi oluşturur ve belirtilen denetimi konağa iliştirir.

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
'ndaki Denetimin bir işaretçisi `IUnknown` .

*ppUnkContainer*<br/>
dışı Ana bilgisayarın işaretçisi `IUnknown` `AxWin` (nesne).

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

İliştirilmekte olan denetim nesnesi çağrılmadan `AttachControl`önce doğru şekilde başlatılmalıdır.

##  <a name="caxwindow"></a>CAxWindow:: CAxWindow

Varolan bir `CAxWindow` pencere nesne tutamacı kullanarak bir nesne oluşturur.

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Varolan bir pencere nesnesine yönelik bir tanıtıcı.

##  <a name="createcontrol"></a>CAxWindow:: CreateControl

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

*lpszName*<br/>
Denetimi oluşturmak için bir dizeye yönelik işaretçi. Aşağıdaki yollarla biçimlendirilmelidir:

- Gibi bir ProgID`"MSCAL.Calendar.7"`

- Gibi bir CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- Gibi bir URL`"<https://www.microsoft.com>"`

- Gibi etkin bir belgeye başvuru`"file://\\\Documents\MyDoc.doc"`

- Şöyle bir HTML parçası`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`bir MSHTML akışı olarak belirlenmiş olması için HTML parçasının önüne gelmelidir. Windows Mobile platformlarında yalnızca Progıd ve CLSID desteklenir. Windows CE yerleşik platformları, CE IE desteği olan Windows Mobile dışında, ProgID, CLSID, URL, etkin belgeye başvuru ve HTML parçası dahil olmak üzere tüm türleri destekler.

*pStream*<br/>
'ndaki Denetimin özelliklerini başlatmak için kullanılan akışa yönelik bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
dışı Kapsayıcının `IUnknown` konumunu alacak bir işaretçinin adresi. NULL olabilir.

*Dwresd*<br/>
Bir HTML kaynağının kaynak KIMLIĞI. WebBrowser denetimi oluşturulacak ve belirtilen kaynakla yüklenecek.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin ikinci sürümü kullanılırsa, bir HTML denetimi oluşturulur ve *Dwrestıd*tarafından tanımlanan kaynağa bağlanır.

Bu yöntem, arama ile aynı sonucu verir:

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

Lisanslı bir ActiveX denetimi oluşturmak, başlatmak ve barındırmak için bkz. [CAxWindow2T:: Createcontrollik](../../atl/reference/caxwindow2t-class.md#createcontrollic) .

### <a name="example"></a>Örnek

Tarafından kullanılan `CreateControl`bir örnek IÇIN bkz. [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) .

##  <a name="createcontrolex"></a>CAxWindow:: CreateControlEx

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

*lpszName*<br/>
Denetimi oluşturmak için bir dizeye yönelik işaretçi. Aşağıdaki yollarla biçimlendirilmelidir:

- Gibi bir ProgID`"MSCAL.Calendar.7"`

- Gibi bir CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- Gibi bir URL`"<https://www.microsoft.com>"`

- Gibi etkin bir belgeye başvuru`"file://\\\Documents\MyDoc.doc"`

- Şöyle bir HTML parçası`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`bir MSHTML akışı olarak belirlenmiş olması için HTML parçasının önüne gelmelidir. Windows Mobile platformlarında yalnızca Progıd ve CLSID desteklenir. Windows CE yerleşik platformları, CE IE desteği olan Windows Mobile dışında, ProgID, CLSID, URL, etkin belgeye başvuru ve HTML parçası dahil olmak üzere tüm türleri destekler.

*pStream*<br/>
'ndaki Denetimin özelliklerini başlatmak için kullanılan akışa yönelik bir işaretçi. NULL olabilir.

*ppUnkContainer*<br/>
dışı Kapsayıcının `IUnknown` konumunu alacak bir işaretçinin adresi. NULL olabilir.

*ppUnkControl*<br/>
dışı Denetimin `IUnknown` konumunu alacak bir işaretçinin adresi. NULL olabilir.

*ııdsink*<br/>
'ndaki Kapsanan nesnedeki bir giden arabirimin arabirim tanımlayıcısı. IID_NULL olabilir.

*punkSink*<br/>
'ndaki *Iıdsink*tarafından `IUnknown` belirtilen kapsanan nesnedeki bağlantı noktasına bağlanacak havuz nesnesinin arabirimine yönelik bir işaretçi.

*Dwresd*<br/>
'ndaki Bir HTML kaynağının kaynak KIMLIĞI. WebBrowser denetimi oluşturulacak ve belirtilen kaynakla yüklenecek.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CAxWindow:: CreateControl](#createcontrol)ile benzerdir, ancak bu yöntemin aksine, `CreateControlEx` yeni oluşturulan denetime bir arabirim işaretçisi almanızı ve denetim tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak sağlar.

Lisanslı bir ActiveX denetimi oluşturmak, başlatmak ve barındırmak için bkz. [CAxWindow2T:: CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) .

### <a name="example"></a>Örnek

Tarafından kullanılan `CreateControlEx`bir örnek IÇIN bkz. [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) .

##  <a name="getwndclassname"></a>CAxWindow:: GetWndClassName

Pencere sınıfının adını alır.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Dönüş Değeri

Lisanslı olmayan ActiveX denetimlerini barındırabilirler pencere sınıfının adını içeren bir dize işaretçisi.

##  <a name="operator_eq"></a>CAxWindow:: operator =

Varolan `CAxWindow` bir nesneye HWND atar.

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Varolan bir pencereye yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `CAxWindow` nesneye bir başvuru döndürür.

##  <a name="querycontrol"></a>CAxWindow:: QueryControl

Barındırılan denetimin belirtilen arabirimini alır.

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki Denetimin arabiriminin IID 'sini belirtir.

*ppUnk*<br/>
dışı Denetimin arabirimine yönelik bir işaretçi. Bu yöntemin şablon sürümünde, ilişkili UUID 'ye sahip bir tür arabirimi geçirildiğinden bir başvuru KIMLIĞI gerekmez.

*Ç*<br/>
'ndaki İçin sorgulanmakta olan arabirim.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="queryhost"></a>CAxWindow:: QueryHost

Konağın belirtilen arabirimini döndürür.

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki Denetimin arabiriminin IID 'sini belirtir.

*ppUnk*<br/>
dışı Konaktaki arabirime yönelik bir işaretçi. Bu yöntemin şablon sürümünde, ilişkili UUID 'ye sahip bir tür arabirimi geçirildiğinden bir başvuru KIMLIĞI gerekmez.

*Ç*<br/>
'ndaki İçin sorgulanmakta olan arabirim.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Konağın arabirimi, tarafından `AxWin`uygulanan pencere barındırma kodunun temel işlevlerine erişim sağlar.

##  <a name="setexternaldispatch"></a>CAxWindow:: SetExternalDispatch

`CAxWindow` Nesne için dış dağıtım arabirimini ayarlar.

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
'ndaki Bir `IDispatch` arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="setexternaluihandler"></a>CAxWindow:: Setexternaluıhandler

`CAxWindow` Nesnesi için dış [ıdochostuihandlerdispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) arabirimini ayarlar.

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>Parametreler

*Puıhandler*<br/>
'ndaki Bir `IDocHostUIHandlerDispatch` arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Dış `IDocHostUIHandlerDispatch` arabirim, konağın sitesini `IDocHostUIHandlerDispatch` arabirim için sorgulayan denetimler tarafından kullanılır. WebBrowser denetimi bunu yapan bir denetimdir.

## <a name="see-also"></a>Ayrıca bkz.

[ATLCON örneği](../../overview/visual-cpp-samples.md)<br/>
[CWindow Sınıfı](../../atl/reference/cwindow-class.md)<br/>
[Bileşik denetim temelleri](../../atl/atl-composite-control-fundamentals.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Denetim kapsama hakkında SSS](../../atl/atl-control-containment-faq.md)
