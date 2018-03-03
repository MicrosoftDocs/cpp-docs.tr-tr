---
title: "Bileşik Denetim genel işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
dev_langs:
- C++
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d5a062ea9477df9db026c75bc775df804ed86da4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="composite-control-global-functions"></a>Bileşik Denetim genel işlevler
Bu işlevler ve oluşturma, barındırma ve ActiveX denetimlerini lisanslama iletişim kutuları oluşturma için destek sağlar.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarda aşağıdaki tabloda listelenen işlevleri kullanılamaz.  
  
|||  
|-|-|  
|[AtlAxDialogBox](#atlaxdialogbox)|Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan kalıcı bir iletişim kutusu oluşturur. Ortaya çıkan iletişim kutusunda ActiveX denetimlerini içerebilir.|  
|[AtlAxCreateDialog](#atlaxcreatedialog)|Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan modsuz bir iletişim kutusu oluşturur. Ortaya çıkan iletişim kutusunda ActiveX denetimlerini içerebilir.|  
|[AtlAxCreateControl](#atlaxcreatecontrol)|Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|  
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|ActiveX denetimi oluşturur, bunu başlatır, belirtilen penceresinde barındıran ve bir arabirim işaretçisi (veya işaretçileri) denetimden alır.|  
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|  
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, bunu başlatır, belirtilen penceresinde barındıran ve bir arabirim işaretçisi (veya işaretçileri) denetimden alır.|  
|[AtlAxAttachControl](#atlaxattachcontrol)|Önceden oluşturulmuş bir denetimi belirtilen pencereye ekler.|  
|[AtlAxGetHost](#atlaxgethost)|Belirli bir pencere (varsa), kapsayıcı doğrudan arabirimi işaretçisi almak için kullanılan, tanıtıcısını verilir.|  
|[AtlAxGetControl](#atlaxgetcontrol)|Belirli bir pencere içinde (varsa), içerdiği denetlemek için doğrudan arabirim işaretçisi almak için kullanılan, tanıtıcısını verilir.|  
|[AtlSetChildSite](#atlsetchildsite)|Başlatır **IUnknown** alt sitenin.|  
|[AtlAxWinInit](#atlaxwininit)|Barındırma kodu AxWin nesneler için başlatır.|  
|[AtlAxWinTerm](#atlaxwinterm)|Barındırma kodu AxWin nesneler için uninitializes.|  
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Bir nesnenin varsayılan kaynak arabirimi hakkında bilgi döndürür.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlhost.h  

##  <a name="atlaxdialogbox"></a>AtlAxDialogBox  
 Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan kalıcı bir iletişim kutusu oluşturur.  
   
```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstance`  
 [in] İletişim kutusu şablonu olan yürütülebilir dosya içermiyor modülü bir örneğini tanımlar.  
  
 `lpTemplateName`  
 [in] İletişim kutusu şablonu tanımlar. Bu parametre, iletişim kutusu şablonunun adını belirten null olarak sonlandırılan bir karakter dizesine işaretçi ya da iletişim kutusunda şablonu kaynak tanıtıcısı belirten bir tamsayı değeri değil. Parametre bir kaynak tanımlayıcısı belirtiyorsa, yüksek sıralı word sıfır olmalıdır ve düşük düzey word tanımlayıcısını içermelidir. Kullanabileceğiniz [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) makrosu bu değeri oluşturun.  
  
 `hWndParent`  
 [in] İletişim kutusu sahibi penceresi tanımlar.  
  
 `lpDialogProc`  
 [in] İletişim kutusu yordamı noktalarına. İletişim kutusu yordam hakkında daha fazla bilgi için bkz: [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] İletişim kutusuna geçirmek için kullanılacak değeri belirtir **lParam** parametresinin **WM_INITDIALOG** ileti.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılacak **AtlAxDialogBox** bir ActiveX denetimini içeren bir iletişim şablonunu ile geçerli bir belirtin **CLSID**, **APPID** veya URL dizesi olarak *metin* alanını **denetim** "AtlAxWin80" birlikte iletişim kutusu kaynağı bölümünü *sınıf adı* aynı bölüm altında. Aşağıdaki hangi geçerli bir gösteren **denetim** bölüm gibi görünebilir:  
  
```  
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,  
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100  
```  
  
 Kaynak komut dosyalarını düzenleme ile ilgili daha fazla bilgi için bkz: [nasıl yapılır: kaynak betik dosyasını metin biçiminde açma](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Denetim kaynak tanımı deyimleri hakkında daha fazla bilgi için bkz: [ortak denetim parametreleri](http://msdn.microsoft.com/library/windows/desktop/aa380902) Windows SDK altında*: SDK Araçları*.  
  
 Genel iletişim kutularında üzerinde daha fazla bilgi için bkz [iletişim](http://msdn.microsoft.com/library/windows/desktop/ms645452) ve [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) Windows SDK'sındaki.  
  
##  <a name="atlaxcreatedialog"></a>AtlAxCreateDialog  
 Kullanıcı tarafından sağlanan bir iletişim kutusu şablonundan modsuz bir iletişim kutusu oluşturur.  
  
```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstance`  
 [in] İletişim kutusu şablonu olan yürütülebilir dosya içermiyor modülü bir örneğini tanımlar.  
  
 `lpTemplateName`  
 [in] İletişim kutusu şablonu tanımlar. Bu parametre, iletişim kutusu şablonunun adını belirten null olarak sonlandırılan bir karakter dizesine işaretçi ya da iletişim kutusunda şablonu kaynak tanıtıcısı belirten bir tamsayı değeri değil. Parametre bir kaynak tanımlayıcısı belirtiyorsa, yüksek sıralı word sıfır olmalıdır ve düşük düzey word tanımlayıcısını içermelidir. Kullanabileceğiniz [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) makrosu bu değeri oluşturun.  
  
 `hWndParent`  
 [in] İletişim kutusu sahibi penceresi tanımlar.  
  
 `lpDialogProc`  
 [in] İletişim kutusu yordamı noktalarına. İletişim kutusu yordam hakkında daha fazla bilgi için bkz: [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] İletişim kutusuna geçirmek için kullanılacak değeri belirtir **lParam** parametresinin **WM_INITDIALOG** ileti.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Ortaya çıkan iletişim kutusunda ActiveX denetimlerini içerebilir.  
  
 Bkz: [CreateDialog](http://msdn.microsoft.com/library/windows/desktop/ms645434) ve [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) Windows SDK.  
  
##  <a name="atlaxcreatecontrol"></a>AtlAxCreateControl  
 Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.  
  

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Denetime geçirilecek bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:  
  
-   Bir ProgID gibi "MSCAL. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID  
  
-   "Http://www.microsoft.com" gibi bir URL  
  
-   Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"  
  
-   HTML gibi bir parçasını "MSHTML:\<HTML >\<gövde > metin satırının budur\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML akış olduğu atanır böylece HTML parçasını gelmelidir.  
  
 `hWnd`  
 [in] Denetim iliştirilmiş penceresine işleyin.  
  
 `pStream`  
 [in] Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. Olabilir **NULL**.  
  
 `ppUnkContainer`  
 [out] Alacak bir işaretçi adresini **IUnknown** kapsayıcısının. Olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genel işlev çağırma aynı sonucu verir [AtlAxCreateControlEx](#atlaxcreatecontrolex)( `lpszName` **,** `hWnd` **,** `pStream` **, NULL, NULL, NULL, NULL** );.  
  
 Lisanslı bir ActiveX denetimi oluşturmak için bkz: [AtlAxCreateControlLic](#atlaxcreatecontrollic).  
  
##  <a name="atlaxcreatecontrolex"></a>AtlAxCreateControlEx  
 Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır. Yeni denetim için bir arabirim işaretçisi ve olay havuzu da oluşturulabilir.  
  
```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Denetime geçirilecek bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:  
  
-   Bir ProgID gibi "MSCAL. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID  
  
-   "Http://www.microsoft.com" gibi bir URL  
  
-   Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"  
  
-   HTML gibi bir parçasını "MSHTML:\<HTML >\<gövde > metin satırının budur\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML akış olduğu atanır böylece HTML parçasını gelmelidir.  
  
 `hWnd`  
 [in] Denetim iliştirilmiş penceresine işleyin.  
  
 `pStream`  
 [in] Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. Olabilir **NULL**.  
  
 `ppUnkContainer`  
 [out] Alacak bir işaretçi adresini **IUnknown** kapsayıcısının. Olabilir **NULL**.  
  
 `ppUnkControl`  
 [out] Alacak bir işaretçi adresini **IUnknown** oluşturulan denetim. Olabilir **NULL**.  
  
 `iidSink`  
 Kapsanan nesne giden bir arabirimde arabirimi tanımlayıcısı.  
  
 *punkSink*  
 Bir işaretçi **IUnknown** arabirimi tarafından belirtilen bağlantı noktası bağlanması için havuz nesnesinin `iidSink` kapsanan nesne başarıyla oluşturulduktan sonra içerilen nesne üzerinde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlAxCreateControlEx`benzer [AtlAxCreateControl](#atlaxcreatecontrol) ancak aynı zamanda yeni oluşturulan denetlemek için bir arabirim işaretçisi almak ve denetim tarafından tetiklenen olayları almak için bir olay iç havuz ayarlamanıza olanak verir.  
  
 Lisanslı bir ActiveX denetimi oluşturmak için bkz: [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).  
  
##  <a name="atlaxcreatecontrollic"></a>AtlAxCreateControlLic  
 Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.  

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Denetime geçirilecek bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:  
  
-   Bir ProgID gibi "MSCAL. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID  
  
-   "Http://www.microsoft.com" gibi bir URL  
  
-   Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"  
  
-   HTML gibi bir parçasını "MSHTML:\<HTML >\<gövde > metin satırının budur\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML akış olduğu atanır böylece HTML parçasını gelmelidir.  
  
 `hWnd`  
 Denetim iliştirilmiş penceresine işleyin.  
  
 `pStream`  
 Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. Olabilir **NULL**.  
  
 `ppUnkContainer`  
 Alacak bir işaretçi adresini **IUnknown** kapsayıcısının. Olabilir **NULL**.  
  
 `bstrLic`  
 Denetim lisansını içeren BSTR.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) nasıl kullanılacağına ilişkin bir örnek için `AtlAxCreateControlLic`.  
  
##  <a name="atlaxcreatecontrollicex"></a>AtlAxCreateControlLicEx  
 Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır. Yeni denetim için bir arabirim işaretçisi ve olay havuzu da oluşturulabilir.  
  
```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Denetime geçirilecek bir dize için bir işaretçi. Aşağıdaki yollardan biriyle biçimlendirilmiş olması gerekir:  
  
-   Bir ProgID gibi "MSCAL. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}" gibi bir CLSID  
  
-   "Http://www.microsoft.com" gibi bir URL  
  
-   Etkin belge gibi bir başvuru "file://\\\Documents\MyDoc.doc"  
  
-   HTML gibi bir parçasını "MSHTML:\<HTML >\<gövde > metin satırının budur\</BODY >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML akış olduğu atanır böylece HTML parçasını gelmelidir.  
  
 `hWnd`  
 Denetim iliştirilmiş penceresine işleyin.  
  
 `pStream`  
 Denetimin özelliklerini başlatmak için kullanılan bir akış için bir işaretçi. Olabilir **NULL**.  
  
 `ppUnkContainer`  
 Alacak bir işaretçi adresini **IUnknown** kapsayıcısının. Olabilir **NULL**.  
  
 `ppUnkControl`  
 [out] Alacak bir işaretçi adresini **IUnknown** oluşturulan denetim. Olabilir **NULL**.  
  
 `iidSink`  
 Kapsanan nesne giden bir arabirimde arabirimi tanımlayıcısı.  
  
 *punkSink*  
 Bir işaretçi **IUnknown** arabirimi tarafından belirtilen bağlantı noktası bağlanması için havuz nesnesinin `iidSink` kapsanan nesne başarıyla oluşturulduktan sonra içerilen nesne üzerinde.  
  
 `bstrLic`  
 Denetim lisansını içeren BSTR.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlAxCreateControlLicEx`benzer [AtlAxCreateControlLic](#atlaxcreatecontrollic) ancak aynı zamanda yeni oluşturulan denetlemek için bir arabirim işaretçisi almak ve denetim tarafından tetiklenen olayları almak için bir olay iç havuz ayarlamanıza olanak verir.  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) nasıl kullanılacağına ilişkin bir örnek için `AtlAxCreateControlLicEx`.  
  
##  <a name="atlaxattachcontrol"></a>AtlAxAttachControl  
 Önceden oluşturulmuş bir denetimi belirtilen pencereye ekler.  
  
```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Parametreler  
 `pControl`  
 [in] Bir işaretçi **IUnknown** denetimi.  
  
 `hWnd`  
 [in] Denetim barındıracak penceresine işleyin.  
  
 `ppUnkContainer`  
 [out] Bir işaretçi bir işaretçi **IUnknown** kapsayıcı nesnesinin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [AtlAxCreateControlEx](#atlaxcreatecontrolex) ve [AtlAxCreateControl](#atlaxcreatecontrol) aynı anda oluşturmak ve bir denetim eklemek için.  
  
> [!NOTE]
>  İliştirilmekte olan denetim nesne doğru çağırmadan önce başlatılmalıdır `AtlAxAttachControl`.  
  
##  <a name="atlaxgethost"></a>AtlAxGetHost  
 Belirli bir pencere için (varsa), kapsayıcıya tanıtıcısını göz önünde bulundurarak doğrudan bir arabirim işaretçisi alır.  
  
```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 `h`  
 [in] Denetimi barındırma penceresi için bir tanıtıcı.  
  
 `pp`  
 [out] **IUnknown** denetimin kapsayıcısının.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="atlaxgetcontrol"></a>AtlAxGetControl  
 Belirli bir pencere içinde yer alan denetim için, tanıcısını göz önünde bulundurarak doğrudan arabirim işaretçisi alır.  
  
```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>Parametreler  
 `h`  
 [in] Denetimi barındırma penceresi için bir tanıtıcı.  
  
 `pp`  
 [out] **IUnknown** barındırılan denetimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="atlsetchildsite"></a>AtlSetChildSite  
 Alt nesne için site ayarlamak için bu işlevi çağırmak **IUnknown** üst nesnenin.  
  
```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```  
  
### <a name="parameters"></a>Parametreler  
 *punkChild*  
 [in] Bir işaretçi **IUnknown** alt arabirimi.  
  
 `punkParent`  
 [in] Bir işaretçi **IUnknown** üst arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
##  <a name="atlaxwininit"></a>AtlAxWinInit  
 Bu işlev ATL'ın denetim kodu kaydederek barındırma başlatır **"AtlAxWin80"** ve **"AtlAxWinLic80"** penceresi özel pencere iletileri birkaç sınıfları.  
  
```
ATLAPI_(BOOL) AtlAxWinInit();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kod barındırma denetim başlatma başarılı olduğunda sıfır olmayan; Aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, API barındırma ATL Denetimi kullanmadan önce çağrılmalıdır. Bu işlev için bir çağrı aşağıdaki **"AtlAxWin"** pencere sınıfı çağrıları kullanılabilir [CreateWindow'u](http://msdn.microsoft.com/library/windows/desktop/ms632679) veya [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680), Windows SDK'ın açıklandığı gibi.  

##  <a name="atlaxwinterm"></a>AtlAxWinTerm  
 Bu işlev ATL'ın denetim kodu kaydını kaldırarak barındırma uninitializes **"AtlAxWin80"** ve **"AtlAxWinLic80"** pencere sınıfları.  
  
```
inline BOOL AtlAxWinTerm();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman döndürür **doğru**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca çağırır [UnregisterClass](http://msdn.microsoft.com/library/windows/desktop/ms644899) Windows SDK'ın açıklandığı gibi.  
  
 Aradığınız varsa var olan tüm ana bilgisayar windows yok sonra temizlemek için bu işlevi çağırmak [AtlAxWinInit](#atlaxwininit) ve artık ana bilgisayar windows oluşturmanız gerekir. Bu işlev çağrısı yok, işlem sonlandırıldığında pencere sınıfı otomatik olarak kaydı kaldırılacak.  
  
##  <a name="atlgetobjectsourceinterface"></a>AtlGetObjectSourceInterface  
 Bir nesnenin varsayılan kaynak arabirimi hakkında bilgi almak için bu işlevi çağırın.  
  
```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```  
  
### <a name="parameters"></a>Parametreler  
 `punkObj`  
 [in] Bilgi döndürülecek nesnesi için bir işaretçi.  
  
 `plibid`  
 [out] Kaynak arabirimi tanımını içeren tür kitaplığı kimliği için bir işaretçi.  
  
 `piid`  
 [out] Nesnenin varsayılan kaynak arabirimi arabirim kimliği için bir işaretçi.  
  
 *pdwMajor*  
 [out] Kaynak arabirimi tanımını içeren tür kitaplığı ana sürüm numarasını gösteren bir işaretçi.  
  
 *pdwMinor*  
 [out] Kaynak arabirimi tanımını içeren tür kitaplığı alt sürüm numarasını gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlGetObjectSourceInterface`Varsayılan kaynak arabirimi kitaplık kimliği ile birlikte ve ana arabirimi kimliği ve ikincil sürüm numaralarını arabirimi açıklayan tür kitaplığı sağlayabilir.  
  
> [!NOTE]
>  Bu işlev başarıyla istenen bilgileri almak, nesneyi temsil ettiği `punkObj` uygulamalıdır `IDispatch` (ve dönüş türü bilgileri aracılığıyla **IDispatch::GetTypeInfo**) artı ayrıca gerekir ya da uygulama `IProvideClassInfo2` veya `IPersist`. Kaynak arabirimi için tür bilgisi için tür bilgisi aynı tür kitaplığında olmalıdır `IDispatch`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir olay havuz sınıfı nasıl tanımlayabilir gösterir `CEasySink`, için geçirebilir şablon bağımsız değişken sayısı azaltır `IDispEventImpl` tam essentials için. `EasyAdvise`ve `EasyUnadvise` kullanmak `AtlGetObjectSourceInterface` başlatmak için [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) üyeleri çağırmadan önce [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) veya [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).  
  
 [!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)   
 [Bileşik Denetim Makroları](../../atl/reference/composite-control-macros.md)
