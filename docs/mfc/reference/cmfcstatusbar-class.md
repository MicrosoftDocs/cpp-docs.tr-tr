---
title: CMFCStatusBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
dev_langs:
- C++
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c82a73c95c0869f7f5245ef3ddc15c0216b07579
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041737"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar sınıfı
`CMFCStatusBar` Sınıfı uygulayan benzer bir durum çubuğu `CStatusBar` sınıfı. Ancak, `CMFCStatusBar` sınıfı tarafından sunulmuyor özelliklere sahiptir `CStatusBar` görüntüleri, animasyonları ve ilerleme çubukları; görüntüleme olanağı ve fare çift tıklamalar yanıt verme yeteneği gibi sınıfı. 

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]   
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(Geçersiz kılmaları [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||  
|[CMFCStatusBar::Create](#create)|Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesnesi. (Geçersiz kılmaları [CPane::Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCStatusBar::CreateEx](#createex)|Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesnesi. (Geçersiz kılmaları [CPane::CreateEx](../../mfc/reference/cpane-class.md#createex).)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Başka bir bölme dinamik olarak bu bölme ve üst çerçeve arasında eklenebilir olup olmadığını belirler. (Geçersiz kılmaları [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Fare işleme etkinleştirir veya devre dışı bırakır durum çubuğundaki çift tıklamalar.|  
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Bir ilerleme çubuğu belirtilen bölmesinde görüntüler.|  
|[CMFCStatusBar::GetCount](#getcount)|Durum çubuğunda bölmeleri sayısını döndürür.|  
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||  
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCStatusBar::GetItemID](#getitemid)||  
|[CMFCStatusBar::GetItemRect](#getitemrect)||  
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||  
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||  
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Bölmesinde stili döndürür. (Geçersiz kılmaları [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|  
|[CMFCStatusBar::GetPaneText](#getpanetext)||  
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Belirtilen durum çubuğu bölmesinin piksel cinsinden genişliği döndürür.|  
|[CMFCStatusBar::GetTipText](#gettiptext)|Belirtilen bölmesinde durum çubuğu için araç ipucu metni döndürür.|  
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|Belirtilen bölmesinde geçersiz kılar ve içeriğini yeniden çizer.|  
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Bu bağlı Windows penceresi oluşturulmasını önce framework tarafından çağrılan `CWnd` nesnesi. (Geçersiz kılmaları [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|  
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||  
|[CMFCStatusBar::SetIndicators](#setindicators)||  
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Bir animasyon belirtilen bölmesine atar.|  
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Belirtilen durum çubuğu bölmesinin arka plan rengini belirler.|  
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Belirtilen durum çubuğu bölmesinin göstergesi simgesi ayarlar.|  
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||  
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|Belirtilen durum çubuğu bölmesinin ilerleme çubuğu geçerli durumunu ayarlar.|  
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Bölmesinin stilini ayarlar. (Geçersiz kılmaları [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|  
|[CMFCStatusBar::SetPaneText](#setpanetext)||  
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Belirtilen durum çubuğu bölmesinin metin rengini belirler.|  
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Belirtilen durum çubuğu bölmesinin piksel cinsinden genişliğini belirler.|  
|[CMFCStatusBar::SetTipText](#settiptext)|Belirtilen bölmesinde durum çubuğu için araç ipucu metni ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Durum çubuğu bölmesinin yeniden çizer çerçevesi tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki diyagramda, Durum Çubuğu'ndan bir şekilde gösterilmektedir [durum çubuğu gösterim örneği](../../visual-cpp-samples.md) uygulama.  
  
 ![CMFCStatusBar örneği](../../mfc/reference/media/cmfcstatusbar.png "cmfcstatusbar")  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemleri çağırmak için uygulamanın kullandığı yerel değişkenleri gösterir `CMFCStatusBar` sınıfı. Bu değişkenler StatusBarDemoView.h bildirilir. Ana çerçeve MainFrm.h içinde bildirilen, belge StatusBarDemoDoc.h bildirilmiş ve görünümü içinde StatusBarDemoView.h bildirilmiş. Bu kod parçacığını parçası olan [durum çubuğu gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir başvuru almak gösterilmiştir `CMFCStatusBar` Tanıtımı nesne `GetStatusBar` MainFrm.h ve bu yöntemi çağırmadan yöntemi `GetStatusBar` StatusBarDemoView.h yöntemi. Bu kod parçacığını parçası olan [durum çubuğu gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemleri çağırmak gösterilmiştir `CMFCStatusBar` StatusBarDemoView.cpp sınıfta. Sabitler MainFrm.h bildirilir. Örnek simgeyi ayarlamak, durum çubuğu bölmesinin araç ipucu metni ayarlamak, belirtilen bölmesinde bir ilerleme çubuğu görüntülemek, belirtilen bölmesine bir animasyon atamak, metin ve durum çubuğu bölmesinin genişliğini ayarlamak ve progr geçerli ilerleme göstergesi ayarlamak nasıl gösterir Durum çubuğu bölmesinin v çubuğu. Bu kod parçacığını parçası olan [durum çubuğu gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxstatusbar.h  
  
##  <a name="calcfixedlayout"></a>  CMFCStatusBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bStretch*  
 [in] *bHorz*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="commandtoindex"></a>  CMFCStatusBar::CommandToIndex  

  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIDFind*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>  CMFCStatusBar::Create  

  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pParentWnd*  
 [in] *dwStyle*  
 [in] *nID*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="createex"></a>  CMFCStatusBar::CreateEx  

  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pParentWnd*  
 [in] *dwCtrlStyle*  
 [in] *dwStyle*  
 [in] *nID*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="doesallowdyninsertbefore"></a>  CMFCStatusBar::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enablepanedoubleclick"></a>  CMFCStatusBar::EnablePaneDoubleClick  
 Fare işleme etkinleştirir veya devre dışı bırakır durum çubuğundaki çift tıklamalar.  
  
```  
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Varsa `TRUE`, fare işlenmesini çift etkinleştir. Aksi takdirde, fare çift işlenmesini devre dışı bırakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Çift tıklama işlemek için durum çubuğunu etkinleştirilirse, Windows durum çubuğu kullanıcı çift durum çubuğu bölmesinde, her seferinde sahibi bir kaynak kimliği ile birlikte WM_COMMAND bildirim gönderir.  
  
##  <a name="enablepaneprogressbar"></a>  CMFCStatusBar::EnablePaneProgressBar  
 Belirtilen bölmesinde bir ilerleme çubuğu gösteriliyor.  
  
```  
void EnablePaneProgressBar(
    int nIndex,  
    long nTotal=100,  
    BOOL bDisplayText=FALSE,  
    COLORREF clrBar=-1,  
    COLORREF clrBarDest=-1,  
    COLORREF clrProgressText=-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Etkinleştirmek için ilerleme çubuğu bölmesinin dizini belirtir.  
  
 [in] *ntoplam yer*  
 İlerleme çubuğu için en büyük değer belirtir.  
  
 [in] *bDisplayText*  
 İlerleme çubuğu geçerli ilerleme değeri görüntüleyip görüntülemeyeceğini belirtir.  
  
 [in] *clrBar*  
 İlerleme çubuğu arka plan rengini belirtir.  
  
 [in] *clrBarDest*  
 İlerleme çubuğu arka plan ikincil rengi belirtir. Farklı değerinden kullanmak *clrBar* gradyan karıştırılan renge göre doldurmak için.  
  
 [in] *clrProgressText*  
 İlerleme çubuğu metnin rengini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İlerleme çubuğu çağrısı devre dışı bırakmak istiyorsanız `EnablePaneProgressBar` ile *ntoplam yer* -1 olarak ayarlayın. Varsayılan olarak *ntoplam yer* 100'e ayarlayın. Bu nedenle, yüzde olarak ilerleme durumunu görüntülemek için diğer tüm hesaplamalar gerekmez.  
  
 Farklı değerler geçirmelisiniz *clrBar* ve *clrBarDest* böylece gradyan karıştırılan renk ilerleme çubuğu arka plan rengini görüntüler. biçimindeki telefon numarasıdır.  
  
 Geçerli ilerleme ayarlamak için arama [CMFCStatusBar::SetPaneProgress](#setpaneprogress) yöntemi.  
  
##  <a name="getcount"></a>  CMFCStatusBar::GetCount  
 Durum çubuğu bölmelerinde sayısını alır.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum çubuğu bölmelerinde sayısı.  
  
##  <a name="getdrawextendedarea"></a>  CMFCStatusBar::GetDrawExtendedArea  

  
```  
BOOL GetDrawExtendedArea() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getextendedarea"></a>  CMFCStatusBar::GetExtendedArea  

  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rect*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getitemid"></a>  CMFCStatusBar::GetItemID  

  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getitemrect"></a>  CMFCStatusBar::GetItemRect  

  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 [in] *lpRect*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpaneinfo"></a>  CMFCStatusBar::GetPaneInfo  

  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 [in] *nID*  
 [in] *nStyle*  
 [in] *cxWidth*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpaneprogress"></a>  CMFCStatusBar::GetPaneProgress  

  
```  
long GetPaneProgress(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanestyle"></a>  CMFCStatusBar::GetPaneStyle  

  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanetext"></a>  CMFCStatusBar::GetPaneText  

  
```  
void GetPaneText(
    int nIndex,  
    CString& s) const;  
  
CString GetPaneText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 [in] *s*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanewidth"></a>  CMFCStatusBar::GetPaneWidth  
 Durum çubuğu bölmesinin genişliğini alır.  
  
```  
int GetPaneWidth(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Durum çubuğu bölmesinin dizinini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum çubuğu bölmesinin genişliğini, *nIndex* belirtir; durum çubuğu bölmesinin yoksa, aksi takdirde, sıfır.  
  
##  <a name="gettiptext"></a>  CMFCStatusBar::GetTipText  
 Durum çubuğu bölmesinin araç ipucu metnini alır.  
  
```  
CString GetTipText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Araç ipucu metnini almak bölmesi dizinini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum çubuğu bölmesinin araç ipucu metnini, *nIndex* belirtir. Aksi durumda, boş dize bir durum çubuğu bölmesinin için belirtilen yoksa *nIndex* veya kendi araç ipucu metni boş ise.  
  
##  <a name="invalidatepanecontent"></a>  CMFCStatusBar::InvalidatePaneContent  
 Durum çubuğu bölmesinin geçersiz kılmak ve içeriği yeniden.  
  
```  
void InvalidatePaneContent(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Geçersiz kılınan ve yeniden düzenlenmiş içerikleri olan bölmesinde dizinini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Durum çubuğu geçersiz kılınması yeniden çizim için işaretlenir. Windows, onu yeniden çizer zaman `UpdateWindow` yöntemi WM_PAINT ileti gönderir `OnPaint` yöntemi.  
  
##  <a name="ondrawpane"></a>  CMFCStatusBar::OnDrawPane  
 Durum çubuğu bölmesinin yeniden çizin.  
  
```  
virtual void OnDrawPane(
    CDC* pDC,  
    CMFCStatusBarPaneInfo* pPane);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Çizim için cihaz bağlamı için bir işaretçi.  
  
 [in] *pPane*  
 Bir işaretçi bir `CMFCStatusBarPaneInfo` çizilmesi için bölmesinde hakkında bilgi içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `OnDrawPane` bölmesinde cihaz bağlamı kullanarak yeniden çizer *pDC* Bölmesi'nin stili ve içerik göre.  
  
 Bu yöntemi geçersiz kılın bir `CMFCStatusBar`-türetilmiş bir bölme görünümünü özelleştirmek için sınıf.  
  
##  <a name="precreatewindow"></a>  CMFCStatusBar::PreCreateWindow  

  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *cs*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdrawextendedarea"></a>  CMFCStatusBar::SetDrawExtendedArea  

  
```  
void SetDrawExtendedArea(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bInternet*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setindicators"></a>  CMFCStatusBar::SetIndicators  

  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpIDArray*  
 [in] *nIDCount*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpaneanimation"></a>  CMFCStatusBar::SetPaneAnimation  
 Bir animasyon belirtilen bölmesine atar.  
  
```  
void SetPaneAnimation(
    int nIndex,  
    HIMAGELIST hImageList,  
    UINT nFrameRate=500,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Bir animasyon atamak istediğiniz bölmesi dizinini belirtir.  
  
 [in] *hImageList*  
 Animasyon kare tutan resim listesi için bir tanıtıcı belirtir.  
  
 [in] *nFrameRate*  
 Kare hızı, animasyonun için milisaniye cinsinden belirtir.  
  
 [in] *bgüncelleştirmesinin*  
 Varsa `TRUE`, bölmesinde içeriği hemen güncelleştirin. Aksi takdirde, geçersiz kılınması bölmesinde içerik güncelleştirilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli animasyonu devre dışı bırakmak istiyorsanız, çağrı `SetPaneAnimation` ile `hImageList` kümesine `NULL`.  
  
##  <a name="setpanebackgroundcolor"></a>  CMFCStatusBar::SetPaneBackgroundColor  
 Durum çubuğu bölmesinin arka plan rengini belirler.  
  
```  
void SetPaneBackgroundColor(
    int nIndex,  
    COLORREF clrBackground=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Yeni bir arka plan rengini ayarlamak bölmesi dizinini belirtir.  
  
 [in] *clrBackground*  
 Yeni arka plan rengini belirtir.  
  
 [in] *bgüncelleştirmesinin*  
 Varsa `TRUE`, bölmesinde içeriği hemen güncelleştirin. Aksi takdirde, başka bir yöntem kullanarak bölmesinde geçersiz kılınan kadar bölmesi içeriği güncelleştirmez.  
  
##  <a name="setpaneicon"></a>  CMFCStatusBar::SetPaneIcon  
 Durum çubuğu bölmesinin simgesi ayarlayın.  
  
```  
void SetPaneIcon(
    int nIndex,  
    HICON hIcon,  
    BOOL bUpdate=TRUE);

 
void SetPaneIcon(
    int nIndex,  
    HBITMAP hBmp,  
    COLORREF clrTransparent=RGB(255, 0, 255),  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Görüntü ayarlanacağı bölmesi dizinini belirtir.  
  
 [in] *hIcon*  
 Bölmesinde görüntüsü olarak ayarlanacak simgesi için bir tanıtıcı belirtir.  
  
 [in] *bgüncelleştirmesinin*  
 Bölmesi içeriği hemen güncelleştirip güncelleştirmeyeceğini belirtir.  
  
 [in] *hBmp*  
 Bölmesinde görüntüsü olarak ayarlanacak bit eşlem için bir tanıtıcı belirtir.  
  
 [in] *clrTransparent*  
 Bit eşlem saydam rengini belirtir, *hBmp* gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ya da geçirebilirsiniz `HICON` veya `HBITMAP` birlikte Bölmesi'nin resmi ayarlamak için saydam rengi. Artık görüntüyü istemiyorsanız geçirmek `NULL` değeri görüntü işleyici olarak.  
  
 Oynatılmakta olan herhangi bir animasyon ise, [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) sahip ayarlayın, animasyonun durdurulur.  
  
##  <a name="setpaneinfo"></a>  CMFCStatusBar::SetPaneInfo  

  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 [in] *nID*  
 [in] *nStyle*  
 [in] *cxWidth*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpaneprogress"></a>  CMFCStatusBar::SetPaneProgress  
 Geçerli İlerleme göstergesi belirtilen bölmesi ilerleme çubuğunun ayarlayın.  
  
```  
void SetPaneProgress(
    int nIndex,  
    long nCurr,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 İlerleme göstergesi güncelleştirileceği bölmesi dizinini belirtir.  
  
 [in] *nCurr*  
 İlerleme göstergesi geçerli değeri belirtir.  
  
 [in] *bgüncelleştirmesinin*  
 Bölmesinde hemen güncelleştirilmesi gerekip gerekmediğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen bölmesinde ilerleme çubuğu İlerleme göstergesi güncelleştirmek istediğinizde bu yöntemi çağırın.  
  
 Verilen bölmesi bu işlevi kullanmak için çağırmalısınız [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) ilk.  
  
##  <a name="setpanestyle"></a>  CMFCStatusBar::SetPaneStyle  

  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 [in] *nStyle*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpanetext"></a>  CMFCStatusBar::SetPaneText  

  
```  
virtual BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 [in] *lpszNewText*  
 [in] *bgüncelleştirmesinin*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpanetextcolor"></a>  CMFCStatusBar::SetPaneTextColor  
 Belirtilen bölmesinin metin rengini belirler.  
  
```  
void SetPaneTextColor(
    int nIndex,  
    COLORREF clrText=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Yeni bir metin rengi atamak istediğiniz bölmesinde dizinini belirtir.  
  
 [in] *clrText*  
 Metin rengini belirtir.  
  
 [in] *bgüncelleştirmesinin*  
 Varsa `TRUE`, bölmesinde içeriği hemen güncelleştirin. Aksi takdirde, başka bir yöntem kullanarak bölmesinde geçersiz kılınan kadar bölmesi içeriği güncelleştirmez.  
  
##  <a name="setpanewidth"></a>  CMFCStatusBar::SetPaneWidth  
 Durum çubuğu bölmesinin genişliğini ayarlayın.  
  
```  
void SetPaneWidth(
    int nIndex,  
    int cx);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Yeni bir genişlik ayarlanacak durum çubuğu bölmesinin dizini.  
  
 [in] *cx*  
 Durum çubuğu bölmesinin piksel cinsinden yeni genişliği.  
  
##  <a name="settiptext"></a>  CMFCStatusBar::SetTipText  
 Durum çubuğu bölmesinin araç ipucu metni ayarlayın.  
  
```  
void SetTipText(
    int nIndex,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Araç İpucu metni atamak istediğiniz bölmesinde dizini.  
  
 [in] *pszTipText*  
 Yeni araç ipucu metni.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPane sınıfı](../../mfc/reference/cpane-class.md)   
 [CStatusBar Sınıfı](../../mfc/reference/cstatusbar-class.md)
