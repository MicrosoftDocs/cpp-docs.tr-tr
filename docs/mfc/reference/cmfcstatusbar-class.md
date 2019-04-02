---
title: CMFCStatusBar sınıfı
ms.date: 11/19/2018
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
ms.openlocfilehash: 87f75769e2f400a7721a8c9089d6c5596c31a4e3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775965"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar sınıfı

`CMFCStatusBar` Sınıfı için benzer bir durum çubuğu uygular `CStatusBar` sınıfı. Ancak, `CMFCStatusBar` sınıfı tarafından önerilmeyen özelliklere sahiptir `CStatusBar` resimleri, animasyonları ve ilerleme çubuğunu görüntüleme ve çift tıklamalara yanıt verme gibi bir sınıf.

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

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
|[CMFCStatusBar::Create](#create)|Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesne. (Geçersiz kılmaları [CPane::Create](../../mfc/reference/cpane-class.md#create).)|
|[CMFCStatusBar::CreateEx](#createex)|Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesne. (Geçersiz kılmaları [CPane::CreateEx](../../mfc/reference/cpane-class.md#createex).)|
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Başka bir bölmesinde dinamik olarak bu bölme ve üst çerçevenin arasında eklenip eklenemeyeceğini belirler. (Geçersiz kılmaları [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Fare işleme etkinleştirir veya devre dışı bırakır ve durum çubuğunda çift tıkladığında.|
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Belirtilen bölmedeki bir ilerleme çubuğu görüntüler.|
|[CMFCStatusBar::GetCount](#getcount)|Durum çubuğunda bölmeleri sayısını döndürür.|
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCStatusBar::GetItemID](#getitemid)||
|[CMFCStatusBar::GetItemRect](#getitemrect)||
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Bölmesinde stili döndürür. (Geçersiz kılmaları [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|
|[CMFCStatusBar::GetPaneText](#getpanetext)||
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Belirtilen durum çubuğu bölmesinin piksel cinsinden genişliğini döndürür.|
|[CMFCStatusBar::GetTipText](#gettiptext)|Belirtilen durum çubuğu bölmesinin araç ipucu metnini döndürür.|
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|Belirtilen bölmesinde geçersiz kılar ve içeriğini yeniden çizer.|
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Şuna bağlı Windows penceresi oluşturulmasını önce framework tarafından çağırılır `CWnd` nesne. (Geçersiz kılmaları [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||
|[CMFCStatusBar::SetIndicators](#setindicators)||
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Bir animasyon belirtilen bölmesine atar.|
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Belirtilen durum çubuğu bölmesinin arka plan rengini ayarlar.|
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Belirtilen durum çubuğu bölmesinin gösterge simgesi ayarlar.|
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|İlerleme çubuğu için belirtilen durum çubuğu bölmesinin geçerli durumunu ayarlar.|
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Bölmesinin stilini ayarlar. (Geçersiz kılmaları [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|
|[CMFCStatusBar::SetPaneText](#setpanetext)||
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Belirtilen durum çubuğu bölmesinin metin rengini belirler.|
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Belirtilen bölmesinin durum çubuğunun piksel cinsinden genişliğini belirler.|
|[CMFCStatusBar::SetTipText](#settiptext)|Belirtilen durum çubuğu bölmesinin araç ipucu metnini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Durum çubuğu bölmesinin çizer framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Durum çubuğunda bir şekilden Aşağıdaki diyagramda gösterilmiştir [durum çubuğu gösterim örneği](../../overview/visual-cpp-samples.md) uygulama.

![CMFCStatusBar örneği](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar örneği")

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemleri çağırmak için uygulamanın kullandığı yerel değişkenlerini gösterir `CMFCStatusBar` sınıfı. Bu değişkenler StatusBarDemoView.h bildirilir. Ana çerçeve MainFrm.h içinde bildirildiği belge içinde StatusBarDemoDoc.h bildirilir ve görünümü içinde StatusBarDemoView.h bildirilir. Bu kod parçacığı parçasıdır [durum çubuğu gösterim örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir başvuru almak gösterilmiştir `CMFCStatusBar` giriş nesnesi `GetStatusBar` MainFrm.h ve ardından bu yöntemi çağırmadan yöntemi `GetStatusBar` StatusBarDemoView.h yöntemi. Bu kod parçacığı parçasıdır [durum çubuğu gösterim örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemleri çağırmak gösterilmiştir `CMFCStatusBar` StatusBarDemoView.cpp sınıfta. Sabitler MainFrm.h bildirilir. Örnek Ayarla simgesi, durum çubuğu bölmesinin araç ipucu metnini ayarlamak, belirtilen bölmesinde bir ilerleme çubuğu gösteriliyor, animasyon için belirtilen bölmesinde atamak, metin ve durum çubuğu bölmesinin genişliğini ayarlamak ve progr geçerli ilerleme göstergesini ayarlamak nasıl gösterir Durum çubuğu bölmesinin çubuğu Sırala. Bu kod parçacığı parçasıdır [durum çubuğu gösterim örneği](../../overview/visual-cpp-samples.md).

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

[in] *bStretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="commandtoindex"></a>  CMFCStatusBar::CommandToIndex

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parametreler

[in] *nIDFind*<br/>

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

[in] *pParentWnd*<br/>
[in] *dwStyle*<br/>
[in] *nID*<br/>

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

[in] *pParentWnd*<br/>
[in] *dwCtrlStyle*<br/>
[in] *dwStyle*<br/>
[in] *nID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="doesallowdyninsertbefore"></a>  CMFCStatusBar::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="enablepanedoubleclick"></a>  CMFCStatusBar::EnablePaneDoubleClick

Fare işleme etkinleştirir veya devre dışı bırakır ve durum çubuğunda çift tıkladığında.

```
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] TRUE ise, fare çift tıklatması işlenmesini sağlar. Aksi takdirde, fare çift tıklatması işlenmesini devre dışı bırakın.

### <a name="remarks"></a>Açıklamalar

Durum çubuğunu çift tıklatma işlemek için etkinse, Windows durum çubuğu kullanıcı çift tıkladığında durum çubuğu bölmesinde her seferinde sahibi bir kaynak kimliği ile birlikte WM_COMMAND bildirim gönderir.

##  <a name="enablepaneprogressbar"></a>  CMFCStatusBar::EnablePaneProgressBar

Belirtilen bölmesinde bir ilerleme çubuğu görüntüler.

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

*nIndex*<br/>
[in] Etkinleştirmek için ilerleme çubuğu bölmesi dizinini belirtir.

*nAkışlara*<br/>
[in] İlerleme çubuğu için maksimum değeri belirtir.

*bDisplayText*<br/>
[in] İlerleme çubuğu geçerli ilerleme değer görüntülemesi gerekip gerekmediğini belirtir.

*clrBar*<br/>
[in] İlerleme çubuğu arka plan rengini belirtir.

*clrBarDest*<br/>
[in] İlerleme çubuğu arka plan ikincil rengi belirtir. Değerinden farklı bir değer kullanmazsanız *clrBar* gradyan karışık bir renge göre doldurmak için.

*clrProgressText*<br/>
[in] İlerleme çubuğu metninin rengini belirtir.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğu çağrısı devre dışı bırakmak isterseniz `EnablePaneProgressBar` ile *nAkışlara* -1 olarak ayarlayın. Varsayılan olarak *nAkışlara* 100'e ayarlayın. Bu nedenle, yüzde olarak ilerleme durumunu görüntülemek için diğer tüm hesaplamalar gerekmez.

Farklı değerler geçmelidir *clrBar* ve *clrBarDest* gradyan karışık bir renk ilerleme çubuğu arka plan rengini görüntüler. biçimindeki telefon numarasıdır.

Geçerli ilerleme durumunu ayarlamak için çağrı [CMFCStatusBar::SetPaneProgress](#setpaneprogress) yöntemi.

##  <a name="getcount"></a>  CMFCStatusBar::GetCount

Durum çubuğunda bölmeleri sayısını alır.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğunda bölmeleri sayısı.

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

[in] *dikdörtgen*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getitemid"></a>  CMFCStatusBar::GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

[in] *nIndex*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getitemrect"></a>  CMFCStatusBar::GetItemRect

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

[in] *nIndex*<br/>
[in] *lpRect*<br/>

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

[in] *nIndex*<br/>
[in] *nID*<br/>
[in] *nStyle*<br/>
[in] *cxWidth*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="getpaneprogress"></a>  CMFCStatusBar::GetPaneProgress

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

[in] *nIndex*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getpanestyle"></a>  CMFCStatusBar::GetPaneStyle

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

[in] *nIndex*<br/>

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

[in] *nIndex*<br/>
[in] *s*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getpanewidth"></a>  CMFCStatusBar::GetPaneWidth

Durum çubuğu bölmesinin genişliğini alır.

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] Durum çubuğu bölmesinin dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu bölmesinin genişliğini, *nIndex* belirtir; durum çubuğu bölmesinin yoksa, aksi takdirde, sıfır.

##  <a name="gettiptext"></a>  CMFCStatusBar::GetTipText

Bir durum çubuğu bölmesinin araç ipucu metnini alır.

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] Araç ipucu metnini almak bölmesi dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu bölmesinin araç ipucu metnini, *nIndex* belirtir. Aksi takdirde boş dize bir durum çubuğu bölmesinin belirtilen mevcut değilse *nIndex* veya araç ipucu metnini boşsa.

##  <a name="invalidatepanecontent"></a>  CMFCStatusBar::InvalidatePaneContent

Durum çubuğu bölmesinin geçersiz kılmak ve içeriği yeniden çizin.

```
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] İçerikleri geçersiz kılındı ve yeniden düzenlenmiş olan bölmesinin dizinini belirtir.

### <a name="remarks"></a>Açıklamalar

Durum çubuğunda geçersiz kılınması yeniden için işaretlenir. Windows çizer olduğunda `UpdateWindow` yöntemi WM_PAINT ileti gönderir `OnPaint` yöntemi.

##  <a name="ondrawpane"></a>  CMFCStatusBar::OnDrawPane

Durum çubuğu bölmesinin yeniden çizin.

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Çizim için bir cihaz bağlamı için bir işaretçi.

*pPane*<br/>
[in] Bir işaretçi bir `CMFCStatusBarPaneInfo` çizilmesini bölmesinde ilgili bilgiler içeren yapısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `OnDrawPane` bölmesinde cihaz bağlamını kullanarak yeniden çizer *pDC* bölmedeki stil ve içeriğe göre.

Bu yöntemin bir `CMFCStatusBar`-türetilmiş bölme görünümünü özelleştirmek için sınıf.

##  <a name="precreatewindow"></a>  CMFCStatusBar::PreCreateWindow

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Parametreler

[in] *cs*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="setdrawextendedarea"></a>  CMFCStatusBar::SetDrawExtendedArea

```
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

[in] *bInternet*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="setindicators"></a>  CMFCStatusBar::SetIndicators

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parametreler

[in] *lpIDArray*<br/>
[in] *nIDCount*<br/>

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

*nIndex*<br/>
[in] Bir animasyon atamak istediğiniz bölmesi dizinini belirtir.

*hImageList*<br/>
[in] Animasyon kareleri tutan resim listesi için bir tanıtıcı belirtir.

*nFrameRate*<br/>
[in] Kare hızı, animasyon için milisaniye cinsinden belirtir.

*bgüncelleştirmesinin*<br/>
[in] TRUE ise bölmesinde içeriği hemen güncelleştirin. Aksi takdirde, geçersiz kılınması bölmesinde içeriği güncelleştirilir.

### <a name="remarks"></a>Açıklamalar

Geçerli animasyon devre dışı bırakmak isterseniz, çağrı `SetPaneAnimation` ile `hImageList` NULL olarak ayarlayın.

##  <a name="setpanebackgroundcolor"></a>  CMFCStatusBar::SetPaneBackgroundColor

Durum çubuğu bölmesinin arka plan rengini ayarlar.

```
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] Bölmesinde yeni bir arka plan rengini ayarlamak istediğiniz dizini belirtir.

*clrBackground*<br/>
[in] Yeni arka plan rengini belirtir.

*bgüncelleştirmesinin*<br/>
[in] TRUE ise bölmesinde içeriği hemen güncelleştirin. Aksi takdirde, bölmesinde farklı bir yöntemle geçersiz kadar bölmesinde içeriği güncelleştirmez.

##  <a name="setpaneicon"></a>  CMFCStatusBar::SetPaneIcon

Durum çubuğu bölmesinin simgeyi ayarlayın.

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

*nIndex*<br/>
[in] Bölmesinin resmi ayarlamak istediğiniz dizini belirtir.

*hIcon*<br/>
[in] Bölmesinde görüntüsü olarak ayarlanacak simgesi için bir tanıtıcı belirtir.

*bgüncelleştirmesinin*<br/>
[in] İçerik bölmesinde hemen güncelleştirilip güncelleştirilmeyeceğini belirtir.

*hBmp*<br/>
[in] Bit eşlem bölmesinde görüntüsü olarak ayarlanacak için bir tanıtıcı belirtir.

*clrTransparent*<br/>
[in] Bit eşlem saydam rengini belirtir, *hBmp* gösterir.

### <a name="remarks"></a>Açıklamalar

Bölmedeki resmi ayarlamak için saydam rengi ile birlikte HICON ya da HBITMAP geçirebilirsiniz. Artık görüntüyü istemiyorsanız NULL değeri görüntü tanıtıcı geçirin.

Çalışan tüm animasyon ise, [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) sahip ayarlayın, animasyon durdurulur.

##  <a name="setpaneinfo"></a>  CMFCStatusBar::SetPaneInfo

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Parametreler

[in] *nIndex*<br/>
[in] *nID*<br/>
[in] *nStyle*<br/>
[in] *cxWidth*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="setpaneprogress"></a>  CMFCStatusBar::SetPaneProgress

Belirtilen bölmesi için ilerleme çubuğunun geçerli ilerleme göstergesi ayarlayın.

```
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] İlerleme göstergesi güncelleştirileceği bölmesi dizinini belirtir.

*nCurr*<br/>
[in] İlerleme göstergesi geçerli değerini belirtir.

*bgüncelleştirmesinin*<br/>
[in] Bölmesinde hemen güncelleştirilmesi gerekip gerekmediğini belirtir.

### <a name="remarks"></a>Açıklamalar

Belirtilen bölmesinde ilerleme çubuğu için İlerleme göstergesi güncelleştireceğinizi kaldığında bu yöntemi çağırın.

Verilen bölmesi bu işlevi kullanmak için çağırmalıdır [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) ilk.

##  <a name="setpanestyle"></a>  CMFCStatusBar::SetPaneStyle

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

[in] *nIndex*<br/>
[in] *nStyle*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="setpanetext"></a>  CMFCStatusBar::SetPaneText

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Parametreler

[in] *nIndex*<br/>
[in] *lpszNewText*<br/>
[in] *bgüncelleştirmesinin*<br/>

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

*nIndex*<br/>
[in] Yeni bir metin rengi atamak istediğiniz bölmesinin dizinini belirtir.

*clrText*<br/>
[in] Metin rengini belirtir.

*bgüncelleştirmesinin*<br/>
[in] TRUE ise bölmesinde içeriği hemen güncelleştirin. Aksi takdirde, bölmesinde farklı bir yöntemle geçersiz kadar bölmesinde içeriği güncelleştirmez.

##  <a name="setpanewidth"></a>  CMFCStatusBar::SetPaneWidth

Durum çubuğu bölmesinin genişliğini ayarlayın.

```
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] Yeni bir genişlik ayarlanacak durum çubuğu bölmesinin dizini.

*cx*<br/>
[in] Durum çubuğu bölmesinin piksel cinsinden yeni genişliği.

##  <a name="settiptext"></a>  CMFCStatusBar::SetTipText

Durum çubuğu bölmesinin araç ipucu metni ayarlayın.

```
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] Araç İpucu metni atamak istediğiniz bölmesinde dizini.

*pszTipText*<br/>
[in] Yeni araç ipucu metni.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPane Sınıfı](../../mfc/reference/cpane-class.md)<br/>
[CStatusBar Sınıfı](../../mfc/reference/cstatusbar-class.md)
