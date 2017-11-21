---
title: IAxWinHostWindow arabirimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
- No header/ATL::IAxWinHostWindow
- No header/ATL::AttachControl
- No header/ATL::CreateControl
- No header/ATL::CreateControlEx
- No header/ATL::QueryControl
- No header/ATL::SetExternalDispatch
- No header/ATL::SetExternalUIHandler
dev_langs: C++
helpviewer_keywords: IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 28fdc1a3a26fc2bb6117c345da3588ff0d2de193
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow arabirimi
Bu arabirim denetimi ve konak nesnesi düzenleme için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Varolan bir denetim ana bilgisayar nesnesine ekler.|  
|[CreateControl](#createcontrol)|Bir denetimi oluşturur ve ana bilgisayar nesnesine ekler.|  
|[CreateControlEx](#createcontrolex)|Bir denetimi oluşturur, ana bilgisayar nesnesine ekler ve isteğe bağlı olarak bir olay işleyicisini ayarlar.|  
|[QueryControl](#querycontrol)|Arabirim işaretçisi barındırılan denetime döndürür.|  
|[SetExternalDispatch](#setexternaldispatch)|Dış ayarlar `IDispatch` arabirimi.|  
|[SetExternalUIHandler](#setexternaluihandler)|Dış ayarlar `IDocHostUIHandlerDispatch` arabirimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim nesneleri barındırma ATL'in ActiveX denetimi tarafından sunulur. Oluşturma ve/veya ana bilgisayar nesnesine bir arabirim barındırılan denetimden almak veya dış görüntüleme arabirimi veya UI işleyicisi kullanmak için Web tarayıcısı barındırdığında ayarlamak için bir denetim eklemek için bu arabirimde yöntemlerini çağırın.  
  
## <a name="requirements"></a>Gereksinimler  
 Bu arabirim tanımı aşağıda gösterildiği gibi IDL ya da C++, kullanılabilir.  
  
|Tanım türü|Dosya|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h içinde de dahil)|  
  
##  <a name="attachcontrol"></a>IAxWinHostWindow::AttachControl  
 Var olan (ve daha önce başlatılmış) denetim tarafından tanımlanan penceresini kullanarak ana bilgisayar nesneye ekler `hWnd`.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnkControl*  
 [in] Bir işaretçi **IUnknown** ana bilgisayar nesnesine eklenecek denetiminin arabirimi.  
  
 `hWnd`  
 [in] Barındırma için kullanılacak penceresi için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="createcontrol"></a>IAxWinHostWindow::CreateControl  
 Bir denetimi oluşturur, bunu başlatır ve tarafından tanımlanan penceresinde barındıran `hWnd`.  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpTricsData`  
 [in] Oluşturulacak denetimin tanımlayan bir dize. (Köşeli parantez içermelidir) CLSID, ProgID, URL veya ham HTML olabilir (önüne **MSHTML:**).  
  
 `hWnd`  
 [in] Barındırma için kullanılacak penceresi için bir tanıtıcı.  
  
 `pStream`  
 [in] Arabirim işaretçisi denetimi için başlatma verilerini içeren bir akış için. Olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu pencere iletileri denetime yansıtılması ve diğer kapsayıcı özellikleri çalışır bu arabirimi gösterme ana bilgisayar nesnesi tarafından sınıflandırma.  
  
 Bu yöntemin çağrılması için arama eşdeğer [IAxWinHostWindow::CreateControlEx](#createcontrolex).  
  
 Lisanslı bir ActiveX denetimi oluşturmak için bkz: [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="createcontrolex"></a>IAxWinHostWindow::CreateControlEx  
 ActiveX denetimi oluşturur, bunu başlatır ve benzer belirtilen penceresinde barındıran [IAxWinHostWindow::CreateControl](#createcontrol).  
  
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
 `lpTricsData`  
 [in] Oluşturulacak denetimin tanımlayan bir dize. (Köşeli parantez içermelidir) CLSID, ProgID, URL veya ham HTML olabilir (önekine sahip **MSHTML:**).  
  
 `hWnd`  
 [in] Barındırma için kullanılacak penceresi için bir tanıtıcı.  
  
 `pStream`  
 [in] Arabirim işaretçisi denetimi için başlatma verilerini içeren bir akış için. Olabilir **NULL**.  
  
 `ppUnk`  
 [out] Alacak bir işaretçi adresini **IUnknown** oluşturulan denetiminin arabirimi. Olabilir **NULL**.  
  
 *riidAdvise*  
 [in] Kapsanan nesne giden bir arabirimde arabirimi tanımlayıcısı. Olabilir **IID_NULL**.  
  
 *punkAdvise*  
 [in] Bir işaretçi **IUnknown** arabirimi tarafından belirtilen kapsanan nesne bağlantı noktasında bağlanması için havuz nesnesinin `iidSink`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı `CreateControl` yöntemi, `CreateControlEx` ayrıca yeni oluşturulan denetlemek için bir arabirim işaretçisi almak ve denetim tarafından tetiklenen olayları almak için bir olay iç havuz ayarlamanıza olanak sağlar.  
  
 Lisanslı bir ActiveX denetimi oluşturmak için bkz: [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 Barındırılan denetim tarafından sağlanan belirtilen arabirim işaretçisi döndürür.  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `riid`  
 [in] İstenen denetim arabirime kimliği.  
  
 `ppvObject`  
 [out] Belirtilen arabirim oluşturulan denetiminin alacak bir işaretçi adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch  
 Kapsanan denetimlerine kullanılabilir olan dış görüntüleme arabirimi, ayarlar [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) yöntemi.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDisp`  
 [in] Bir işaretçi bir `IDispatch` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler  
 Dış ayarlamak için bu işlevi çağırmak [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) için arabirim `CAxWindow` nesnesi.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDisp`  
 [in] Bir işaretçi bir **IDocHostUIHandlerDispatch** arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev ana bilgisayarın site için sorgu denetimleri (örneğin, Web tarayıcısı denetimi) tarafından kullanılan `IDocHostUIHandlerDispatch` arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IAxWinAmbientDispatch arabirimi](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









