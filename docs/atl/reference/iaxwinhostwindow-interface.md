---
title: Iaxwinhostwindow arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bee312cd5e7a88dd0798778d5f8385df265d78a1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099784"
---
# <a name="iaxwinhostwindow-interface"></a>Iaxwinhostwindow arabirimi

Bu arabirim, Denetim ve onun ana nesneyi düzenlemek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AttachControl](#attachcontrol)|Varolan bir denetimi için konak nesnesi ekler.|
|[CreateControl](#createcontrol)|Bir denetimi oluşturur ve ana bilgisayar nesnesine iliştirir.|
|[CreateControlEx](#createcontrolex)|Bir denetimi oluşturur, ana bilgisayar nesnesine iliştirir ve isteğe bağlı olarak bir olay işleyicisini ayarlar.|
|[QueryControl](#querycontrol)|Barındırılan denetim için bir arabirim işaretçisini döndürür.|
|[SetExternalDispatch](#setexternaldispatch)|Dış ayarlar `IDispatch` arabirimi.|
|[SetExternalUIHandler](#setexternaluihandler)|Dış ayarlar `IDocHostUIHandlerDispatch` arabirimi.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, nesneler barındırma ATL'nin ActiveX denetimi tarafından kullanıma sunulur. Oluşturma ve/veya ana bilgisayar nesnesine bir arabirim barındırılan denetimden almak ya da dış dispinterface veya kullanıcı Arabirimi işleyicisi kullanmak için Web tarayıcısını barındırırken ayarlamak için bir denetim eklemek için bu arabirimdeki yöntemleri çağırın.

## <a name="requirements"></a>Gereksinimler

Bu arabirim tanımı aşağıda gösterildiği gibi IDL veya C++ olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|ATLIFace.h (ATLBase.h içinde de dahil)|

##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl

Var olan (ve daha önce başlatılmış) bir denetim tarafından tanımlanan penceresini kullanarak konak nesnesi ekler *hWnd*.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*pUnkControl*<br/>
[in] Bir işaretçi `IUnknown` konak nesnesine eklenecek denetimin arabirimi.

*hWnd*<br/>
[in] Tanıtıcı penceresine barındırmak için kullanılacak.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="createcontrol"></a>  IAxWinHostWindow::CreateControl

Bir denetimi oluşturur, onu başlatır ve tarafından tanımlanan penceresinde barındıran *hWnd*.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*lpTricsData*<br/>
[in] Denetimi oluşturmak için tanımlayan bir dize. (Küme ayraçları içermelidir) CLSID, program kimliği, URL veya ham HTML olabilir (önek **MSHTML:**).

*hWnd*<br/>
[in] Tanıtıcı penceresine barındırmak için kullanılacak.

*pStream*<br/>
[in] Denetim için başlatma verilerini içeren bir akış için bir arabirim işaretçisi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bu pencere, bu arabirim iletilerin denetimine yansıtılır ve diğer kapsayıcı özellikleri çalışır böylece gösterme konak nesnesi tarafından sınıflandırma.

Bu yöntemin çağrılması için arama eşdeğer [IAxWinHostWindow::CreateControlEx](#createcontrolex).

Lisanslı bir ActiveX denetimi oluşturmak için bkz [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

##  <a name="createcontrolex"></a>  IAxWinHostWindow::CreateControlEx

Bir ActiveX denetimi oluşturur, onu başlatır ve benzer şekilde belirtilen pencerede barındırır [IAxWinHostWindow::CreateControl](#createcontrol).

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
[in] Denetimi oluşturmak için tanımlayan bir dize. (Küme ayraçları içermelidir) CLSID, program kimliği, URL veya ham HTML olabilir (ön eki **MSHTML:**).

*hWnd*<br/>
[in] Tanıtıcı penceresine barındırmak için kullanılacak.

*pStream*<br/>
[in] Denetim için başlatma verilerini içeren bir akış için bir arabirim işaretçisi. NULL olabilir.

*ppUnk*<br/>
[out] Adresi alacak bir işaretçi `IUnknown` arabirimi oluşturulan denetimi. NULL olabilir.

*riidAdvise*<br/>
[in] Kapsanan nesne üzerinde giden bir arabirim arabirimi tanımlayıcısı. IID_NULL olabilir.

*punkAdvise*<br/>
[in] Bir işaretçi `IUnknown` arabirimi tarafından belirtilen kapsanan nesne üzerindeki bağlantı noktasına bağlı havuz nesnenin `iidSink`.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Farklı `CreateControl` yöntemi `CreateControlEx` de yeni oluşturulan denetime bir arabirim işaretçisi alır ve denetimi tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak sağlar.

Lisanslı bir ActiveX denetimi oluşturmak için bkz [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl

Barındırılan denetim tarafından sağlanan belirtilen arabirim işaretçisini döndürür.

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*riid*<br/>
[in] İstenen denetimin bir arabirim kimliği.

*ppvObject*<br/>
[out] Oluşturulan denetimi belirtilen arabirim alacak bir işaretçi adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch

Kapsanan denetimlere kullanılabilir olan dış dispinterface ayarlar [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) yöntemi.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
[in] Bir işaretçi bir `IDispatch` arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler

Dış ayarlamak için bu işlevi çağırın [Idochostuıhandlerdispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) için arabirim `CAxWindow` nesne.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
[in] Bir işaretçi bir `IDocHostUIHandlerDispatch` arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bu işlev ana bilgisayarın site için sorgu denetimler (örneğin, Web tarayıcı denetimi) tarafından kullanılan `IDocHostUIHandlerDispatch` arabirimi.

## <a name="see-also"></a>Ayrıca Bkz.

[IAxWinAmbientDispatch Arabirimi](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)

