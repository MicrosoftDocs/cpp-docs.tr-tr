---
title: Caxdialogımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd019112e846875bfa8e27faac5088fbcf1cdaef
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881993"
---
# <a name="caxdialogimpl-class"></a>Caxdialogımpl sınıfı
Bu sınıf, bir iletişim kutusu (kalıcı veya kısıtlayıcı olmayan) barındıran ActiveX denetimlerini uygular.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class TBase = CWindow>  
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `CAxDialogImpl`.  
  
 *Ttemel*  
 Ana pencere sınıfı için `CDialogImplBaseT`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Eşlemesindeki nesnenin havuz olayı eşlemi tüm girişleri önermek veya öneriyi kaldırmak için bu yöntemi çağırın.|  
|[CAxDialogImpl::Create](#create)|Modsuz iletişim kutusu oluşturmak için bu yöntemi çağırın.|  
|[CAxDialogImpl::DestroyWindow](#destroywindow)|Modsuz iletişim kutusu yok etmek için bu yöntemi çağırın.|  
|[CAxDialogImpl::DoModal](#domodal)|Kalıcı bir iletişim kutusu oluşturmak için bu yöntemi çağırın.|  
|[CAxDialogImpl::EndDialog](#enddialog)|Kalıcı bir iletişim kutusu yok etmek için bu yöntemi çağırın.|  
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|Bir işaretçi almak için bu yöntemi çağırın `DialogProc` geri çağırma işlevi.|  
|[CAxDialogImpl::GetIDD](#getidd)|İletişim şablonu kaynak Kimliğini almak için bu yöntemi çağırın|  
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|Bu iletişim kutusu için bir ileti yönelik olduğunu belirlemek için bu yöntemi çağırın ve ise, iletisi işlenemedi.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAxDialogImpl::m_bModal](#m_bmodal)|Hata ayıklama yalnızca mevcut bir değişken oluşturur ve iletişim kutusunu kalıcı ise true olarak ayarlandı.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAxDialogImpl` kalıcı veya geçici bir iletişim kutusu oluşturmanıza olanak sağlar. `CAxDialogImpl` uygun işleyicileri iletilerini yönlendirmek için varsayılan ileti eşlemesi kullanan iletişim kutusu yordam sağlar.  
  
 `CAxDialogImpl` öğesinden türetilen `CDialogImplBaseT`, hangi sırayla türetilir *Ttemel* (varsayılan olarak, `CWindow`) ve `CMessageMap`.  
  
 Sınıfınıza iletişim şablonu kaynak kimliğini belirtir. bir IDD üyesi tanımlanmalıdır Örneğin, bir ATL iletişim kutusu kullanılarak nesne ekleme **sınıfı Ekle** iletişim kutusu otomatik olarak sınıfınıza aşağıdaki satırı ekler:  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]  
  
 Burada `MyDialog` olduğu **kısa ad** ATL iletişim kutusu Sihirbazı'nda girildi.  
  
 Bkz: [iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) daha fazla bilgi için.  
  
 Kalıcı bir iletişim kutusu bir ActiveX denetimi ile oluşturulan Not `CAxDialogImpl` kısayol tuşları desteklemez. Hızlandırıcı tuşları ile oluşturulan bir iletişim kutusu desteklemek için `CAxDialogImpl`, modsuz iletişim kutusu oluşturabilir ve kendi ileti döngüsü kullanarak kullanın [CAxDialogImpl::IsDialogMessage](#isdialogmessage) işlemek için kuyruktan ileti alma sonra bir Hızlandırıcı tuşu.  
  
 Daha fazla bilgi için `CAxDialogImpl`, bkz: [ATL Denetim kapsamı SSS](../../atl/atl-control-containment-faq.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="advisesinkmap"></a>  CAxDialogImpl::AdviseSinkMap  
 Eşlemesindeki nesnenin havuz olayı eşlemi tüm girişleri önermek veya öneriyi kaldırmak için bu yöntemi çağırın.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Parametreler  
 *bAdvise*  
 Tüm havuz girişleri olun gerekiyorsa true olarak ayarlayın; Tüm false havuz girişleri unadvised olacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.  
  
##  <a name="create"></a>  CAxDialogImpl::Create  
 Modsuz iletişim kutusu oluşturmak için bu yöntemi çağırın.  
  
```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *hWndParent*  
 [in] İşleci sahip penceresine.  
  
 *dwInitParam*  
 [in] İletişim kutusundaki geçirmek için bir değer belirtir *lParam* WM_INITDIALOG iletisinin parametresi.  
  
 *RECT &AMP;*  
 Bu parametre kullanılmaz. Bu parametre geçirilen `CComControl`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan bir iletişim kutusu için tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu iletişim kutusu otomatik olarak bağlı `CAxDialogImpl` nesne. Kalıcı bir iletişim kutusu oluşturmak için arama [DoModal](#domodal).  
  
 İkinci geçersiz kılma ile iletişim kutuları yalnızca kullanılabilmesi için sağlanan [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="destroywindow"></a>  CAxDialogImpl::DestroyWindow  
 Modsuz iletişim kutusu yok etmek için bu yöntemi çağırın.  
  
```
BOOL DestroyWindow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencerenin başarıyla edildiğinde TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmayın `DestroyWindow` kalıcı bir iletişim kutusu yok edilemiyor. Çağrı [EndDialog](#enddialog) yerine.  
  
##  <a name="domodal"></a>  CAxDialogImpl::DoModal  
 Kalıcı bir iletişim kutusu oluşturmak için bu yöntemi çağırın.  
  
```
INT_PTR DoModal(
  HWND hWndParent = ::GetActiveWindow(), 
  LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *hWndParent*  
 [in] İşleci sahip penceresine. Varsayılan değer dönüş değeri [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 işlevi.  
  
 *dwInitParam*  
 [in] İletişim kutusundaki geçirmek için bir değer belirtir *lParam* WM_INITDIALOG iletisinin parametresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, değerini *nRetCode* yapılan çağrıda belirtilen parametre [EndDialog](#enddialog); Aksi takdirde, -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu iletişim kutusu otomatik olarak bağlı `CAxDialogImpl` nesne.  
  
 Modsuz iletişim kutusu oluşturmak için arama [Oluştur](#create).  
  
##  <a name="enddialog"></a>  CAxDialogImpl::EndDialog  
 Kalıcı bir iletişim kutusu yok etmek için bu yöntemi çağırın.  
  
```
BOOL EndDialog(int nRetCode);
```  
  
### <a name="parameters"></a>Parametreler  
 *nRetCode*  
 [in] Tarafından döndürülen değer [DoModal](#domodal).  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusunu yok TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 `EndDialog` iletişim kutusu yordam boyunca çağrılmalıdır. İletişim kutusunu yok sonra Windows değerini kullanır. *nRetCode* dönüş değeri olarak `DoModal`, iletişim kutusu oluşturulur.  
  
> [!NOTE]
>  Çağırmayın `EndDialog` modsuz iletişim kutusu yok edilemiyor. Çağrı [DestroyWindow](#destroywindow) yerine.  
  
##  <a name="getdialogproc"></a>  CAxDialogImpl::GetDialogProc  
 Bir işaretçi almak için bu yöntemi çağırın `DialogProc` geri çağırma işlevi.  
  
```
virtual DLGPROC GetDialogProc();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür `DialogProc` geri çağırma işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 `DialogProc` İşlev, bir uygulama tanımlı geri çağırma işlevi.  
  
##  <a name="getidd"></a>  CAxDialogImpl::GetIDD  
 İletişim şablonu kaynak kimliği almak için bu yöntemi çağırın  
  
```
int GetIDD();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim şablonu kaynak IDsini döndürür.  
  
##  <a name="isdialogmessage"></a>  CAxDialogImpl::IsDialogMessage  
 Bu iletişim kutusu için bir ileti yönelik olduğunu belirlemek için bu yöntemi çağırın ve ise, iletisi işlenemedi.  
  
```
BOOL IsDialogMessage(LPMSG pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 *pMsg*  
 İşaretçi bir [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) denetlenecek iletiyi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işlenemiyor, yanlış Aksi durumda kalıp kalmadığını TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir ileti döngüsü içinde öğesinden çağrılması beklenir.  
  
##  <a name="m_bmodal"></a>  CAxDialogImpl::m_bModal  
 Hata ayıklama yalnızca mevcut bir değişken oluşturur ve iletişim kutusunu kalıcı ise true olarak ayarlandı.  
  
```
bool m_bModal;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cdialogımpl sınıfı](../../atl/reference/cdialogimpl-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
