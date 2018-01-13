---
title: "Cdialogımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
dev_langs: C++
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab4bb1e04bd21900cdf8d8122af51547e79aea22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdialogimpl-class"></a>Cdialogımpl sınıfı
Bu sınıf kalıcı veya geçici bir iletişim kutusu oluşturmak için yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 
template <class T,  
    class TBase = CWindow>  
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>  
 
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `CDialogImpl`.  
  
 *TBase*  
 Yeni sınıfın temel sınıf. Varsayılan taban sınıf [CWindow](../../atl/reference/cwindow-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Oluşturma](#create)|Kalıcı olmayan iletişim kutusu oluşturur.|  
|[DestroyWindow](#destroywindow)|Kalıcı olmayan iletişim kutusu yok eder.|  
|[DoModal](#domodal)|Modal bir iletişim kutusu oluşturur.|  
|[EndDialog](#enddialog)|Modal bir iletişim kutusu yok eder.|  
  
### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT yöntemleri  
  
|||  
|-|-|  
|[GetDialogProc](#getdialogproc)|Geçerli iletişim kutusu yordamı döndürür.|  
|[MapDialogRect](#mapdialogrect)|Belirtilen dikdörtgeninin iletişim kutusu birimleri ekran birimlerine (piksel) eşler.|  
|[OnFinalMessage](#onfinalmessage)|Genellikle son iletiyi aldıktan sonra adlı `WM_NCDESTROY`.|  
  
### <a name="static-functions"></a>Statik işlevler  
  
|||  
|-|-|  
|[DialogProc](#dialogproc)|İletişim kutusuna gönderilen iletileri işler.|  
|[StartDialogProc](#startdialogproc)|İletişim kutusuna gönderilen iletileri işlemek için ilk iletisi alındığında çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 İle `CDialogImpl` kalıcı veya geçici bir iletişim kutusu oluşturabilirsiniz. `CDialogImpl`Varsayılan ileti eşlemesi uygun işleyicileri iletilerini yönlendirmek için kullandığı iletişim kutusu yordam sağlar.  
  
 Taban sınıf yıkıcı **~ CWindowImplRoot** pencere nesnesi yok etme önce gittiğini sağlar.  
  
 `CDialogImpl`türetilen **CDialogImplBaseT**, hangi sırayla türetilen **CWindowImplRoot**.  
  
> [!NOTE]
>  Sınıfınızda tanımlamalısınız bir **IDD** üye iletişim şablonu kaynak kimliğini belirtir. Örneğin, ATL Proje Sihirbazı otomatik olarak sınıfınıza aşağıdaki satırı ekler:  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]  
  
 Burada `MyDlg` olan **kısa ad** sihirbazın içinde girilen **adları** sayfası.  
  
|Daha fazla bilgi|Bkz. |  
|--------------------------------|---------|  
|Denetimler oluşturma|[ATL öğretici](../../atl/active-template-library-atl-tutorial.md)|  
|ATL iletişim kutularında kullanma|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|  
|ATL Proje Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|  
|İletişim kutuları|[İletişim kutuları](http://msdn.microsoft.com/library/windows/desktop/ms632588) ve sonraki konularda Windows SDK'sı|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="create"></a>CDialogImpl::Create  
 Kalıcı olmayan iletişim kutusu oluşturur.  
  
```  
HWND Create(
    HWND hWndParent,  
    LPARAM dwInitParam = NULL );  

HWND Create(
    HWND hWndParent,  
    RECT&, 
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 [in] Sahibi penceresine işleci.  
  
 **RECT &**`rect`  
 [in] A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Yapısı iletişim kutusu boyutunu ve konumunu belirtme.  
  
 `dwInitParam`  
 [in] İletişim kutusuna geçirmek için kullanılacak değeri belirtir **lParam** parametresinin **WM_INITDIALOG** ileti.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan iletişim kutusu için tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu iletişim kutusu otomatik olarak bağlı `CDialogImpl` nesnesi. Modal bir iletişim kutusu oluşturmak için arama [DoModal](#domodal). Yalnızca yukarıda ikinci geçersiz kılma kullanılan [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="destroywindow"></a>CDialogImpl::DestroyWindow  
 Kalıcı olmayan iletişim kutusu yok eder.  
  
```  
 
BOOL DestroyWindow();

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** iletişim kutusu, başarılı bir şekilde yok aksi **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür **TRUE** iletişim kutusu, başarılı bir şekilde yok aksi **FALSE**.  
  
##  <a name="dialogproc"></a>CDialogImpl::DialogProc  
 Bu statik işlev iletişim kutusu yordamı uygular.  
  
```  
 
static LRESULT CALLBACK DialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam);

 
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 [in] İletişim kutusu için tanıtıcı.  
  
 `uMsg`  
 [in] İletişim kutusuna gönderilen ileti.  
  
 `wParam`  
 [in] Ek ileti özgü bilgiler.  
  
 `lParam`  
 [in] Ek ileti özgü bilgiler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** ileti, işlenen; Aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 `DialogProc`Varsayılan ileti eşlemesi uygun işleyicileri iletilerini yönlendirmek için kullanır.  
  
 Geçersiz kılabilirsiniz `DialogProc` iletileri işlemek için farklı bir mekanizma sağlamak için.  
  
##  <a name="domodal"></a>CDialogImpl::DoModal  
 Modal bir iletişim kutusu oluşturur.  
  
```   
INT_PTR DoModal(  
    HWND hWndParent = ::GetActiveWindow(),   
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 [in] Sahibi penceresine işleci. Varsayılan değer dönüş değeri [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 işlevi.  
  
 `dwInitParam`  
 [in] İletişim kutusuna geçirmek için kullanılacak değeri belirtir **lParam** parametresinin **WM_INITDIALOG** ileti.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, değeri `nRetCode` çağrısında belirtilen parametresi [EndDialog](#enddialog). Aksi durumda, -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu iletişim kutusu otomatik olarak bağlı `CDialogImpl` nesnesi.  
  
 Kalıcı olmayan iletişim kutusu oluşturmak için çağrı [oluşturma](#create).  
  
##  <a name="enddialog"></a>CDialogImpl::EndDialog  
 Modal bir iletişim kutusu yok eder.  
  
```   
BOOL EndDialog(int nRetCode); 
```  
  
### <a name="parameters"></a>Parametreler  
 `nRetCode`  
 [in] Tarafından döndürülecek değer [CDialogImpl::DoModal](#domodal).  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** iletişim kutusunu yok etme, aksi takdirde ise **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 `EndDialog`iletişim yordam boyunca çağrılmalıdır. İletişim kutusu yok sonra Windows değerini kullanır `nRetCode` dönüş değeri olarak `DoModal`, iletişim kutusu oluşturuldu.  
  
> [!NOTE]
>  Çağırmayın `EndDialog` kalıcı olmayan iletişim kutusunu yok etme. Çağrı [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) yerine.  
  
##  <a name="getdialogproc"></a>CDialogImpl::GetDialogProc  
 Döndürür `DialogProc`, geçerli iletişim kutusu yordamı.  
  
```   
virtual WNDPROC GetDialogProc(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli iletişim kutusu yordam.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim yordamı kendi değiştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="mapdialogrect"></a>CDialogImpl::MapDialogRect  
 (Maps) ekranına belirtilen dikdörtgeninin iletişim kutusu birimleri birimler (piksel) dönüştürür.  
  
```   
BOOL MapDialogRect(LPRECT lpRect); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret eden bir `CRect` nesne veya [RECT](../../mfc/reference/rect-structure1.md) güncelleştirme bölge barındırır güncelleştirme istemci koordinatları alacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirme başarılı olursa sıfır olmayan; güncelleştirmesi başarısız olursa 0. Genişletilmiş hata bilgilerini için arama `GetLastError`.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen koordinatlarında işlevi değiştirir `RECT` yapısı dönüştürülen koordinatlarıyla olanak sağlayan bir iletişim kutusu oluşturmak veya bir iletişim kutusu içinde bir denetim konumlandırmak için kullanılacak yapısı.  
  
##  <a name="onfinalmessage"></a>CDialogImpl::OnFinalMessage  
 Sıradaki son iletiyi aldıktan sonra adlı (genellikle `WM_NCDESTROY`).  
  
```   
virtual void OnFinalMessage(HWND hWnd); 
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 [in] Pencerenin yok için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik olarak nesnenizin pencere yok etme bağlı silmek istiyorsanız, çağırabilirsiniz Not `delete this;` burada.  
  
##  <a name="startdialogproc"></a>CDialogImpl::StartDialogProc  
 İlk ileti alındığında iletişim kutusuna gönderilen iletileri işlemek için yalnızca bir kez çağrılır.  
  
```   
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam); 
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 [in] İletişim kutusu için tanıtıcı.  
  
 `uMsg`  
 [in] İletişim kutusuna gönderilen ileti.  
  
 `wParam`  
 [in] Ek ileti özgü bilgiler.  
  
 `lParam`  
 [in] Ek ileti özgü bilgiler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencere yordamı.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk çağrısından sonra `StartDialogProc`, `DialogProc` iletişim yordam ve daha fazla çağrıları var. devam ederken ayarlanmadı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)