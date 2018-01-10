---
title: "COccManager sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
dev_langs: C++
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ffa16b7a210bc53f178e3ec437aefb6cede766a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coccmanager-class"></a>COccManager sınıfı
Çeşitli özel denetim siteleri yönetir; tarafından uygulanan `COleControlContainer` ve `COleControlSite` nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COccManager::CreateContainer](#createcontainer)|Oluşturur bir **COleContainer** nesnesi.|  
|[COccManager::CreateDlgControls](#createdlgcontrols)|ActiveX denetimleri, ilişkili tarafından barındırılan oluşturur `COleContainer` nesnesi.|  
|[COccManager::CreateSite](#createsite)|Oluşturur bir `COleClientSite` nesnesi.|  
|[COccManager::GetDefBtnCode](#getdefbtncode)|Varsayılan düğme kodu alır.|  
|[COccManager::IsDialogMessage](#isdialogmessage)|Bir iletişim kutusu ileti hedef belirler.|  
|[COccManager::IsLabelControl](#islabelcontrol)|Belirtilen denetim bir etiket denetimi olup olmadığını belirler.|  
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|Geçerli anımsatıcı belirtilen denetim anımsatıcı eşleşip eşleşmediğini belirler.|  
|[COccManager::OnEvent](#onevent)|Belirtilen olayını işlemek çalışır.|  
|[COccManager::PostCreateDialog](#postcreatedialog)|İletişim kutusu oluşturma sırasında ayrılan kaynakları serbest bırakır.|  
|[COccManager::PreCreateDialog](#precreatedialog)|ActiveX denetimleri için bir iletişim şablonunu işler.|  
|[COccManager::SetDefaultButton](#setdefaultbutton)|Belirtilen denetim varsayılan durumunu değiştirir.|  
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Varolan tüm ActiveX denetimleri belirtilen iletişim şablonunda ortak denetimler ayırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Taban sınıfı **CNoTrackObject**, belgelenmemiş bir taban sınıfı (AFXTLS içinde bulunur. H). Türetilmiş sınıflar MFC çerçevesi tarafından kullanılmak üzere tasarlanmış **CNoTrackObject** sınıfı bellek sızıntısı algılama muafiyet. Doğrudan öğesinden türetilen önerilmez **CNoTrackObject**.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CNoTrackObject`  
  
 `COccManager`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxocc.h  
  
##  <a name="createcontainer"></a>COccManager::CreateContainer  
 Bir denetim kapsayıcısı oluşturmak için çerçevesi tarafından çağrılır.  
  
```  
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Özel site kapsayıcı ile ilişkili pencere nesnesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan kapsayıcı için bir işaretçi; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel site oluşturma ile ilgili daha fazla bilgi için bkz: [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).  
  
##  <a name="createdlgcontrols"></a>COccManager::CreateDlgControls  
 Tarafından belirtilen ActiveX denetimleri oluşturmak için bu işlevi çağırmak `pOccDialogInfo` parametresi.  
  
```  
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    LPCTSTR lpszResourceName,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

 
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    void* lpResource,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWndParent*  
 İletişim nesnenin üst için bir işaretçi.  
  
 `lpszResourceName`  
 Oluşturulan kaynak adı.  
  
 `pOccDialogInfo`  
 İletişim nesnesi oluşturmak için kullanılan iletişim şablonu için bir işaretçi.  
  
 `lpResource`  
 Bir kaynak için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimi başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde sıfır.  
  
##  <a name="createsite"></a>COccManager::CreateSite  
 Gösterdiği kapsayıcı tarafından barındırılan bir denetim sitesi oluşturmak için framework tarafından çağrılan `pCtrlCont`.  
  
```  
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCtrlCont`  
 Yeni Denetim siteyi barındıran denetimi kapsayıcısı için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan denetim site için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bir denetim oluşturmak için bu işlevi geçersiz kılma kullanarak, site, [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-türetilmiş sınıf.  
  
 Her denetim kapsayıcı birden çok site barındırabilir. Ek siteler için birden fazla çağrı oluşturmak `CreateSite`.  
  
##  <a name="getdefbtncode"></a>COccManager::GetDefBtnCode  
 Denetimi varsayılan düğme olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Düğme denetimi içeren pencere nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden biri:  
  
- **DLGC_DEFPUSHBUTTON** denetimidir iletişim kutusunda varsayılan düğme.  
  
- **DLGC_UNDEFPUSHBUTTON** denetim iletişim kutusunda varsayılan düğme değil.  
  
- **0** denetim bir düğme değil.  
  
##  <a name="isdialogmessage"></a>COccManager::IsDialogMessage  
 Bir ileti için belirtilen iletişim kutusu kullanılmaya ise, iletiyi işler olup olmadığını ve belirlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWndDlg*  
 İletinin hedef iletişim için bir işaretçi.  
  
 `lpMsg`  
 Bir işaretçi bir `MSG` denetlenecek ileti içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleniyorsa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan davranışını `IsDialogMessage` için klavye iletilerini denetleyin ve ilgili iletişim kutusunda seçimlerini dönüştürün. Örneğin, SEKME tuşuna bastığınızda, sonraki denetim veya denetimlerin grubu seçer.  
  
 Belirtilen iletişim gönderilen iletiler için özel davranışı sağlamak için bu işlevi geçersiz kılar.  
  
##  <a name="islabelcontrol"></a>COccManager::IsLabelControl  
 Belirtilen denetim bir etiket denetimi olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);  
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Denetimi içeren pencere için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etiket denetimi ise, sıfır olmayan; Aksi takdirde sıfır  
  
### <a name="remarks"></a>Açıklamalar  
 Etiket denetimi ne olursa olsun denetim sıralamada sonraki için bir etiket gibi davranır biridir.  
  
##  <a name="ismatchingmnemonic"></a>COccManager::IsMatchingMnemonic  
 Geçerli anımsatıcı denetim tarafından temsil eşleşip eşleşmediğini belirlemek için bu işlevini çağırın.  
  
```  
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,  
    LPMSG lpMsg);

 
static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Denetimi içeren pencere için bir işaretçi.  
  
 `lpMsg`  
 Eşleştirilecek anımsatıcı içeren ileti için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anımsatıcı denetimi eşleşirse sıfır olmayan; Aksi takdirde sıfır  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onevent"></a>COccManager::OnEvent  
 Belirtilen olayını işlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,  
    UINT idCtrl,  
    AFX_EVENT* pEvent,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 *pCmdTarget*  
 Bir işaretçi `CCmdTarget` olayını işlemek çalışırken nesnesi  
  
 `idCtrl`  
 Denetimin kaynak kimliği.  
  
 `pEvent`  
 İşlenen olay.  
  
 `pHandlerInfo`  
 Aksi takdirde **NULL**, `OnEvent` doldurur **pTarget** ve **pmf** üyeleri **AFX_CMDHANDLERINFO** yerine yapısı komut gönderme. Genellikle, bu parametre olmalıdır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olay işleniyorsa, aksi takdirde sıfır sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan olay işleme işlemi özelleştirmek için geçersiz kılar.  
  
##  <a name="precreatedialog"></a>COccManager::PreCreateDialog  
 Gerçek iletişim kutusu oluşturmadan önce ActiveX denetimleri için bir iletişim şablonunu işlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,  
    const DLGTEMPLATE* pOrigTemplate);
```  
  
### <a name="parameters"></a>Parametreler  
 `pOccDialogInfo`  
 Bir **_AFX_OCC_DIALOG_INFO** iletişim şablonunu ve iletişim kutusu tarafından barındırılan tüm ActiveX denetimleri hakkında bilgi içeren yapısı.  
  
 *pOrigTemplate*  
 İletişim kutusu oluşturulurken kullanılacak iletişim şablon için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusu oluşturmak için kullanılan bir iletişim şablonunu yapısına yönelik işaretçinin.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan davranışı için bir çağrı yapar `SplitDialogTemplate`olması durumunda tüm ActiveX denetimlerini mevcut belirleme ve sonuç iletişim şablonu döndürür.  
  
 ActiveX denetimlerini barındırma bir iletişim kutusu oluşturma işlemi özelleştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="postcreatedialog"></a>COccManager::PostCreateDialog  
 İletişim şablonu için ayrılan belleği boşaltmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `pOccDialogInfo`  
 Bir **_AFX_OCC_DIALOG_INFO** iletişim şablonunu ve iletişim kutusu tarafından barındırılan tüm ActiveX denetimleri hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bellek için bir çağrı tarafından ayrıldı `SplitDialogTemplate`ve iletişim kutusunda barındırılan tüm ActiveX denetimleri için kullanıldı.  
  
 Bu işlev iletişim kutusu nesnesi tarafından kullanılan tüm kaynakları temizleme işlemi özelleştirmek için geçersiz kılar.  
  
##  <a name="setdefaultbutton"></a>COccManager::SetDefaultButton  
 Denetimi varsayılan düğme olarak ayarlamak için bu işlevini çağırın.  
  
```  
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,  
    BOOL bDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Denetimi içeren pencere için bir işaretçi.  
  
 `bDefault`  
 Denetimi varsayılan düğme duruma gelir, sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Denetimi olmalıdır **OLEMISC_ACTSLIKEBUTTON** durum biti ayarlanmamış. Daha fazla bilgi için **OLEMISC** bayrakları, bkz: [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) konu Windows SDK.  
  
##  <a name="splitdialogtemplate"></a>COccManager::SplitDialogTemplate  
 Ortak iletişim kutusu denetimleri ActiveX denetimlerini bölüneceği çerçevesi tarafından çağrılır.  
  
```  
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,  
    DLGITEMTEMPLATE** ppOleDlgItems);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTemplate`  
 İncelenmesi için iletişim şablonu için bir işaretçi.  
  
 `ppOleDlgItems`  
 ActiveX denetimleri iletişim kutusu öğeleri işaretçiler listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yalnızca olmayan ActiveX denetimlerini içeren bir iletişim şablonunu yapısına yönelik işaretçinin. ActiveX denetimleri yoksa **NULL** döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Herhangi bir ActiveX denetimini bulunursa, şablon analiz edilir ve yalnızca olmayan ActiveX denetimleri içeren yeni bir şablon oluşturulur. Bu işlem sırasında bulunan herhangi bir ActiveX denetimini eklenir `ppOleDlgItems`.  
  
 Şablonda, ActiveX denetimler yoksa **NULL** döndürülen *.*  
  
> [!NOTE]
>  Yeni şablon de serbest için ayrılmış bellek `PostCreateDialog` işlevi.  
  
 Bu işlev bu işlemi özelleştirmek için geçersiz kılar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleControlSite sınıfı](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer Sınıfı](../../mfc/reference/colecontrolcontainer-class.md)
