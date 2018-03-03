---
title: "CMFCDesktopAlertWnd sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cfebb488921d81c36f842885ad49eae3f40a37fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd sınıfı
`CMFCDesktopAlertWnd` Sınıfı kullanıcıyı bir olay hakkında bilgilendirmek için ekranda görünen bir kalıcı olmayan iletişim kutusu işlevselliğini uygular.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDesktopAlertWnd::Create](#create)|Oluşturur ve Masaüstü uyarı pencere başlatır.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Animasyon hızı döndürür.|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Animasyon türü döndürür.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Otomatik kapat zaman aşımı döndürür.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Resim yazısını yüksekliğini döndürür.|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Ekranda Masaüstü uyarı pencere son geçerli konumunu döndürür.|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Saydamlık düzeyi döndürür.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Masaüstü uyarı pencere küçük resim yazısı ile görüntülenip görüntülenmeyeceğini belirler.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Kullanıcı masaüstü uyarı menüsünde bulunan bir bağlantı düğmesini tıklattığında çerçevesi tarafından çağrılır.|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|Kullanıcı bir öğeyi menüden, bir alt denetim bir bildirim iletisi gönderdiğinde ya da bir kısayol tuş vuruşu çevrildiğinde seçtiğinde framework bu üye işlevi çağırır. (Geçersiz kılmaları [CWnd::OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Yeni animasyon hızı ayarlar.|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Animasyon türünü ayarlar.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Otomatik kapat zaman aşımı ayarlar.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Küçük ve normal başlıkları arasında geçiş yapar.|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Saydamlık düzeyi ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir masaüstü uyarı pencere saydam olabilir, animasyon efektleri ile görüntülenebilir ve (belirtilen bir gecikmeden sonra veya kullanıcı Kapat düğmesini tıklatarak kapatılır) kaybolabilir.  
  
 Bir masaüstü uyarı pencere sırayla bir simge, ileti metni (Etiket) ve bir bağlantı içeren bir varsayılan iletişim de içerebilir. Alternatif olarak, Masaüstü uyarı pencere uygulamanın kaynaklardan özel bir iletişim kutusu içerebilir.  
  
 Bir masaüstü uyarı pencere iki adımda oluşturun. İlk olarak, oluşturmak için oluşturucu çağrısı `CMFCDesktopAlertWnd` nesnesi. İkinci olarak, arama [CMFCDesktopAlertWnd::Create](#create) penceresi oluşturun ve ona eklemek için üye işlevi `CMFCDesktopAlertWnd` nesnesi.  
  
 `CMFCDesktopAlertWnd` Nesnesi Masaüstü uyarı pencere istemci alanını doldurur bir özel alt iletişim kutusu oluşturur. İletişim kutusu üzerine yerleştirilmiş tüm denetimler sahip olur.  
  
 Açılan pencerede özel iletişim kutusunu görüntülemek için aşağıdaki adımları izleyin:  
  
1.  Öğesinden bir sınıf türetin `CMFCDesktopAlertDialog`.  
  
2.  Bir alt iletişim kutusu şablon kaynakları oluşturun.  
  
3.  Çağrı [CMFCDesktopAlertWnd::Create](#create) iletişim kutusu şablon ve çalışma zamanı sınıf bilgileri türetilmiş sınıf için bir işaretçi kaynak Kimliğini kullanıyor.  
  
4.  Bu bildirimler doğrudan işlemek için barındırılan denetimlerin program veya barındırılan denetimlerden gelen tüm bildirimleri işlemek için özel iletişim kutusunu program.  
  
 Masaüstü uyarı pencere davranışını denetlemek için aşağıdaki işlevleri kullanabilirsiniz:  
  
-   Animasyon türü aranarak [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Geçerli seçenekler şunlardır unfold, slayt ve silinerek.  
  
-   Animasyon kare hızı aranarak [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).  
  
-   Saydamlık düzeyi aranarak [CMFCDesktopAlertWnd::SetTransparency](#settransparency).  
  
-   Çağırarak resim yazısını boyutunu değiştirmek için küçük [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). Küçük resim yazısı 7 yüksek pikseldir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanma gösterilmektedir `CMFCDesktopAlertWnd` yapılandırmak için sınıf bir `CMFCDesktopAlertWnd` nesnesi. Örneğin, bir animasyon türü açılır pencere saydamlığı ayarlayın, uyarı pencere küçük resim yazısı görüntüler belirtin ve uyarı penceresi otomatik olarak kapanmadan önce geçen süreyi ayarlayın gösterilmektedir. Örnek oluşturma ve Masaüstü uyarı pencere başlatmak da gösterir. Bu kod parçacığını parçası olan [Masaüstü uyarı demosu örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDesktopAlertWnd.h  
  
##  <a name="create"></a>CMFCDesktopAlertWnd::Create  
 Oluşturur ve Masaüstü uyarı pencere başlatır.  
  
```  
virtual BOOL Create(
    CWnd* pWndOwner,  
    UINT uiDlgResID,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1),  
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

 
virtual BOOL Create(
    CWnd* pWndOwner,  
    CMFCDesktopAlertWndInfo& params,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1));
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out]`pWndOwner`  
 Uyarı pencere sahibini belirtir. Sahibi sonra Masaüstü uyarı pencere ilişkin tüm bildirimler alır. Bu değer olamaz `NULL`.  
  
 [in]`uiDlgResID`  
 Uyarı pencere kaynak Kimliğini belirtir.  
  
 [in]`hMenu`  
 Kullanıcı menü düğmesini tıklattığında görüntüleyen menü belirtir. Varsa `NULL`, menü düğmesi görüntülenmez.  
  
 [in]`ptPos`  
 Ekran koordinatları kullanarak, uyarı pencere görüntülendiği ilk konumlarını belirtir. Bu parametre, (-1, -1) uyarı penceresini ekranın sağ alt köşesinde görüntülenir.  
  
 [in]`pRTIDlgBar`  
 Uyarı pencere istemci alanını kapsayan bir özel iletişim kutusu sınıfı için çalışma zamanı sınıf bilgileri.  
  
 [in]`params`  
 Bir uyarı pencere oluşturmak için kullanılan parametreleri belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Uyarı pencere başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir uyarı pencere oluşturmak için bu yöntemi çağırın. Uyarı pencere istemci alanını kullanıcıya görüntülenen tüm denetimler barındıran bir alt iletişim kutusu içerir.  
  
 İlk yöntemi aşırı yüklemesini uygulamanın kaynaklardan yüklenen bir alt iletişim kutusu içeren bir uyarı pencere oluşturur. İlk yöntemi aşırı yüklemesini, özel iletişim kutusu sınıfı için çalışma zamanı sınıf bilgileri de belirtebilirsiniz.  
  
 İkinci yöntemi aşırı yüklemesini varsayılan denetimleri içeren bir uyarı pencere oluşturur. Değiştirerek görüntülenecek denetleyen belirtebilirsiniz [CMFCDesktopAlertWndInfo sınıfı](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).  
  
##  <a name="getanimationspeed"></a>CMFCDesktopAlertWnd::GetAnimationSpeed  
 Animasyon hızı döndürür.  
  
```  
UINT GetAnimationSpeed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon hızı uyarı penceresinin milisaniye cinsinden.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon hızı ne kadar hızlı uyarı penceresi açar ve kapatır açıklar.  
  
##  <a name="getanimationtype"></a>CMFCDesktopAlertWnd::GetAnimationType  
 Animasyon türü döndürür.  
  
```  
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki animasyon türlerden biri:  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="getautoclosetime"></a>CMFCDesktopAlertWnd::GetAutoCloseTime  
 Otomatik kapat zaman aşımı döndürür.  
  
```  
int GetAutoCloseTime() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Milisaniye cinsinden süre geçtikten sonra uyarı penceresi otomatik olarak kapatılacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Uyarı pencere otomatik olarak kapatılacak önce ne kadar zaman geçmesi belirlemek için bu yöntemi kullanın.  
  
##  <a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight  
 Resim yazısını yüksekliğini döndürür.  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Resim yazısının piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, türetilen bir sınıfta geçersiz kılınabilir. Varsayılan uygulama ya da: açılan pencerede küçük resim yazısı ya da Windows API işlevinden alınan değer görüntülenmelidir küçük resim yazısı yükseklik değeri (7 piksel) verir `GetSystemMetrics(SM_CYSMCAPTION)`.  
  
##  <a name="getlastpos"></a>CMFCDesktopAlertWnd::GetLastPos  
 Ekranda Masaüstü uyarı pencere son konumunu döndürür.  
  
```  
CPoint GetLastPos() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ekran koordinatları bir nokta.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, ekranda uyarı penceresinin son geçerli konumunu döndürür.  
  
##  <a name="gettransparency"></a>CMFCDesktopAlertWnd::GetTransparency  
 Saydamlık düzeyi döndürür.  
  
```  
BYTE GetTransparency() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 0 ile 255 (dahil) arasında saydamlık düzeyi. Bu değer arttıkça, daha fazla opak penceresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Uyarı pencere geçerli saydamlık düzeyi almak için bu yöntemi kullanın.  
  
##  <a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption  
 Masaüstü uyarı pencere küçük resim yazısını veya normal boyutu resim yazısı olup olmadığını belirler.  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`açılan pencerede küçük resim yazısını görüntülenir `FALSE` açılan pencereyi normal boyuta sahip bir resim yazısı ile görüntüleniyorsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Açılan pencerede küçük resim yazısını veya normal boyutu resim yazısı olup olmadığını belirlemek için bu yöntemi kullanın. Varsayılan olarak, küçük resim yazısı 7 yüksek pikseldir. Windows API işlevini çağırarak normal boyutu resim yazısı yüksekliğini edinebilirsiniz `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow  

  
```  
virtual BOOL OnBeforeShow(CPoint&);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`CPoint&`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onclicklinkbutton"></a>CMFCDesktopAlertWnd::OnClickLinkButton  
 Kullanıcı masaüstü uyarı menüsünde bulunan bir bağlantı düğmesini tıklattığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmdID`  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı uyarı pencere bağlantısına tıkladığında bildirim almak istiyorsanız, bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="oncommand"></a>CMFCDesktopAlertWnd::OnCommand  

  
```  
virtual BOOL OnCommand(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wParam`  
 [in]`lParam`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondraw"></a>CMFCDesktopAlertWnd::OnDraw  

  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand  

  
```  
BOOL ProcessCommand(HWND hwnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hwnd`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setanimationspeed"></a>CMFCDesktopAlertWnd::SetAnimationSpeed  
 Yeni animasyon hızı ayarlar.  
  
```  
void SetAnimationSpeed(UINT nSpeed);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nSpeed`  
 Yeni animasyon hızı milisaniye cinsinden belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Uyarı pencere animasyon hızı ayarlamak için bu yöntemi çağırın. Varsayılan animasyon hızı 30 milisaniyedir.  
  
##  <a name="setanimationtype"></a>CMFCDesktopAlertWnd::SetAnimationType  
 Animasyon türünü ayarlar.  
  
```  
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`type`  
 Animasyon türünü belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon türünü ayarlamak için bu yöntemi çağırın. Aşağıdaki değerlerden birini belirleyebilirsiniz.  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="setautoclosetime"></a>CMFCDesktopAlertWnd::SetAutoCloseTime  
 Otomatik kapat zaman aşımı ayarlar.  
  
```  
void SetAutoCloseTime(int nTime);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nTime`  
 Uyarı pencere otomatik olarak kapanmadan önce milisaniye cinsinden süre geçtikten.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı penceresiyle etkileşime girmez varsa uyarı pencere belirlenen süre sonunda otomatik olarak kapatılır.  
  
##  <a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption  
 Küçük ve normal boyutu resim yazıları arasında geçiş yapar.  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bSmallCaption`  
 `TRUE`Uyarı pencere küçük resim yazısı görüntüler belirtmek için; Aksi takdirde `FALSE` uyarı Pencereyi normal boyutuna resim yazısı görüntüler belirtmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Küçük veya normal boyutu resim yazısı görüntülemek için bu yöntemi çağırın. Varsayılan olarak, küçük resim yazısı 7 yüksek pikseldir. Windows API işlevini çağırarak normal resim yazısı boyutunu edinebilirsiniz `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency  
 Açılan pencerede saydamlık düzeyi ayarlar.  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nTransparency`  
 Saydamlık düzeyini belirtir. Bu değer, 0 ile 255 (dahil) arasında olmalıdır. Bu değer arttıkça, daha fazla opak penceresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Açılan pencerede saydamlık düzeyi ayarlamak için bu işlevini çağırın.  
  
##  <a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize  

  
```  
virtual CSize GetDialogSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWndInfo sınıfı](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
