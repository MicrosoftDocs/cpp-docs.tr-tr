---
title: CMFCStatusBar Sınıfı
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
ms.openlocfilehash: 8f262d0139b6dffe54e16748ffda4938ba43fc08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366050"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar Sınıfı

Sınıf, `CMFCStatusBar` `CStatusBar` sınıfa benzer bir durum çubuğu uygular. Ancak, `CMFCStatusBar` sınıf, görüntüleri, animasyonları ve ilerleme çubuklarını görüntüleme yeteneği gibi `CStatusBar` sınıf tarafından sunulmayan özelliklere sahiptir; ve fare çift tıklama yanıt yeteneği.

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|[(Overrides CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCStatusBar::CommandtoIndex](#commandtoindex)||
|[CMFCStatusBar::Oluştur](#create)|Bir denetim çubuğu oluşturur ve [CPane](../../mfc/reference/cpane-class.md) nesnesine bağlar. [(CPane geçersiz kılar::Oluştur](../../mfc/reference/cpane-class.md#create).)|
|[CMFCStatusBar::CreateEx](#createex)|Bir denetim çubuğu oluşturur ve [CPane](../../mfc/reference/cpane-class.md) nesnesine bağlar. [(CPane geçersiz kılar::CreateEx](../../mfc/reference/cpane-class.md#createex).)|
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bu bölme ile üst çerçeve arasına dinamik olarak başka bir bölme eklenip eklenemeyeceğini belirler. [(Overrides CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Durum çubuğuna çift tıklamayla farenin kullanımını etkinleştirir veya devre dışı klarabilir.|
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Belirtilen bölmede bir ilerleme çubuğu görüntüler.|
|[CMFCStatusBar::GetCount](#getcount)|Durum çubuğundaki bölme sayısını verir.|
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCStatusBar::GetItemID](#getitemid)||
|[CMFCStatusBar::GetItemRect](#getitemrect)||
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||
|[CMFCStatusBar::GetPaneİlerleme](#getpaneprogress)||
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Bölme stilini döndürür. [(CBasePane geçersiz kılar::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|
|[CMFCStatusBar::GetPaneText](#getpanetext)||
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Durum çubuğunun belirtilen bölmesinin piksel cinsinden genişliğini verir.|
|[CMFCStatusBar::GetTipText](#gettiptext)|Durum çubuğunun belirtilen bölmesi için araç ipucu metnini döndürür.|
|[CMFCStatusBar::Geçersiz PaneContent](#invalidatepanecontent)|Belirtilen bölmeyi geçersiz kılınve içeriğini yeniden çizer.|
|[CMFCStatusBar::PyenidenCreateWindow](#precreatewindow)|Bu `CWnd` nesneye bağlı Windows penceresi nin oluşturulmasından önce çerçeve tarafından çağrılır. [(CWnd geçersiz kılar::Pyeniden CreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||
|[CMFCStatusBar::Göstergeler](#setindicators)||
|[CMFCStatusBar::SetPaneAnimasyon](#setpaneanimation)|Belirtilen bölmeye bir animasyon atar.|
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Durum çubuğunun belirtilen bölmesinin arka plan rengini ayarlar.|
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Durum çubuğunun belirtilen bölmesinin gösterge simgesini ayarlar.|
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||
|[CMFCStatusBar::SetPaneİlerleme](#setpaneprogress)|Durum çubuğunun belirtilen bölmesi için ilerleme çubuğunun geçerli ilerlemesini ayarlar.|
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Bölmenin stilini ayarlar. [(Overrides CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|
|[CMFCStatusBar::SetPaneText](#setpanetext)||
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Durum çubuğunun belirtilen bölmesi için metin rengini ayarlar.|
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Durum çubuğunun belirtilen bölmesinin piksellerinde genişliği ayarlar.|
|[CMFCStatusBar::SetTipText](#settiptext)|Durum çubuğunun belirtilen bölmesi için araç ipucu metnini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Durum çubuğunun bölmesini yeniden çizdiğinde çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki [diyagram, Durum Çubuğu Demo örnek](../../overview/visual-cpp-samples.md) uygulamasından durum çubuğunun bir figürünü gösterir.

![CMFCStatusBar örneği](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar örneği")

## <a name="example"></a>Örnek

Aşağıdaki örnek, uygulamanın `CMFCStatusBar` sınıftaki çeşitli yöntemleri çağırmak için kullandığı yerel değişkenleri gösterir. Bu değişkenler StatusBarDemoView.h olarak bildirilir. Ana çerçeve MainFrm.h'de ilan edilir, belge StatusBarDemoDoc.h'de bildirilir ve görünüm StatusBarDemoView.h'de bildirilir. Bu kod snippet [Durum Çubuğu Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCStatusBar` `GetStatusBar` MainFrm.h'de metodu tanıtarak ve bu yöntemi `GetStatusBar` StatusBarDemoView.h'deki yöntemden çağırarak nesneye nasıl başvuru alınabildiğini göstermektedir. Bu kod snippet [Durum Çubuğu Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, StatusBarDemoView.cpp'de sınıfta çeşitli yöntemlerin `CMFCStatusBar` nasıl çağrıldığını göstermektedir. Sabitler MainFrm.h'de beyan edilir. Örnek, simgeyi nasıl ayarlayacağını, durum çubuğu bölmesinin araç ipucu metnini nasıl ayarlayacağını, belirtilen bölmede bir ilerleme çubuğu nu görüntülemeyi, belirtilen bölmeye animasyon atamasını, metni ve durum çubuğu bölmesinin genişliğini nasıl ayarlayacağını ve durum çubuğu bölmesi için ilerleme çubuğunun geçerli ilerleme göstergesini nasıl ayarlayacağını gösterir. Bu kod snippet [Durum Çubuğu Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[Cmfcstatusbar](../../mfc/reference/cmfcstatusbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxstatusbar.h

## <a name="cmfcstatusbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCStatusBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

[içinde] *bStretch*<br/>
[içinde] *bHorz*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarcommandtoindex"></a><a name="commandtoindex"></a>CMFCStatusBar::CommandtoIndex

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *nIDFind*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarcreate"></a><a name="create"></a>CMFCStatusBar::Oluştur

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

[içinde] *pParentWnd*<br/>
[içinde] *dwStyle*<br/>
[içinde] *nID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarcreateex"></a><a name="createex"></a>CMFCStatusBar::CreateEx

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

[içinde] *pParentWnd*<br/>
[içinde] *dwCtrlStyle*<br/>
[içinde] *dwStyle*<br/>
[içinde] *nID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFCStatusBar::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarenablepanedoubleclick"></a><a name="enablepanedoubleclick"></a>CMFCStatusBar::EnablePaneDoubleClick

Durum çubuğuna çift tıklamayla farenin kullanımını etkinleştirir veya devre dışı klarabilir.

```
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] TRUE ise, farenin çift tıklatılmasını etkinleştirin. Aksi takdirde farenin işlenmesini çift tıklatma devre dışı kakın.

### <a name="remarks"></a>Açıklamalar

Durum çubuğunun çift tıklamaişlemi etkinleştirilirse, Windows WM_COMMAND bildirimini kaynak kimliğiyle birlikte durum çubuğunun sahibine gönderir ve kullanıcı durum çubuğu bölmesine her çift tıkladığında.

## <a name="cmfcstatusbarenablepaneprogressbar"></a><a name="enablepaneprogressbar"></a>CMFCStatusBar::EnablePaneProgressBar

Belirtilen bölmede bir ilerleme çubuğu görüntüleyin.

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

*Nındex*<br/>
[içinde] İlerleme çubuğuetkinleştirmek için bölmenin dizinbelirtir.

*nToplam*<br/>
[içinde] İlerleme çubuğu için en büyük değeri belirtir.

*bDisplayText*<br/>
[içinde] İlerleme çubuğunun geçerli ilerleme değerini gösterip göstermeyeceğini belirtir.

*clrBar*<br/>
[içinde] İlerleme çubuğunun arka plan rengini belirtir.

*clrBarDest*<br/>
[içinde] İlerleme çubuğu arka planının ikincil rengini belirtir. Bir degrade içine harmanlanmış bir renk ile doldurmak için *clrBar* farklı değeri kullanın.

*clrProgressText*<br/>
[içinde] İlerleme çubuğunun metninin rengini belirtir.

### <a name="remarks"></a>Açıklamalar

*NTotal* -1 olarak ayarlanmış ilerleme `EnablePaneProgressBar` çubuğu aramasını devre dışı kılabilir. Varsayılan *olarak nTotal* 100 olarak ayarlanır. Bu nedenle, ilerlemeyi yüzde olarak görüntülemek için ek hesaplamalara gerek yoktur.

İlerleme çubuğunun arka plan renginin bir degradeye harmanlanmış bir renk görüntülemesi için *clrBar* ve *clrBarDest* için farklı değerler geçirmelisiniz. .

Geçerli ilerlemeyi ayarlamak için [CMFCStatusBar::SetPaneProgress](#setpaneprogress) yöntemini arayın.

## <a name="cmfcstatusbargetcount"></a><a name="getcount"></a>CMFCStatusBar::GetCount

Durum çubuğundaki bölme sayısını alır.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğundaki bölme lerin sayısı.

## <a name="cmfcstatusbargetdrawextendedarea"></a><a name="getdrawextendedarea"></a>CMFCStatusBar::GetDrawExtendedArea

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetextendedarea"></a><a name="getextendedarea"></a>CMFCStatusBar::GetExtendedArea

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *rekt*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetitemid"></a><a name="getitemid"></a>CMFCStatusBar::GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *nIndex*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetitemrect"></a><a name="getitemrect"></a>CMFCStatusBar::GetItemRect

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *nIndex*<br/>
[içinde] *lpRect*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CMFCStatusBar::GetPaneInfo

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *nIndex*<br/>
[içinde] *nID*<br/>
[içinde] *nStyle*<br/>
[içinde] *cxGenişlik*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpaneprogress"></a><a name="getpaneprogress"></a>CMFCStatusBar::GetPaneİlerleme

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *nIndex*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpanestyle"></a><a name="getpanestyle"></a>CMFCStatusBar::GetPaneStyle

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *nIndex*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpanetext"></a><a name="getpanetext"></a>CMFCStatusBar::GetPaneText

```
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *nIndex*<br/>
[içinde] *s*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpanewidth"></a><a name="getpanewidth"></a>CMFCStatusBar::GetPaneWidth

Durum çubuğunun bölmesinin genişliğini alır.

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Durum çubuğu bölmesinin dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

*nIndex'in* belirttiği durum çubuğu bölmesinin genişliği; aksi takdirde, durum çubuğu bölmesi yoksa sıfır.

## <a name="cmfcstatusbargettiptext"></a><a name="gettiptext"></a>CMFCStatusBar::GetTipText

Durum çubuğu bölmesinin araç ipucu metnini alın.

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Araç ipucu metnini almak için bölmenin dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

*nIndex'in* belirttiği durum çubuğu bölmesinin araç ipucu metni. Aksi takdirde, belirtilen *nIndex* için bir durum çubuğu bölmesi yoksa veya araç ipucu metni boşsa boş dize.

## <a name="cmfcstatusbarinvalidatepanecontent"></a><a name="invalidatepanecontent"></a>CMFCStatusBar::Geçersiz PaneContent

Durum çubuğu bölmesini geçersiz kılın ve içeriğini yeniden çizin.

```
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] İçeriği geçersiz kılınacak ve yeniden çizilecek bölmenin dizinini belirtir.

### <a name="remarks"></a>Açıklamalar

Durum çubuğu geçersiz kılındığında, yeniden çizmek için işaretlenir. `UpdateWindow` Yöntem yönteme WM_PAINT ileti gönderdiğinde Windows `OnPaint` bu iletiyi yeniden çizer.

## <a name="cmfcstatusbarondrawpane"></a><a name="ondrawpane"></a>CMFCStatusBar::OnDrawPane

Durum çubuğunun bölmesini yeniden çizin.

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Çizim için aygıt bağlamına işaretçi.

*pPane*<br/>
[içinde] Yeniden çizilecek `CMFCStatusBarPaneInfo` bölme yle ilgili bilgileri içeren bir yapıya işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `OnDrawPane` bölmenin stiline ve içeriğine göre aygıt *bağlamı pDC'sini* kullanarak bölmeyi yeniden çizer.

Bölmegörünümünü özelleştirmek `CMFCStatusBar`için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfcstatusbarprecreatewindow"></a><a name="precreatewindow"></a>CMFCStatusBar::PyenidenCreateWindow

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Parametreler

[içinde] *cs*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetdrawextendedarea"></a><a name="setdrawextendedarea"></a>CMFCStatusBar::SetDrawExtendedArea

```
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

[içinde] *bSet*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetindicators"></a><a name="setindicators"></a>CMFCStatusBar::Göstergeler

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parametreler

[içinde] *lpIDArray*<br/>
[içinde] *nIDSayısı*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetpaneanimation"></a><a name="setpaneanimation"></a>CMFCStatusBar::SetPaneAnimasyon

Belirtilen bölmeye bir animasyon atar.

```
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Ona animasyon atamak istediğiniz bölmenin dizinini belirtir.

*hImageList*<br/>
[içinde] Animasyon çerçevelerini tutan görüntü listesine bir tanıtıcı belirtir.

*nFrameRate*<br/>
[içinde] Animasyon için kare hızını milisaniye cinsinden belirtir.

*Bgüncelleştirme*<br/>
[içinde] TRUE ise, bölme içeriğini hemen güncelleştirin. Aksi takdirde, bölme içeriği geçersiz kılındığında güncelleştirilir.

### <a name="remarks"></a>Açıklamalar

Geçerli animasyonu devre dışı kakmak `SetPaneAnimation` `hImageList` istiyorsanız, NULL olarak ayarla'yı arayın.

## <a name="cmfcstatusbarsetpanebackgroundcolor"></a><a name="setpanebackgroundcolor"></a>CMFCStatusBar::SetPaneBackgroundColor

Durum çubuğu bölmesinin arka plan rengini ayarlar.

```
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Yeni bir arka plan rengi ayarlamak için bölmenin dizinini belirtir.

*clrArka*<br/>
[içinde] Yeni arka plan rengini belirtir.

*Bgüncelleştirme*<br/>
[içinde] TRUE ise, bölme içeriğini hemen güncelleştirin. Aksi takdirde, bölme başka bir yöntemle geçersiz kılınana kadar bölme içeriğini güncelleştirmeyin.

## <a name="cmfcstatusbarsetpaneicon"></a><a name="setpaneicon"></a>CMFCStatusBar::SetPaneIcon

Durum çubuğu bölmesi simgesini ayarlayın.

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

*Nındex*<br/>
[içinde] Görüntüyü ayarlamak için bölmenin dizinini belirtir.

*Hıcon*<br/>
[içinde] Bölme görüntüsü olarak ayarlanacak simgeye bir tutamaç belirtir.

*Bgüncelleştirme*<br/>
[içinde] Bölme içeriğini hemen güncelleştirip güncelleştirmeyeceğini belirtir.

*hBmp*<br/>
[içinde] Bölme görüntüsü olarak ayarlanacak bit eşlemi için bir tutamaç belirtir.

*clrŞeffaf*<br/>
[içinde] *hBmp'nin* gösterdiği bit eşleminin saydam rengini belirtir.

### <a name="remarks"></a>Açıklamalar

Bölmenin görüntüsünü ayarlamak için saydam renkle birlikte HICON veya HBITMAP'i geçebilirsiniz. Görüntüyü daha fazla görüntülemek istemiyorsanız, görüntü tutamacı olarak NULL değerini geçirin.

[CMFCStatusBar::SetPaneAnimation'in](#setpaneanimation) ayardığı çalışan animasyon varsa, animasyon durdurulur.

## <a name="cmfcstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a>CMFCStatusBar::SetPaneInfo

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Parametreler

[içinde] *nIndex*<br/>
[içinde] *nID*<br/>
[içinde] *nStyle*<br/>
[içinde] *cxGenişlik*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetpaneprogress"></a><a name="setpaneprogress"></a>CMFCStatusBar::SetPaneİlerleme

Belirtilen bölme için ilerleme çubuğunun geçerli ilerleme göstergesini ayarlayın.

```
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] İlerleme göstergesini güncelleştirmek için bölmenin dizinini belirtir.

*nCurr*<br/>
[içinde] İlerleme göstergesinin geçerli değerini belirtir.

*Bgüncelleştirme*<br/>
[içinde] Bölmenin hemen güncelleştirilip güncellenmemesi gerektiğini belirtir.

### <a name="remarks"></a>Açıklamalar

Belirtilen bölmedeki ilerleme çubuğunun ilerleme göstergesini güncelleştirmek istediğinizde bu yöntemi arayın.

Verilen bölme için bu işlevi kullanmak için önce [CMFCStatusBar::EnablePaneProgressBar'ı](#enablepaneprogressbar) aramalısınız.

## <a name="cmfcstatusbarsetpanestyle"></a><a name="setpanestyle"></a>CMFCStatusBar::SetPaneStyle

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

[içinde] *nIndex*<br/>
[içinde] *nStyle*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetpanetext"></a><a name="setpanetext"></a>CMFCStatusBar::SetPaneText

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Parametreler

[içinde] *nIndex*<br/>
[içinde] *lpszNewText*<br/>
[içinde] *bUpdate*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetpanetextcolor"></a><a name="setpanetextcolor"></a>CMFCStatusBar::SetPaneTextColor

Belirtilen bölmenin metin rengini ayarlar.

```
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Yeni bir metin rengi atamak istediğiniz bölmenin dizinini belirtir.

*clrMetin*<br/>
[içinde] Metin rengini belirtir.

*Bgüncelleştirme*<br/>
[içinde] TRUE ise, bölme içeriğini hemen güncelleştirin. Aksi takdirde, bölme başka bir yöntemle geçersiz kılınana kadar bölme içeriğini güncelleştirmeyin.

## <a name="cmfcstatusbarsetpanewidth"></a><a name="setpanewidth"></a>CMFCStatusBar::SetPaneWidth

Durum çubuğu bölmesinin genişliğini ayarlayın.

```
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Yeni bir genişlik ayarlamak için durum çubuğu bölmesi dizin.

*Cx*<br/>
[içinde] Durum çubuğu bölmesinin yeni genişliği piksel olarak.

## <a name="cmfcstatusbarsettiptext"></a><a name="settiptext"></a>CMFCStatusBar::SetTipText

Durum çubuğu bölmesinin araç ipucu metnini ayarlayın.

```
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Araç ipucu metnini atamak istediğiniz bölmenin dizini.

*pszTipText*<br/>
[içinde] Yeni araç ipucu metni.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPane Sınıfı](../../mfc/reference/cpane-class.md)<br/>
[CStatusBar Sınıfı](../../mfc/reference/cstatusbar-class.md)
