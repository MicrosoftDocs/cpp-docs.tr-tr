---
title: "CAxWindow sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8848e8ecf85b073032561e2db52a0db1889911e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="caxwindow-class"></a>CAxWindow sınıfı
Bu sınıf bir ActiveX denetimini barındıran bir pencere düzenleme için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAxWindow : public CWindow
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Varolan bir ActiveX denetimine iliştirir `CAxWindow` nesnesi.|  
|[CAxWindow](#caxwindow)|Oluşturan bir `CAxWindow` nesnesi.|  
|[CreateControl](#createcontrol)|ActiveX denetimi oluşturur, bunu başlatır ve içinde barındıran `CAxWindow` penceresi.|  
|[CreateControlEx](#createcontrolex)|ActiveX denetimi oluşturur ve bir arabirim işaretçisi (veya işaretçileri) denetimden alır.|  
|[GetWndClassName](#getwndclassname)|(Statik) Önceden tanımlanmış sınıf adını alır `CAxWindow` nesnesi.|  
|[QueryControl](#querycontrol)|Alır **IUnknown** barındırılan ActiveX denetiminin.|  
|[QueryHost](#queryhost)|Alır **IUnknown** işaretçisi `CAxWindow` nesnesi.|  
|[SetExternalDispatch](#setexternaldispatch)|Tarafından kullanılan dış dağıtma arabirimi ayarlar `CAxWindow` nesnesi.|  
|[SetExternalUIHandler](#setexternaluihandler)|Dış ayarlar **IDocHostUIHandler** tarafından kullanılan arabirimi `CAxWindow` nesnesi.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](#operator_eq)|Atayan bir **HWND** varolan bir **CAxWindow** nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir ActiveX denetimini barındıran bir pencere düzenleme için yöntemleri sağlar. Barındırma tarafından sağlanan " **AtlAxWin80"**, tarafından Sarmalanan `CAxWindow`.  
  
 Sınıf `CAxWindow` uzmanlaşması uygulanan `CAxWindowT` sınıfı. Bu uzmanlık olarak bildirilmiş:  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 Taban sınıfı değiştirmeniz gerekiyorsa, kullanabileceğiniz `CAxWindowT` ve şablon bağımsız değişken yeni taban sınıfı belirtin.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="attachcontrol"></a>CAxWindow::AttachControl  
 Bir zaten mevcut değilse ve belirtilen denetim ana bilgisayara bağlanan yeni bir ana bilgisayar nesnesi oluşturur.  
  
```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Parametreler  
 `pControl`  
 [in] Bir işaretçi **IUnknown** denetimi.  
  
 `ppUnkContainer`  
 [out] Bir işaretçi **IUnknown** ana bilgisayar ( **AxWin** nesnesi).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İliştirilmekte olan denetim nesne doğru çağırmadan önce başlatılmalıdır `AttachControl`.  
  
##  <a name="caxwindow"></a>CAxWindow::CAxWindow  
 Oluşturan bir `CAxWindow` var olan bir pencere nesnesi işleci kullanılarak nesne.  
  
```
CAxWindow(HWND hWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 Varolan bir pencere nesnesi için bir tanıtıcı.  
  
##  <a name="createcontrol"></a>CAxWindow::CreateControl  
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
 `lpszName`  
 Denetimi oluşturmak için bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:  
  
-   Bir ProgID gibi "MSCAL. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID  
  
-   "Http://www.microsoft.com" gibi bir URL  
  
-   Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"  
  
-   HTML gibi bir parçasını "MSHTML:\<HTML >\<gövde > metin satırının budur\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML akış olduğu atanır böylece HTML parçasını gelmelidir. Windows Mobile platformları yalnızca ProgID ve CLSID desteklenir. Windows CE embedded platformları, Windows Mobile CE IE desteği için destek ile dışında ProgID dahil olmak üzere tüm türleri CLSID, URL, başvuru etkin belgeyi ve HTML parçasını.  
  
 `pStream`  
 [in] Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. Olabilir **NULL**.  
  
 `ppUnkContainer`  
 [out] Alacak bir işaretçi adresini **IUnknown** kapsayıcısının. Olabilir **NULL**.  
  
 `dwResID`  
 Bir HTML kaynağının kaynak kimliği. WebBrowser denetimi oluşturulur ve belirtilen kaynakla yüklendi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ikinci sürümü kullanılırsa, bir HTML denetimini oluşturulur ve tarafından tanımlanan bir kaynağa bağlı `dwResID`.  
  
 Bu yöntem çağırma aynı sonucu verir:  
  
 [!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]  
  
 Bkz: [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) oluşturmak için başlatmak ve lisanslı bir ActiveX denetimi barındırır.  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CreateControl`.  
  
##  <a name="createcontrolex"></a>CAxWindow::CreateControlEx  
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
 `lpszName`  
 Denetimi oluşturmak için bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:  
  
-   Bir ProgID gibi "MSCAL. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID  
  
-   "Http://www.microsoft.com" gibi bir URL  
  
-   Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"  
  
-   HTML gibi bir parçasını "MSHTML:\<HTML >\<gövde > metin satırının budur\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML akış olduğu atanır böylece HTML parçasını gelmelidir. Windows Mobile platformları yalnızca ProgID ve CLSID desteklenir. Windows CE embedded platformları, Windows Mobile CE IE desteği için destek ile dışında ProgID dahil olmak üzere tüm türleri CLSID, URL, başvuru etkin belgeyi ve HTML parçasını.  
  
 `pStream`  
 [in] Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. Olabilir **NULL**.  
  
 `ppUnkContainer`  
 [out] Alacak bir işaretçi adresini **IUnknown** kapsayıcısının. Olabilir **NULL**.  
  
 `ppUnkControl`  
 [out] Alacak bir işaretçi adresini **IUnknown** denetimi. Olabilir **NULL**.  
  
 `iidSink`  
 [in] Kapsanan nesne giden bir arabirimde arabirimi tanımlayıcısı. Olabilir **IID_NULL**.  
  
 *punkSink*  
 [in] Bir işaretçi **IUnknown** arabirimi tarafından belirtilen kapsanan nesne bağlantı noktasında bağlanması için havuz nesnesinin `iidSink`.  
  
 `dwResID`  
 [in] Bir HTML kaynağının kaynak kimliği. WebBrowser denetimi oluşturulur ve belirtilen kaynakla yüklendi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem benzer [CAxWindow::CreateControl](#createcontrol), ancak bu yöntem aksine `CreateControlEx` ayrıca yeni oluşturulan denetlemek için bir arabirim işaretçisi almak ve denetim tarafından tetiklenen olayları almak için bir olay iç havuz ayarlamanıza olanak sağlar.  
  
 Bkz: [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) oluşturmak için başlatmak ve lisanslı bir ActiveX denetimi barındırır.  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CreateControlEx`.  
  
##  <a name="getwndclassname"></a>CAxWindow::GetWndClassName  
 Pencere sınıfı adını alır.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nonlicensed ActiveX denetimlerini barındırabilir pencere sınıfı adını içeren bir dize için bir işaretçi.  
  
##  <a name="operator_eq"></a>CAxWindow::operator =  
 Atayan bir `HWND` varolan bir `CAxWindow` nesnesi.  
  
```
CAxWindow<TBase>& operator=(HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 Varolan bir pencere için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir başvuru döndürür `CAxWindow` nesnesi.  
  
##  <a name="querycontrol"></a>CAxWindow::QueryControl  
 Belirtilen arabirim barındırılan denetimin alır.  
  
```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] Denetimin arabirimi IID belirtir.  
  
 `ppUnk`  
 [out] Arabirim denetimi için bir işaretçi. Bu yöntem şablon sürümde gerek yoktur başvuru kimliği için ilişkili bir UUID yazılan arabirimiyle geçirilen sürece.  
  
 `Q`  
 [in] İçin sorgulanan arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="queryhost"></a>CAxWindow::QueryHost  
 Ana bilgisayarın belirtilen arabirimini döndürür.  
  
```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] Denetimin arabirimi IID belirtir.  
  
 `ppUnk`  
 [out] Ana bilgisayarda arabirimi için bir işaretçi. Bu yöntem şablon sürümde gerek yoktur başvuru kimliği için ilişkili bir UUID yazılan arabirimiyle geçirilen sürece.  
  
 `Q`  
 [in] İçin sorgulanan arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Ana bilgisayar arabirimi tarafından uygulanan penceresi barındırma kodu temel işlevselliğini erişmesini sağlar **AxWin**.  
  
##  <a name="setexternaldispatch"></a>CAxWindow::SetExternalDispatch  
 Dış gönderme arabirimi ayarlar `CAxWindow` nesnesi.  
  
```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDisp`  
 [in] Bir işaretçi bir `IDispatch` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="setexternaluihandler"></a>CAxWindow::SetExternalUIHandler  
 Dış ayarlar [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) için arabirim `CAxWindow` nesnesi.  
  
```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUIHandler*  
 [in] Bir işaretçi bir **IDocHostUIHandlerDispatch** arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Dış `IDocHostUIHandlerDispatch` arabirimi ana bilgisayarın site için sorgu denetimleri tarafından kullanılan `IDocHostUIHandlerDispatch` arabirimi. WebBrowser denetimi bunu yapan bir denetimdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATLCON örnek](../../visual-cpp-samples.md)   
 [CWindow sınıfı](../../atl/reference/cwindow-class.md)   
 [Bileşik Denetim temelleri](../../atl/atl-composite-control-fundamentals.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Denetim kapsamı SSS](../../atl/atl-control-containment-faq.md)

