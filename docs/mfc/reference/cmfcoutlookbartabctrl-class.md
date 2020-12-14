---
description: 'Daha fazla bilgi edinin: CMFCOutlookBarTabCtrl sınıfı'
title: CMFCOutlookBarTabCtrl sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
helpviewer_keywords:
- CMFCOutlookBarTabCtrl [MFC], AddControl
- CMFCOutlookBarTabCtrl [MFC], CanShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], CanShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], Create
- CMFCOutlookBarTabCtrl [MFC], EnableAnimation
- CMFCOutlookBarTabCtrl [MFC], EnableInPlaceEdit
- CMFCOutlookBarTabCtrl [MFC], EnableScrollButtons
- CMFCOutlookBarTabCtrl [MFC], GetBorderSize
- CMFCOutlookBarTabCtrl [MFC], GetVisiblePageButtons
- CMFCOutlookBarTabCtrl [MFC], IsAnimation
- CMFCOutlookBarTabCtrl [MFC], IsMode2003
- CMFCOutlookBarTabCtrl [MFC], OnShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowOptions
- CMFCOutlookBarTabCtrl [MFC], SetActiveTab
- CMFCOutlookBarTabCtrl [MFC], SetBorderSize
- CMFCOutlookBarTabCtrl [MFC], SetPageButtonTextAlign
- CMFCOutlookBarTabCtrl [MFC], SetToolbarImageList
- CMFCOutlookBarTabCtrl [MFC], SetVisiblePageButtons
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
ms.openlocfilehash: b969fbb592fc3098dc8d287004fab90da6f30111
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333499"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl sınıfı

