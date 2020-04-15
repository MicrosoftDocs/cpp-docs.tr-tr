---
title: IAxWinHostWindow Arabirimi
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
ms.openlocfilehash: ebecc611660a788ce59bb11beb95bd60eacaf01b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329992"
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow Arabirimi

Bu arabirim, bir denetimi ve ana bilgisayar nesnesini işlemek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Ekteki Kontrol](#attachcontrol)|Varolan bir denetimi ana bilgisayar nesnesine bağlar.|
|[Createcontrol](#createcontrol)|Denetim oluşturur ve ana bilgisayar nesnesine bağlar.|
|[CreateControlEx](#createcontrolex)|Denetim oluşturur, ana bilgisayar nesnesine bağlar ve isteğe bağlı olarak bir olay işleyicisi kurar.|
|[SorguDenetimi](#querycontrol)|Bir arabirim işaretçisini barındırılan denetime döndürür.|
|[SetExternalDispatch](#setexternaldispatch)|Dış `IDispatch` arabirimi ayarlar.|
|[SetExternalUIHandler](#setexternaluihandler)|Dış `IDocHostUIHandlerDispatch` arabirimi ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, ATL'nin ActiveX denetim barındırma nesneleri tarafından ortaya çıkarır. Barındırılan bir denetim oluşturmak ve/veya ana bilgisayar nesnesine denetim eklemek, barındırılan denetimden bir arabirim almak veya Web tarayıcısını barındırırken kullanılmak üzere harici arabirimi veya Kullanıcı Arabirimi işleyicisini ayarlamak için bu arabirimdeki yöntemleri çağırın.

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı aşağıda gösterildiği gibi IDL veya C++ olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|ıdl|ATLIFace.idl|
|C++|ATLIFace.h (Ayrıca ATLBase.h dahil)|

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a>IAxWinHostWindow::AttachControl

*hWnd*tarafından tanımlanan pencereyi kullanarak ana bilgisayar nesnesine varolan (ve daha önce başlatma) bir denetim bağlar.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*pUnkKontrol*<br/>
[içinde] Ana bilgisayar `IUnknown` nesnesine eklenecek denetimin arabirimine işaretçi.

*Hwnd*<br/>
[içinde] Barındırma için kullanılacak pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a>IAxWinHostWindow::CreateControl

Bir denetim oluşturur, başharflerini ilke landırır ve *hWnd*tarafından tanımlanan pencerede barındırışlar.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*lpTricsData*<br/>
[içinde] Oluşturmak için denetimi tanımlayan bir dize. CLSID (ayraçları içermelidir), ProgID, URL veya ham HTML **(MSHTML**tarafından önceden belirlenmiş: ) olabilir.

*Hwnd*<br/>
[içinde] Barındırma için kullanılacak pencerenin tutamacı.

*pStream*<br/>
[içinde] Denetim için başlatma verilerini içeren bir akış için arabirim işaretçisi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu pencere, iletilerin denetime yansıtılabilmesi ve diğer kapsayıcı özelliklerinin çalışabilmesi için bu arabirimi açığa çıkaran ana bilgisayar nesnesi tarafından alt sınıflanır.

Bu yöntemi arama [iAxWinHostWindow arama eşdeğerdir::CreateControlEx](#createcontrolex).

Lisanslı activex denetimi oluşturmak için Bkz. [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a>IAxWinHostWindow:CreateControlEx

ActiveX denetimi oluşturur, başlatılmasını sağlar ve [iAxWinHostWindow](#createcontrol)benzer belirtilen pencerede barındırır::CreateControl .

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>Parametreler

*lpTricsData*<br/>
[içinde] Oluşturmak için denetimi tanımlayan bir dize. CLSID (ayraçlar dahil olmalıdır), ProgID, URL veya ham HTML **(MSHTML**ile önceden belirlenmiş: ) olabilir.

*Hwnd*<br/>
[içinde] Barındırma için kullanılacak pencerenin tutamacı.

*pStream*<br/>
[içinde] Denetim için başlatma verilerini içeren bir akış için arabirim işaretçisi. NULL olabilir.

*ppUnk*<br/>
[çıkış] Oluşturulan denetimin arabirimini `IUnknown` alacak bir işaretçinin adresi. NULL olabilir.

*riidAdvise*<br/>
[içinde] İçe çıkan nesne üzerinde giden bir arabirimin arabirim tanımlayıcısı. IID_NULL olabilir.

*punkAdvise*<br/>
[içinde] Tarafından belirtilen `iidSink` `IUnknown` yer alan nesnenin bağlantı noktasına bağlanacak lavabo nesnesinin arabirimine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yöntemin `CreateControl` aksine, `CreateControlEx` aynı zamanda yeni oluşturulan denetim için bir arabirim işaretçisi almak ve denetim tarafından ateşlenen olayları almak için bir olay lavabo kurmak sağlar.

Lisanslı activex denetimi oluşturmak için Bkz. [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a>IAxWinHostWindow::QueryControl

Barındırılan denetim tarafından sağlanan belirtilen arabirim işaretçisini döndürür.

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
[içinde] İstenmekte olan denetimdeki arabirimin kimliği.

*ppvNesne*<br/>
[çıkış] Oluşturulan denetimin belirtilen arabirimini alacak bir işaretçinin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch

[IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) yöntemi ile denetimleri içerebilecek harici dispinterface'i ayarlar.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
[içinde] `IDispatch` Arabirime işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler

Nesne için harici [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) arabirimini `CAxWindow` ayarlamak için bu işlevi arayın.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
[içinde] `IDocHostUIHandlerDispatch` Arabirime işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `IDocHostUIHandlerDispatch` arabirim için ana bilgisayar sitesini sorgulayan denetimler (Web tarayıcıdenetimi gibi) tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[IAxWinAmbientDispatch Arabirimi](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
