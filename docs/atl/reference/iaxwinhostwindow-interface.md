---
title: IAxWinHostWindow arabirimi
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
ms.openlocfilehash: 44681b94e0bd1dfd757ebfa19f83074785dd95f5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833380"
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow arabirimi

Bu arabirim, bir denetimi ve konak nesnesini yönetmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[AttachControl](#attachcontrol)|Ana bilgisayar nesnesine varolan bir denetim ekler.|
|[CreateControl](#createcontrol)|Bir denetim oluşturur ve onu ana bilgisayar nesnesine ekler.|
|[CreateControlEx](#createcontrolex)|Bir denetim oluşturur, onu ana bilgisayar nesnesine ekler ve isteğe bağlı olarak bir olay işleyicisi ayarlar.|
|[QueryControl](#querycontrol)|Barındırılan denetime bir arabirim işaretçisi döndürür.|
|[SetExternalDispatch](#setexternaldispatch)|Dış arabirimi ayarlar `IDispatch` .|
|[Setexternaluıhandler](#setexternaluihandler)|Dış arabirimi ayarlar `IDocHostUIHandlerDispatch` .|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, ATL 'nin ActiveX denetimi barındırma nesneleri tarafından sunulur. Konak nesnesine bir denetim oluşturmak ve/veya bir denetim eklemek, barındırılan bir denetimden arabirim almak veya dış dispınterface veya Kullanıcı arabirimi işleyicisini Web tarayıcısını barındırırken kullanmak üzere ayarlamak için bu arabirimdeki yöntemleri çağırın.

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı aşağıda gösterildiği gibi IDL veya C++ olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|Atlıyüz. IDL|
|C++|Atlıyüz. h (ATLBase. h 'ye de dahildir)|

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a> IAxWinHostWindow:: AttachControl

*HWND*tarafından tanımlanan pencereyi kullanarak, mevcut (ve daha önce başlatılmış) bir denetimi ana bilgisayar nesnesine iliştirir.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*pUnkControl*<br/>
'ndaki `IUnknown` Ana bilgisayar nesnesine eklenecek denetimin arabirimine yönelik bir işaretçi.

*lendiği*<br/>
'ndaki Barındırma için kullanılacak pencereye yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a> IAxWinHostWindow:: CreateControl

Bir denetim oluşturur, onu başlatır ve *HWND*tarafından tanımlanan pencerede barındırır.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*Lplarincesdata*<br/>
'ndaki Oluşturulacak denetimi tanımlayan bir dize. Bir CLSID (küme ayraçları içermesi gerekir), ProgID, URL veya ham HTML (ön ek olarak **MSHTML:**) olabilir.

*lendiği*<br/>
'ndaki Barındırma için kullanılacak pencereye yönelik bir tanıtıcı.

*pStream*<br/>
'ndaki Denetim için başlatma verilerini içeren bir akış için arabirim işaretçisi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu pencere, iletilerin denetime yansıtılabilmesi ve diğer kapsayıcı özelliklerinin çalışması için bu arabirimi kullanıma sunan konak nesnesi tarafından alt sınıflandırılacak.

Bu yöntemi çağırmak, [IAxWinHostWindow:: CreateControlEx](#createcontrolex)çağırma ile eşdeğerdir.

Lisanslı bir ActiveX denetimi oluşturmak için, bkz. [ıaxwinhostwindowlik:: Createcontrollik](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a> IAxWinHostWindow:: CreateControlEx

Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede, [IAxWinHostWindow:: CreateControl](#createcontrol)öğesine benzer şekilde barındırır.

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

*Lplarincesdata*<br/>
'ndaki Oluşturulacak denetimi tanımlayan bir dize. Bir CLSID (küme ayraçları içermesi gerekir), ProgID, URL veya ham HTML (ön ek olarak **MSHTML:**) olabilir.

*lendiği*<br/>
'ndaki Barındırma için kullanılacak pencereye yönelik bir tanıtıcı.

*pStream*<br/>
'ndaki Denetim için başlatma verilerini içeren bir akış için arabirim işaretçisi. NULL olabilir.

*ppUnk*<br/>
dışı Oluşturulan denetimin arabirimini alacak bir işaretçinin adresi `IUnknown` . NULL olabilir.

*Riidadmenlik*<br/>
'ndaki Kapsanan nesnedeki bir giden arabirimin arabirim tanımlayıcısı. IID_NULL olabilir.

*punkAdvise*<br/>
'ndaki `IUnknown` Tarafından belirtilen kapsanan nesnedeki bağlantı noktasına bağlanacak havuz nesnesinin arabirimine yönelik bir işaretçi `iidSink` .

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yönteminden farklı olarak `CreateControl` , `CreateControlEx` Yeni oluşturulan denetime bir arabirim işaretçisi almanızı ve denetim tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak sağlar.

Lisanslı bir ActiveX denetimi oluşturmak için, bkz. [ıaxwinhostwindowlik:: CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a> IAxWinHostWindow:: QueryControl

Barındırılan denetim tarafından sunulan belirtilen arabirim işaretçisini döndürür.

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
'ndaki İstenen denetimdeki bir arabirimin KIMLIĞI.

*ppvObject*<br/>
dışı Oluşturulan denetimin belirtilen arabirimini alacak bir işaretçinin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a> IAxWinHostWindow:: SetExternalDispatch

[Idochostuihandlerdispatch:: GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) yöntemi aracılığıyla içerilen denetimler için kullanılabilen dış dispınterface 'i ayarlar.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
'ndaki Bir `IDispatch` arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a> IAxWinHostWindow:: Setexternaluıhandler

Nesnesi için dış [ıdochostuihandlerdispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) arabirimini ayarlamak için bu işlevi çağırın `CAxWindow` .

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
'ndaki Bir `IDocHostUIHandlerDispatch` arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, arabirim için konağın sitesini sorgulayan denetimler (Web tarayıcısı denetimi gibi) tarafından kullanılır `IDocHostUIHandlerDispatch` .

## <a name="see-also"></a>Ayrıca bkz.

[IAxWinAmbientDispatch arabirimi](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[CAxWindow:: QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
