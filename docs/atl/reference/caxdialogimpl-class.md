---
title: "CAxDialogImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
dev_langs: C++
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6f11d86eda98696ea85899817dbecc276d5533a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl sınıfı
Bu sınıf, bir iletişim kutusu (kalıcı veya geçici) barındıran ActiveX denetimlerini uygular.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class TBase = CWindow>  
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `CAxDialogImpl`.  
  
 *TBase*  
 İçin temel pencere sınıfı **CDialogImplBaseT**.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Öneri veya nesnenin havuz olay eşlemini tüm girişler unadvise için bu yöntemi çağırın.|  
|[CAxDialogImpl::Create](#create)|Kalıcı olmayan iletişim kutusu oluşturmak için bu yöntemi çağırın.|  
|[CAxDialogImpl::DestroyWindow](#destroywindow)|Kalıcı olmayan iletişim kutusu yok etmek için bu yöntemi çağırın.|  
|[CAxDialogImpl::DoModal](#domodal)|Modal bir iletişim kutusu oluşturmak için bu yöntemi çağırın.|  
|[CAxDialogImpl::EndDialog](#enddialog)|Modal bir iletişim kutusu yok etmek için bu yöntemi çağırın.|  
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|Bir işaretçi almak için bu yöntemi çağırın `DialogProc` geri çağırma işlevi.|  
|[CAxDialogImpl::GetIDD](#getidd)|İletişim şablonu kaynak kimliği almak için bu yöntemi çağırın|  
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|Bu iletişim kutusu için bir ileti yönelik olduğunu belirlemek için bu yöntemi çağırın ve ise, ileti işlem.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAxDialogImpl::m_bModal](#m_bmodal)|Hata ayıklama yalnızca mevcut bir değişken oluşturur ve iletişim kutusunu kalıcı ise true olarak ayarlandı.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAxDialogImpl`kalıcı veya geçici bir iletişim kutusu oluşturmanıza olanak sağlar. `CAxDialogImpl`Varsayılan ileti eşlemesi uygun işleyicileri iletilerini yönlendirmek için kullandığı iletişim kutusu yordam sağlar.  
  
 `CAxDialogImpl`türetilen `CDialogImplBaseT`, hangi sırayla türetilen *TBase* (varsayılan olarak, `CWindow`) ve `CMessageMap`.  
  
 Sınıfınızda iletişim şablonu kaynak kimliğini belirtir. bir IDD üye tanımlamanız gerekir Örneğin, bir ATL iletişim kutusu kullanılarak nesne ekleme **sınıfı Ekle** iletişim kutusu otomatik olarak sınıfınıza aşağıdaki satırı ekler:  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]  
  
 Burada `MyDialog` olan **kısa ad** ATL iletişim sihirbazda girdiğiniz.  
  
 Bkz: [bir iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) daha fazla bilgi için.  
  
 Modal bir iletişim kutusu bir ActiveX denetimi ile oluşturulan Not `CAxDialogImpl` Hızlandırıcı tuşları desteklemez. Hızlandırıcı tuşları ile oluşturulan bir iletişim kutusu desteklemek için `CAxDialogImpl`, kalıcı olmayan iletişim kutusu oluşturma ve kendi ileti döngüsü kullanarak kullanmak [CAxDialogImpl::IsDialogMessage](#isdialogmessage) işlemek için sıradan ileti alma sonra bir Hızlandırıcı tuşu.  
  
 Daha fazla bilgi için `CAxDialogImpl`, bkz: [ATL Denetim kapsamı SSS](../../atl/atl-control-containment-faq.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="advisesinkmap"></a>CAxDialogImpl::AdviseSinkMap  
 Öneri veya nesnenin havuz olay eşlemini tüm girişler unadvise için bu yöntemi çağırın.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Parametreler  
 `bAdvise`  
 Tüm havuz girişleri tavsiye gerekiyorsa true olarak ayarlanır; Tüm false havuzu girdilerini unadvised olacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="create"></a>CAxDialogImpl::Create  
 Kalıcı olmayan iletişim kutusu oluşturmak için bu yöntemi çağırın.  
  
```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 [in] Sahibi penceresine işleci.  
  
 `dwInitParam`  
 [in] İletişim kutusuna geçirmek için kullanılacak değeri belirtir `lParam` parametresinin **WM_INITDIALOG** ileti.  
  
 **RECT &**  
 Bu parametre kullanılmaz. Bu parametre geçirilen `CComControl`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan iletişim kutusu için tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu iletişim kutusu otomatik olarak bağlı `CAxDialogImpl` nesnesi. Modal bir iletişim kutusu oluşturmak için arama [DoModal](#domodal).  
  
 İkinci geçersiz kılma ile iletişim kutuları yalnızca kullanılabilmesi için sağlanan [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="destroywindow"></a>CAxDialogImpl::DestroyWindow  
 Kalıcı olmayan iletişim kutusu yok etmek için bu yöntemi çağırın.  
  
```
BOOL DestroyWindow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencerenin başarıyla yok TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmayın `DestroyWindow` modal bir iletişim kutusu yok etmek için. Çağrı [EndDialog](#enddialog) yerine.  
  
##  <a name="domodal"></a>CAxDialogImpl::DoModal  
 Modal bir iletişim kutusu oluşturmak için bu yöntemi çağırın.  
  
```
INT_PTR DoModal(
  HWND hWndParent = ::GetActiveWindow(), 
  LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 [in] Sahibi penceresine işleci. Varsayılan değer dönüş değeri [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 işlevi.  
  
 `dwInitParam`  
 [in] İletişim kutusuna geçirmek için kullanılacak değeri belirtir `lParam` parametresinin **WM_INITDIALOG** ileti.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, değeri `nRetCode` çağrısında belirtilen parametresi [EndDialog](#enddialog); Aksi halde, -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu iletişim kutusu otomatik olarak bağlı `CAxDialogImpl` nesnesi.  
  
 Kalıcı olmayan iletişim kutusu oluşturmak için çağrı [oluşturma](#create).  
  
##  <a name="enddialog"></a>CAxDialogImpl::EndDialog  
 Modal bir iletişim kutusu yok etmek için bu yöntemi çağırın.  
  
```
BOOL EndDialog(int nRetCode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nRetCode`  
 [in] Tarafından döndürülecek değer [DoModal](#domodal).  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusu yok TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 `EndDialog`iletişim kutusu yordam boyunca çağrılmalıdır. İletişim kutusu yok sonra Windows değerini kullanır `nRetCode` dönüş değeri olarak `DoModal`, iletişim kutusu oluşturuldu.  
  
> [!NOTE]
>  Çağırmayın `EndDialog` kalıcı olmayan iletişim kutusunu yok etme. Çağrı [DestroyWindow](#destroywindow) yerine.  
  
##  <a name="getdialogproc"></a>CAxDialogImpl::GetDialogProc  
 Bir işaretçi almak için bu yöntemi çağırın `DialogProc` geri çağırma işlevi.  
  
```
virtual DLGPROC GetDialogProc();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür `DialogProc` geri çağırma işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 `DialogProc` İşlevi olan bir uygulama tanımlı geri çağırma işlevi.  
  
##  <a name="getidd"></a>CAxDialogImpl::GetIDD  
 İletişim şablonu kaynak kimliği almak için bu yöntemi çağırın  
  
```
int GetIDD();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim şablonu kaynak kimliği döndürür  
  
##  <a name="isdialogmessage"></a>CAxDialogImpl::IsDialogMessage  
 Bu iletişim kutusu için bir ileti yönelik olduğunu belirlemek için bu yöntemi çağırın ve ise, ileti işlem.  
  
```
BOOL IsDialogMessage(LPMSG pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMsg`  
 İşaretçi bir [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) denetlenecek ileti içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE ileti işlenemiyor, FALSE Aksi durumda olup olmadığını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, içinde bir ileti döngüsü oluşturucudan çağrılmaya yöneliktir.  
  
##  <a name="m_bmodal"></a>CAxDialogImpl::m_bModal  
 Hata ayıklama yalnızca mevcut bir değişken oluşturur ve iletişim kutusunu kalıcı ise true olarak ayarlandı.  
  
```
bool m_bModal;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cdialogımpl sınıfı](../../atl/reference/cdialogimpl-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
