---
description: 'Daha fazla bilgi edinin: CMFCStatusBar sınıfı'
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
ms.openlocfilehash: 79ba7c749a73406893173d7486fd5df208a37b83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307086"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar sınıfı

`CMFCStatusBar`Sınıfı, sınıfına benzer bir durum çubuğu uygular `CStatusBar` . Ancak, sınıfı, görüntü `CMFCStatusBar` `CStatusBar` , animasyon ve ilerleme çubuğu gibi, fare çift tıklamalarına yanıt verebilme gibi sınıf tarafından sunulmayan özelliklere sahiptir.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCStatusBar:: CalcFixedLayout](#calcfixedlayout)|( [CBasePane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).) öğesini geçersiz kılar|
|[CMFCStatusBar:: CommandToIndex](#commandtoindex)||
|[CMFCStatusBar:: Create](#create)|Bir denetim çubuğu oluşturur ve bunu [CPane](../../mfc/reference/cpane-class.md) nesnesine ekler. ( [CPane:: Create](../../mfc/reference/cpane-class.md#create)geçersiz kılar.)|
|[CMFCStatusBar:: CreateEx](#createex)|Bir denetim çubuğu oluşturur ve bunu [CPane](../../mfc/reference/cpane-class.md) nesnesine ekler. ( [CPane:: CreateEx](../../mfc/reference/cpane-class.md#createex)geçersiz kılar.)|
|[CMFCStatusBar::D Oesallowdynınsertbefore](#doesallowdyninsertbefore)|Bu bölme ve üst çerçeve arasında dinamik olarak bir bölme eklenip eklenemeyeceğini belirler. ( [CBasePane::D Oesallowdynınsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore)geçersiz kılar.)|
|[CMFCStatusBar:: Enablebölmesi DoubleClick](#enablepanedoubleclick)|Durum çubuğunda fare çift tıklamasının işlenmesini mümkün veya devre dışı bırakır.|
|[CMFCStatusBar:: Enablebölmesi ProgressBar](#enablepaneprogressbar)|Belirtilen bölmedeki bir ilerleme çubuğunu görüntüler.|
|[CMFCStatusBar:: GetCount](#getcount)|Durum çubuğundaki bölme sayısını döndürür.|
|[CMFCStatusBar:: GetDrawExtendedArea](#getdrawextendedarea)||
|[CMFCStatusBar:: Gebir Dedarea](#getextendedarea)||
|[CMFCStatusBar:: GetItemID](#getitemid)||
|[CMFCStatusBar:: GetItemRect](#getitemrect)||
|[CMFCStatusBar:: Getbölmesi bilgileri](#getpaneinfo)||
|[CMFCStatusBar:: Getbölmesi Ilerlemesi](#getpaneprogress)||
|[CMFCStatusBar:: Getbölmesi stili](#getpanestyle)|Bölme stilini döndürür. ( [CBasePane:: Getbölmesi stilini](../../mfc/reference/cbasepane-class.md#getpanestyle)geçersiz kılar.)|
|[CMFCStatusBar:: Getbölmesi metni](#getpanetext)||
|[CMFCStatusBar:: Getbölmesi genişliği](#getpanewidth)|Durum çubuğunun belirtilen bölmesinin piksel cinsinden genişliğini döndürür.|
|[CMFCStatusBar:: GetTipText](#gettiptext)|Durum çubuğunun belirtilen bölmesi için araç ipucu metnini döndürür.|
|[CMFCStatusBar:: ınvalidatebölmesi Içeriği](#invalidatepanecontent)|Belirtilen bölmeyi geçersiz kılar ve içeriğini yeniden çizer.|
|[CMFCStatusBar::P reCreateWindow](#precreatewindow)|Bu nesneye eklenen Windows penceresinin oluşturulmasından önce Framework tarafından çağırılır `CWnd` . ( [CWnd::P recreatewindow](../../mfc/reference/cwnd-class.md#precreatewindow).) öğesini geçersiz kılar|
|[CMFCStatusBar:: SetDrawExtendedArea](#setdrawextendedarea)||
|[CMFCStatusBar:: SetIndicators](#setindicators)||
|[CMFCStatusBar:: Setbölmesi animasyonu](#setpaneanimation)|Belirtilen bölmeye bir animasyon atar.|
|[CMFCStatusBar:: Setbölmesi BackgroundColor](#setpanebackgroundcolor)|Durum çubuğunun belirtilen bölmesi için arka plan rengini ayarlar.|
|[CMFCStatusBar:: SetPaneIcon](#setpaneicon)|Durum çubuğunun belirtilen bölmesi için gösterge simgesini ayarlar.|
|[CMFCStatusBar:: Setbölmesi bilgileri](#setpaneinfo)||
|[CMFCStatusBar:: Setbölmesi Ilerlemesi](#setpaneprogress)|Durum çubuğunun belirtilen bölmesi için ilerleme çubuğunun geçerli ilerlemesini ayarlar.|
|[CMFCStatusBar:: Setbölmesi stili](#setpanestyle)|Bölmenin stilini ayarlar. ( [CBasePane:: Setbölmesi stilini](../../mfc/reference/cbasepane-class.md#setpanestyle)geçersiz kılar.)|
|[CMFCStatusBar:: Setbölmesi metni](#setpanetext)||
|[CMFCStatusBar:: Setbölmesi TextColor](#setpanetextcolor)|Durum çubuğunun belirtilen bölmesi için metin rengini ayarlar.|
|[CMFCStatusBar:: Setbölmesi genişliği](#setpanewidth)|Durum çubuğunun belirtilen bölmesinin piksel cinsinden genişliğini ayarlar.|
|[CMFCStatusBar:: SetTipText](#settiptext)|Durum çubuğunun belirtilen bölmesi için araç ipucu metnini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCStatusBar:: OnDrawPane](#ondrawpane)|Durum çubuğunun bölmesini yeniden çizer çerçevesi tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki diyagramda durum çubuğu [tanıtım örneği](../../overview/visual-cpp-samples.md) uygulamasındaki durum çubuğunun bir şekli gösterilmektedir.

![CMFCStatusBar örneği](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar örneği")

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, uygulamanın sınıfındaki çeşitli yöntemleri çağırmak için kullandığı yerel değişkenleri gösterir `CMFCStatusBar` . Bu değişkenler StatusBarDemoView. h içinde bildirilmiştir. Ana çerçeve MainFrm. h içinde bildirildiği için, belge StatusBarDemoDoc. h içinde bildirilmiştir ve görünüm StatusBarDemoView. h içinde bildirilmiştir. Bu kod parçacığı, [durum çubuğu tanıtım örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

Aşağıdaki örnek, `CMFCStatusBar` `GetStatusBar` MainFrm. h içindeki yöntemine bakarak ve sonra bu yöntemi `GetStatusBar` StatusBarDemoView. h içindeki yöntemden çağırarak nesnesine nasıl başvuru alınacağını göstermektedir. Bu kod parçacığı, [durum çubuğu tanıtım örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

Aşağıdaki örnek, `CMFCStatusBar` StatusBarDemoView. cpp sınıfında çeşitli yöntemlerin nasıl çağrılacağını gösterir. Sabitler MainFrm. h içinde bildirilmiştir. Örnekte, simgenin nasıl ayarlanacağı, durum çubuğu bölmesinin araç ipucu metnini nasıl ayarlanacağı, belirtilen bölmede bir ilerleme çubuğu görüntüleme, belirtilen bölmeye bir animasyon atama, durum çubuğu bölmesinin metin ve genişliğini ayarlama ve durum çubuğu bölmesinin ilerleme çubuğunun geçerli ilerleme göstergesini ayarlama işlemlerinin nasıl yapılacağı gösterilmektedir. Bu kod parçacığı, [durum çubuğu tanıtım örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

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

**Üstbilgi:** afxstatusbar. h

## <a name="cmfcstatusbarcalcfixedlayout"></a><a name="calcfixedlayout"></a> CMFCStatusBar:: CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

'ndaki *Besnetme*<br/>
'ndaki *bHorz*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarcommandtoindex"></a><a name="commandtoindex"></a> CMFCStatusBar:: CommandToIndex

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Nıdfind*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarcreate"></a><a name="create"></a> CMFCStatusBar:: Create

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

'ndaki *pParentWnd*<br/>
'ndaki *dwStyle*<br/>
'ndaki *NID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarcreateex"></a><a name="createex"></a> CMFCStatusBar:: CreateEx

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

'ndaki *pParentWnd*<br/>
'ndaki *dwCtrlStyle*<br/>
'ndaki *dwStyle*<br/>
'ndaki *NID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCStatusBar::D Oesallowdynınsertbefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarenablepanedoubleclick"></a><a name="enablepanedoubleclick"></a> CMFCStatusBar:: Enablebölmesi DoubleClick

Durum çubuğunda fare çift tıklamasının işlenmesini mümkün veya devre dışı bırakır.

```cpp
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki DOĞRU ise, fare çift tıklamasını etkinleştirin. Aksi takdirde fare çift tıklamasını devre dışı bırakın.

### <a name="remarks"></a>Açıklamalar

Durum çubuğu çift tıklamaları işlemek üzere etkinleştirilmişse, Windows, durum çubuğu bölmesinde kullanıcı çift tıkladığında durum çubuğunun sahibine bir kaynak KIMLIĞIYLE birlikte WM_COMMAND bildirimi gönderir.

## <a name="cmfcstatusbarenablepaneprogressbar"></a><a name="enablepaneprogressbar"></a> CMFCStatusBar:: Enablebölmesi ProgressBar

Belirtilen bölmede bir ilerleme çubuğu görüntüler.

```cpp
void EnablePaneProgressBar(
    int nIndex,
    long nTotal=100,
    BOOL bDisplayText=FALSE,
    COLORREF clrBar=-1,
    COLORREF clrBarDest=-1,
    COLORREF clrProgressText=-1);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki İlerleme çubuğu etkinleştirilecek olan bölmenin dizinini belirtir.

*Ntoplam*<br/>
'ndaki İlerleme çubuğunun en büyük değerini belirtir.

*Bgörüntümetni*<br/>
'ndaki İlerleme çubuğunun geçerli ilerleme değerini görüntüleyip görüntülememeyeceğini belirtir.

*clrBar*<br/>
'ndaki İlerleme çubuğunun arka plan rengini belirtir.

*clrBarDest*<br/>
'ndaki İlerleme çubuğunun arka planının ikincil rengini belirtir. Bir degradeyle karıştırılan renkle doldurulacak şekilde *clrBar* 'ten farklı bir değer kullanın.

*clrProgressText*<br/>
'ndaki İlerleme çubuğu metninin rengini belirtir.

### <a name="remarks"></a>Açıklamalar

İlerleme çubuğu çağrısını `EnablePaneProgressBar` *nTotal* ile-1 olarak ayarlamak istiyorsanız. Varsayılan olarak, *nTotal* , 100 olarak ayarlanmıştır. Bu nedenle, ilerlemeyi yüzde olarak göstermek için ek hesaplamalar yapmanız gerekmez.

İlerleme çubuğunun arka plan renginin degradeyle karışan bir renk görüntüleyeceği şekilde *clrBar* ve *clrBarDest* için farklı değerler geçirmeniz gerekir. .

Geçerli ilerlemeyi ayarlamak için [CMFCStatusBar:: Setbölmesi Progress](#setpaneprogress) metodunu çağırın.

## <a name="cmfcstatusbargetcount"></a><a name="getcount"></a> CMFCStatusBar:: GetCount

Durum çubuğundaki bölme sayısını alır.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğundaki bölme sayısı.

## <a name="cmfcstatusbargetdrawextendedarea"></a><a name="getdrawextendedarea"></a> CMFCStatusBar:: GetDrawExtendedArea

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetextendedarea"></a><a name="getextendedarea"></a> CMFCStatusBar:: Gebir Dedarea

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Rect*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetitemid"></a><a name="getitemid"></a> CMFCStatusBar:: GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *nDizin*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetitemrect"></a><a name="getitemrect"></a> CMFCStatusBar:: GetItemRect

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *nDizin*<br/>
'ndaki *lpRect*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpaneinfo"></a><a name="getpaneinfo"></a> CMFCStatusBar:: Getbölmesi bilgileri

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *nDizin*<br/>
'ndaki *NID*<br/>
'ndaki *nStyle*<br/>
'ndaki *Cxwidth*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpaneprogress"></a><a name="getpaneprogress"></a> CMFCStatusBar:: Getbölmesi Ilerlemesi

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *nDizin*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpanestyle"></a><a name="getpanestyle"></a> CMFCStatusBar:: Getbölmesi stili

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *nDizin*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpanetext"></a><a name="getpanetext"></a> CMFCStatusBar:: Getbölmesi metni

```cpp
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *nDizin*<br/>
'ndaki *s*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbargetpanewidth"></a><a name="getpanewidth"></a> CMFCStatusBar:: Getbölmesi genişliği

Durum çubuğunun bölmesinin genişliğini alır.

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Durum çubuğu bölmesinin dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

*NIndex* 'in belirttiği durum çubuğu bölmesinin genişliği; Aksi takdirde, bir durum çubuğu bölmesi yoksa sıfır.

## <a name="cmfcstatusbargettiptext"></a><a name="gettiptext"></a> CMFCStatusBar:: GetTipText

Bir durum çubuğu bölmesinin araç ipucu metnini alın.

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Araç ipucu metnini almak için bölmenin dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

*NIndex* 'in belirttiği durum çubuğu bölmesinin araç ipucu metni. Aksi halde, belirtilen *nIndex* için bir durum çubuğu bölmesi yoksa veya araç ipucu metni boşsa boş dize boş olur.

## <a name="cmfcstatusbarinvalidatepanecontent"></a><a name="invalidatepanecontent"></a> CMFCStatusBar:: ınvalidatebölmesi Içeriği

Durum çubuğu bölmesini geçersiz kılın ve içeriğini yeniden çizin.

```cpp
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki İçeriği geçersiz kılınmış ve yeniden çizilebilir olan bölmenin dizinini belirtir.

### <a name="remarks"></a>Açıklamalar

Durum çubuğu geçersiz kılındığınızda, yeniden çizim için işaretlenir. `UpdateWindow`Yöntemi yöntemine bir WM_PAINT iletisi gönderdiğinde Windows bunu yeniden çizer `OnPaint` .

## <a name="cmfcstatusbarondrawpane"></a><a name="ondrawpane"></a> CMFCStatusBar:: OnDrawPane

Durum çubuğunun bölmesini yeniden çizin.

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Çizim için bir cihaz bağlamı işaretçisi.

*pPane*<br/>
'ndaki Yeniden `CMFCStatusBarPaneInfo` çizilebilir bölme hakkındaki bilgileri içeren bir yapıya yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, Pano `OnDrawPane` stili ve içeriğine göre cihaz bağlamı *PDC* 'sini kullanarak bölmeyi yeniden çizer.

Bir `CMFCStatusBar` bölmenin görünüşünü özelleştirmek için bu yöntemi, türetilmiş bir sınıfta geçersiz kılın.

## <a name="cmfcstatusbarprecreatewindow"></a><a name="precreatewindow"></a> CMFCStatusBar::P reCreateWindow

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Parametreler

'ndaki *CS*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetdrawextendedarea"></a><a name="setdrawextendedarea"></a> CMFCStatusBar:: SetDrawExtendedArea

```cpp
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

'ndaki *bSet*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetindicators"></a><a name="setindicators"></a> CMFCStatusBar:: SetIndicators

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parametreler

'ndaki *lpIDArray*<br/>
'ndaki *nIDCount*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetpaneanimation"></a><a name="setpaneanimation"></a> CMFCStatusBar:: Setbölmesi animasyonu

Belirtilen bölmeye bir animasyon atar.

```cpp
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Bir animasyonuna atamak istediğiniz bölmenin dizinini belirtir.

*hImageList*<br/>
'ndaki Animasyon çerçevelerini tutan görüntü listesi için bir tanıtıcı belirtir.

*Kare içinde*<br/>
'ndaki Animasyon için kare hızını milisaniye olarak belirtir.

*Macrovision*<br/>
'ndaki DOĞRU ise, bölme içeriğini hemen güncelleştirin. Aksi takdirde, bölme içeriği geçersiz kılınmadıkça güncellenir.

### <a name="remarks"></a>Açıklamalar

Geçerli animasyonu devre dışı bırakmak istiyorsanız, öğesini `SetPaneAnimation` `hImageList` null olarak ayarla ' yı çağırın.

## <a name="cmfcstatusbarsetpanebackgroundcolor"></a><a name="setpanebackgroundcolor"></a> CMFCStatusBar:: Setbölmesi BackgroundColor

Durum çubuğu bölmesinin arka plan rengini ayarlar.

```cpp
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Yeni bir arka plan rengi ayarlanacak bölmenin dizinini belirtir.

*clrBackground*<br/>
'ndaki Yeni arka plan rengini belirtir.

*Macrovision*<br/>
'ndaki DOĞRU ise, bölme içeriğini hemen güncelleştirin. Aksi takdirde, bölmesi başka bir yöntem tarafından geçersiz kılınana kadar bölmesi içeriğini güncelleştirmeyin.

## <a name="cmfcstatusbarsetpaneicon"></a><a name="setpaneicon"></a> CMFCStatusBar:: SetPaneIcon

Durum çubuğu bölmesinin simgesini ayarlayın.

```cpp
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

*nDizin*<br/>
'ndaki Görüntünün ayarlanacağı bölmenin dizinini belirtir.

*HICON*<br/>
'ndaki Bölme resmi olarak ayarlanacak simgeye yönelik bir tanıtıcı belirtir.

*Macrovision*<br/>
'ndaki Bölme içeriğinin hemen güncelleştirilmesini isteyip istemediğinizi belirtir.

*hBmp*<br/>
'ndaki Bölme resmi olarak ayarlanacak bit eşlem için bir tanıtıcı belirtir.

*clrTransparent*<br/>
'ndaki *Hbmp* 'nin gösterdiği bit eşlemin saydam rengini belirtir.

### <a name="remarks"></a>Açıklamalar

Bölmenin görüntüsünü ayarlamak için, bir HıCON veya HBITMAP 'i saydam renkle birlikte geçirebilirsiniz. Görüntüyü daha uzun bir süre içinde göstermek istemiyorsanız, NULL değeri görüntü tutamacı olarak geçirin.

[CMFCStatusBar:: Setbölmesi animasyonunun](#setpaneanimation) ayarlandığı herhangi bir çalışan animasyon varsa, animasyon durdurulur.

## <a name="cmfcstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a> CMFCStatusBar:: Setbölmesi bilgileri

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Parametreler

'ndaki *nDizin*<br/>
'ndaki *NID*<br/>
'ndaki *nStyle*<br/>
'ndaki *Cxwidth*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetpaneprogress"></a><a name="setpaneprogress"></a> CMFCStatusBar:: Setbölmesi Ilerlemesi

Belirtilen bölme için ilerleme çubuğunun geçerli ilerleme göstergesini ayarlayın.

```cpp
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki İlerleme göstergesinin güncelleştirilmesi için bölmenin dizinini belirtir.

*NPB*<br/>
'ndaki İlerleme göstergesinin geçerli değerini belirtir.

*Macrovision*<br/>
'ndaki Bölmenin hemen güncelleştirilmesini gerekip gerekmediğini belirtir.

### <a name="remarks"></a>Açıklamalar

Belirtilen bölmedeki ilerleme çubuğunun ilerleme göstergesini güncelleştirmek istediğinizde bu yöntemi çağırın.

Verilen bölme için bu işlevi kullanmak üzere, önce [CMFCStatusBar:: Enablepane ProgressBar](#enablepaneprogressbar) öğesini çağırmanız gerekir.

## <a name="cmfcstatusbarsetpanestyle"></a><a name="setpanestyle"></a> CMFCStatusBar:: Setbölmesi stili

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

'ndaki *nDizin*<br/>
'ndaki *nStyle*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetpanetext"></a><a name="setpanetext"></a> CMFCStatusBar:: Setbölmesi metni

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Parametreler

'ndaki *nDizin*<br/>
'ndaki *lpszNewText*<br/>
'ndaki *bGüncelleştirme*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcstatusbarsetpanetextcolor"></a><a name="setpanetextcolor"></a> CMFCStatusBar:: Setbölmesi TextColor

Belirtilen bölmenin metin rengini ayarlar.

```cpp
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Yeni metin rengi atamak istediğiniz bölmenin dizinini belirtir.

*clrText*<br/>
'ndaki Metin rengini belirtir.

*Macrovision*<br/>
'ndaki DOĞRU ise, bölme içeriğini hemen güncelleştirin. Aksi takdirde, bölmesi başka bir yöntem tarafından geçersiz kılınana kadar bölmesi içeriğini güncelleştirmeyin.

## <a name="cmfcstatusbarsetpanewidth"></a><a name="setpanewidth"></a> CMFCStatusBar:: Setbölmesi genişliği

Durum çubuğu bölmesinin genişliğini ayarlayın.

```cpp
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Yeni bir genişlik ayarlanacak durum çubuğu bölmesinin dizini.

*yazmaç*<br/>
'ndaki Durum çubuğu bölmesinin piksel cinsinden yeni genişliği.

## <a name="cmfcstatusbarsettiptext"></a><a name="settiptext"></a> CMFCStatusBar:: SetTipText

Durum çubuğu bölmesinin araç ipucu metnini ayarlayın.

```cpp
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Araç ipucu metnini atamak istediğiniz bölmenin dizini.

*pszTipText*<br/>
'ndaki Yeni araç ipucu metni.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPane sınıfı](../../mfc/reference/cpane-class.md)<br/>
[CStatusBar sınıfı](../../mfc/reference/cstatusbar-class.md)