Microsoft Outlook 'taki **Gezinti bölmesinin** görsel görünümüne sahip bir sekme denetimi.
Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Varsayılan Oluşturucu.|
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCOutlookBarTabCtrl:: AddControl](#addcontrol)|Outlook çubuğuna yeni sekme olarak bir Windows denetimi ekler.|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Kullanıcı bir sekmeyi yeniden adlandırdığında görüntülenen düzenleme kutusunun boyutlarını öğrenmek için Framework tarafından çağırılır. (geçersiz kılmalar `CMFCBaseTabCtrl::CalcRectEdit` .)|
|[CMFCOutlookBarTabCtrl:: CanShowFewerPageButtons](#canshowfewerpagebuttons)|Şu anda görünenden daha az Outlook çubuğu sekme sayfası düğmesinin görüntülenip görüntülenmediğini belirleme işlemleri sırasında Framework tarafından çağırılır.|
|[CMFCOutlookBarTabCtrl:: CanShowMorePageButtons](#canshowmorepagebuttons)|Daha fazla Outlook çubuğu sekme sayfası düğmesinin görünür olup olmadığını belirleme işlemleri sırasında Framework tarafından çağırılır.|
|[CMFCOutlookBarTabCtrl:: Create](#create)|Outlook çubuğu sekme denetimi oluşturur.|
|`CMFCOutlookBarTabCtrl::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCOutlookBarTabCtrl:: EnableAnimation](#enableanimation)|Etkin sekmeler arasındaki anahtar sırasında gerçekleşen Animasyonun etkinleştirilip etkinleştirilmeyeceğini belirtir.|
|[CMFCOutlookBarTabCtrl:: EnableInPlaceEdit](#enableinplaceedit)|Kullanıcının Outlook çubuğunun sekme düğmelerindeki metin etiketlerini değiştirip değiştiremeyeceğini belirtir. ( [CMFCBaseTabCtrl:: EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit)geçersiz kılar.)|
|[CMFCOutlookBarTabCtrl:: EnableScrollButtons](#enablescrollbuttons)|Kullanıcının Outlook çubuğu bölmesindeki düğmelere kaydırılmasına izin veren düğmeleri etkinleştirmek için Framework tarafından çağırılır.|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Belirtilen noktayı içeren bölmeyi tanımlar. ( [CMFCBaseTabCtrl:: FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd)' i geçersiz kılar)|
|[CMFCOutlookBarTabCtrl:: GetBorderSize](#getbordersize)|Outlook sekme denetiminin kenarlık boyutunu döndürür.|
|`CMFCOutlookBarTabCtrl::GetTabArea`|Sekme denetiminin sekme alanının boyutunu ve konumunu alır. ( [CMFCBaseTabCtrl:: GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea)geçersiz kılar.)|
|`CMFCOutlookBarTabCtrl::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCOutlookBarTabCtrl:: GetVisiblePageButtons](#getvisiblepagebuttons)||
|[CMFCOutlookBarTabCtrl:: ısanimation](#isanimation)|Etkin sekmeler arasındaki anahtar sırasında gerçekleşen animasyonun etkin olup olmadığını belirler.|
|[CMFCOutlookBarTabCtrl:: IsMode2003](#ismode2003)|Outlook çubuğu sekme denetiminin Microsoft Outlook 2003 'e öykünen bir modda olup olmadığını belirler.|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Bir noktanın sekme alanının içinde olup olmadığını belirler. ( [CMFCBaseTabCtrl:: ısptintabarea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea)geçersiz kılar.)|
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Bir sekmenin çıkarılabilir olup olmadığını belirler. ( [CMFCBaseTabCtrl:: ıstabıable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable)geçersiz kılar.)|
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Bir sekme eklendiğinde veya kaldırıldığında Framework tarafından çağırılır. (Geçersiz kılmalar `CMFCBaseTabCtrl::OnChangeTabs` .)|
|[CMFCOutlookBarTabCtrl:: OnShowFewerPageButtons](#onshowfewerpagebuttons)|Görünür olan sekme sayfası düğmelerinin sayısını azaltmak için Framework tarafından çağırılır.|
|[CMFCOutlookBarTabCtrl:: OnShowMorePageButtons](#onshowmorepagebuttons)|Görünür olan sekme sayfası düğmelerinin sayısını artırmak için Framework tarafından çağırılır.|
|[CMFCOutlookBarTabCtrl:: OnShowOptions](#onshowoptions)|**Gezinti bölmesi seçenekleri** iletişim kutusunu görüntüler.|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Sekme denetiminin iç yerleşimini yeniden hesaplar. ( [CMFCBaseTabCtrl:: RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|
|[CMFCOutlookBarTabCtrl:: SetActiveTab](#setactivetab)|Etkin sekmesini ayarlar. ( [CMFCBaseTabCtrl:: SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab)' i geçersiz kılar.)|
|[CMFCOutlookBarTabCtrl:: SetBorderSize](#setbordersize)|Outlook sekme denetiminin kenarlık boyutunu ayarlar.|
|[CMFCOutlookBarTabCtrl:: SetPageButtonTextAlign](#setpagebuttontextalign)|Outlook çubuğunun sekme düğmelerindeki metin etiketlerinin hizalamasını ayarlar.|
|[CMFCOutlookBarTabCtrl:: SetToolbarImageList](#settoolbarimagelist)|Outlook 2003 modunda Outlook çubuğunun altında görüntülenen simgeleri içeren bit eşlemi ayarlar (bkz. [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)).|
|[CMFCOutlookBarTabCtrl:: SetVisiblePageButtons](#setvisiblepagebuttons)||

## <a name="remarks"></a>Açıklamalar

Yerleştirme desteği olan bir Outlook çubuğu oluşturmak için, `CMFCOutlookBar` Outlook çubuğu sekme denetimini barındırmak üzere bir nesnesi kullanın. Daha fazla bilgi için bkz. [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnenin nasıl başlatılacağını `CMFCOutlookBarTabCtrl` ve sınıfında çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCOutlookBarTabCtrl` . Örnekte, Outlook çubuğunun sekme sayfası düğmelerinde metin etiketinin yerinde düzenlenmesinin nasıl etkinleştirileceği gösterilmektedir, animasyonu etkinleştirir, kullanıcının Outlook çubuğu bölmesindeki düğmelere kaymasını sağlayan kaydırma tutamaçlarını etkinleştirir, Outlook sekme denetiminin kenarlık boyutunu ayarlar ve Outlook çubuğunun sekme düğmelerindeki metin etiketlerinin hizalamasını ayarlar. Bu kod parçacığı, [Outlook demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)

[CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxoutlookbartabctrl. h

## <a name="cmfcoutlookbartabctrladdcontrol"></a><a name="addcontrol"></a> CMFCOutlookBarTabCtrl:: AddControl

Outlook çubuğuna yeni sekme olarak bir Windows denetimi ekler.

```cpp
void AddControl(
    CWnd* pWndCtrl,
    LPCTSTR lpszName,
    int nImageID=-1,
    BOOL bDetachable=TRUE,
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```

### <a name="parameters"></a>Parametreler

*pWndCtrl*<br/>
'ndaki Eklenecek denetime yönelik bir işaretçi.

*lpszName*<br/>
'ndaki Sekmenin adını belirtir.

*Ayrılabilir*<br/>
'ndaki DOĞRU ise, sayfa çıkarılabilir olarak oluşturulur.

*nImageID*<br/>
'ndaki Yeni sekmede görüntülenecek görüntünün iç görüntü listesinde görüntü dizini.

*dwControlBarStyle*<br/>
'ndaki Kaydırılan yerleştirme bölmeleri için AFX_ CBRS_ * stilini belirtir.

### <a name="remarks"></a>Açıklamalar

Bir Outlook çubuğunun yeni sayfası olarak bir denetim eklemek için bu işlevi kullanın.

Bu işlev [CMFCBaseTabCtrl:: AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)üzerine dahili olarak çağrı.

*Bayrılabilir* değerini doğru olarak ayarlarsanız, `AddControl` dahili olarak bir nesne oluşturur `CDockablePaneAdapter` ve eklenen denetimi sarmalanmış olarak kaydırır. Sekmeli pencerenin çalışma zamanı sınıfını, ' ın çalışma zamanı sınıfına `CMFCOutlookBar` ve kayan çerçevenin çalışma zamanı sınıfına otomatik olarak ayarlar `CMultiPaneFrameWnd` .

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında yönteminin nasıl kullanılacağını gösterir `AddControl` `CMFCOutlookBarTabCtrl` . Bu kod parçacığı, [Outlook demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

## <a name="cmfcoutlookbartabctrlcanshowfewerpagebuttons"></a><a name="canshowfewerpagebuttons"></a> CMFCOutlookBarTabCtrl:: CanShowFewerPageButtons

Şu anda görünenden daha az Outlook çubuğu sekme sayfası düğmesinin görüntülenip görüntülenmeyeceğini belirleme işlemleri sırasında Framework tarafından çağırılır.

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birden çok düğme varsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğu sekme denetimi, kullanılabilir odanın ne kadar yer olduğuna bağlı olarak, ekranda dinamik olarak sekme ekler veya kaldırır. Bu yöntem, Framework tarafından bu işleme yardımcı olmak için kullanılır.

## <a name="cmfcoutlookbartabctrlcanshowmorepagebuttons"></a><a name="canshowmorepagebuttons"></a> CMFCOutlookBarTabCtrl:: CanShowMorePageButtons

Şu anda görünür olandan daha fazla Outlook çubuğu sekme sayfası düğmesi görüntülenip görüntülenmeyeceğini belirleme işlemleri sırasında Framework tarafından çağırılır.

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda görünür olmayan düğmeler varsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğu sekme denetimi, kullanılabilir odanın miktarına bağlı olarak, ekranda dinamik olarak sekme ekler veya kaldırır. Bu yöntem, Framework tarafından bu işleme yardımcı olmak için kullanılır.

## <a name="cmfcoutlookbartabctrlcreate"></a><a name="create"></a> CMFCOutlookBarTabCtrl:: Create

Outlook çubuğu sekme denetimi oluşturur.

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
'ndaki Başlangıç boyutunu ve konumunu piksel cinsinden belirtir.

*pParentWnd*<br/>
'ndaki Üst pencereyi işaret eder. NULL olmamalıdır.

*NID*<br/>
'ndaki Denetim KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Denetim başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genellikle, [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md) işlemin WM_CREATE iletisini denetliyorsa, Outlook çubuğu sekme denetimleri oluşturulur.

## <a name="cmfcoutlookbartabctrlenableanimation"></a><a name="enableanimation"></a> CMFCOutlookBarTabCtrl:: EnableAnimation

Etkin sekmeler arasındaki anahtar sırasında gerçekleşen Animasyonun etkinleştirilip etkinleştirilmeyeceğini belirtir.

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Animasyonun etkin mi yoksa devre dışı mı olacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyonu etkinleştirmek ve devre dışı bırakmak için bu işlevi çağırın. Kullanıcı bir sekme sayfası açtığında, animasyon etkinse sayfanın başlık metni yukarı veya aşağı görüntülenir. Animasyon devre dışıysa, sayfa hemen etkin hale gelir.

Varsayılan olarak, animasyon etkindir.

## <a name="cmfcoutlookbartabctrlenableinplaceedit"></a><a name="enableinplaceedit"></a> CMFCOutlookBarTabCtrl:: EnableInPlaceEdit

Kullanıcının Outlook çubuğunun sekme sayfası düğmelerindeki metin etiketlerini değiştirip değiştiremeyeceğini belirtir.

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
DOĞRU ise, metin etiketini yerinde düzenlemenizi etkinleştirin. YANLıŞSA, yerinde düzenlemenizi devre dışı bırakın.

### <a name="remarks"></a>Açıklamalar

Sekme sayfası düğmelerinde metin etiketlerinin yerinde düzenlemesini etkinleştirmek veya devre dışı bırakmak için bu işlevi çağırın. Varsayılan olarak, yerinde Düzenle devre dışıdır.

## <a name="cmfcoutlookbartabctrlenablescrollbuttons"></a><a name="enablescrollbuttons"></a> CMFCOutlookBarTabCtrl:: EnableScrollButtons

Kullanıcının Outlook çubuğu bölmesindeki düğmelere kaydırılmasına izin veren kaydırma tutamaçlarını etkinleştirmek için Framework tarafından çağırılır.

```cpp
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Kaydırma düğmelerinin görüntülenip görüntülenmeyeceğini belirler.

*bIsUp*<br/>
'ndaki Üstteki ScrollBar 'ın görüntülenip görüntülenmeyeceğini belirler.

*Bisaşağı*<br/>
'ndaki Alt ScrollBar 'ın görüntülenip görüntülenmeyeceğini belirler.

### <a name="remarks"></a>Açıklamalar

Kaydırma düğmelerinin görüntülenmesini etkinleştirilir. Bu yöntem, kaydırma düğmelerini geri yüklemek için etkin sekme değiştiğinde Framework tarafından çağırılır.

## <a name="cmfcoutlookbartabctrlgetbordersize"></a><a name="getbordersize"></a> CMFCOutlookBarTabCtrl:: GetBorderSize

Outlook sekme denetiminin kenarlık boyutunu döndürür.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kenarlık boyutu (piksel cinsinden).

## <a name="cmfcoutlookbartabctrlgetvisiblepagebuttons"></a><a name="getvisiblepagebuttons"></a> CMFCOutlookBarTabCtrl:: GetVisiblePageButtons

```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcoutlookbartabctrlisanimation"></a><a name="isanimation"></a> CMFCOutlookBarTabCtrl:: ısanimation

Etkin sekmeler arasındaki anahtar sırasında gerçekleşen Animasyonun etkinleştirilip etkinleştirilmeyeceğini belirtir.

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon etkinse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Animasyonu etkinleştirmek veya devre dışı bırakmak için [CMFCOutlookBarTabCtrl:: EnableAnimation](#enableanimation) işlevini çağırın.

## <a name="cmfcoutlookbartabctrlismode2003"></a><a name="ismode2003"></a> CMFCOutlookBarTabCtrl:: IsMode2003

Outlook çubuğu sekme denetiminin Microsoft Outlook 2003 'e öykünen bir modda olup olmayacağını belirler.

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook çubuğu sekme denetimi Outlook 2003 modundaysa doğru; Aksi takdirde yanlış;

### <a name="remarks"></a>Açıklamalar

Bu değer [CMFCOutlookBar:: SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003)tarafından ayarlanır.

## <a name="cmfcoutlookbartabctrlonshowfewerpagebuttons"></a><a name="onshowfewerpagebuttons"></a> CMFCOutlookBarTabCtrl:: OnShowFewerPageButtons

Görünür olan sekme sayfası düğmelerinin sayısını azaltmak için Framework tarafından çağırılır.

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetim yeniden boyutlandırılırken görünür sayfa sekmesi düğmelerinin sayısını ayarlar.

## <a name="cmfcoutlookbartabctrlonshowmorepagebuttons"></a><a name="onshowmorepagebuttons"></a> CMFCOutlookBarTabCtrl:: OnShowMorePageButtons

Görünür olan sekme sayfası düğmelerinin sayısını artırmak için Framework tarafından çağırılır.

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetim yeniden boyutlandırılırken görünür olan sekme sayfası düğmelerinin sayısını ayarlar.

## <a name="cmfcoutlookbartabctrlonshowoptions"></a><a name="onshowoptions"></a> CMFCOutlookBarTabCtrl:: OnShowOptions

**Gezinti bölmesi seçenekleri** iletişim kutusunu görüntüler.

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>Açıklamalar

**Gezinti bölmesi seçenekleri** iletişim kutusu, kullanıcının hangi sekme sayfası düğmelerinin gösterileceğini ve görüntülenme sırasını seçmesine olanak sağlar.

Bu yöntem, Kullanıcı denetimin özelleştirme menüsünden **Gezinti bölmesi seçenekleri** menü öğesini seçtiğinde Framework tarafından çağrılır.

## <a name="cmfcoutlookbartabctrlsetactivetab"></a><a name="setactivetab"></a> CMFCOutlookBarTabCtrl:: SetActiveTab

Etkin sekmesini ayarlar. Etkin sekmesi, içeriği görünür olan açık olan bir sekmedir.

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>Parametreler

*ITAB*<br/>
'ndaki Açılacak sekmenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sekme başarıyla açıldıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Etkin sekmeyi ayarlamanın görsel etkisi, animasyonu etkinleştirdiğinize bağlıdır. Daha fazla bilgi için bkz. [CMFCOutlookBarTabCtrl:: EnableAnimation](#enableanimation).

## <a name="cmfcoutlookbartabctrlsetbordersize"></a><a name="setbordersize"></a> CMFCOutlookBarTabCtrl:: SetBorderSize

Outlook sekme denetiminin kenarlık boyutunu ayarlar.

```cpp
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>Parametreler

*nBorderSize*<br/>
'ndaki Yeni kenarlık boyutunu piksel cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

Yeni kenarlık boyutunu ayarlar ve Outlook pencere yerleşimini yeniden hesaplar.

## <a name="cmfcoutlookbartabctrlsetpagebuttontextalign"></a><a name="setpagebuttontextalign"></a> CMFCOutlookBarTabCtrl:: SetPageButtonTextAlign

Outlook çubuğunun sekme düğmelerindeki metin etiketlerinin hizalamasını ayarlar.

```cpp
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*Uıalign*<br/>
'ndaki Metin hizalamasını belirtir.

*bRedraw*<br/>
'ndaki TRUE ise Outlook penceresi yeniden çizilir.

### <a name="remarks"></a>Açıklamalar

Sayfa düğmelerinin metin hizalamasını değiştirmek için bu işlevi kullanın.

*Uıalign* aşağıdaki değerlerden biri olabilir:

|Sabit|Anlamı|
|--------------|-------------|
|TA_LEFT|Sola hizalama|
|TA_CENTER|Ortaya Hizala|
|TA_RIGHT|Sağa hizalama|

Varsayılan değer TA_CENTER.

## <a name="cmfcoutlookbartabctrlsettoolbarimagelist"></a><a name="settoolbarimagelist"></a> CMFCOutlookBarTabCtrl:: SetToolbarImageList

Outlook 2003 modunda Outlook çubuğunun altında görüntülenen simgeleri içeren bit eşlemi ayarlar.

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
'ndaki Yüklenecek görüntünün kaynak KIMLIĞINI belirtir.

*yazmaç*<br/>
'ndaki Görüntü listesindeki görüntünün genişliğini piksel cinsinden belirtir.

*clrTransp*<br/>
'ndaki Saydam rengi belirten bir RGB değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE döndürür; Aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Görüntüleri Microsoft Office 2003 modundaki araç çubuğu düğmelerinde görüntülenecek bir resim listesi eklemek için bu işlevi kullanın. Görüntü dizinleri sayfa dizinlerine karşılık gelmelidir.

Bu yöntem Microsoft Office 2003 modunda değilse çağrılmamalıdır. Daha fazla bilgi için bkz. [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

## <a name="cmfcoutlookbartabctrlsetvisiblepagebuttons"></a><a name="setvisiblepagebuttons"></a> CMFCOutlookBarTabCtrl:: SetVisiblePageButtons

```cpp
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>Parametreler

'ndaki *Nvisiblepagebuttons*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md)
