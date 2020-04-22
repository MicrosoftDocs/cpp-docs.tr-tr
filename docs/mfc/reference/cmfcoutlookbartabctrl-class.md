---
title: CMFCOutlookBarTabCtrl Sınıfı
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
ms.openlocfilehash: 9c5d7d5135c3b207bbf113970deb8cbeb186bcca
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749572"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Sınıfı

Microsoft Outlook'ta **Gezinti Bölmesi'nin** görsel görünümüne sahip bir sekme denetimi.
Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Varsayılan oluşturucu.|
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Outlook çubuğuna yeni bir sekme olarak Windows denetimi ekler.|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Bir kullanıcı bir sekmeyi yeniden adlandırdığında görünen düzenleme kutusunun boyutlarını belirlemek için `CMFCBaseTabCtrl::CalcRectEdit`çerçeve tarafından çağrılır. (Geçersiz kılar .)|
|[CMFCOutlookBarTabCtrl::CanShowLessPageButtons](#canshowfewerpagebuttons)|Yeniden boyutlandırma işlemleri sırasında çerçeve tarafından çağrılan outlook çubuğu sekmesi sayfa düğmelerinin şu anda görünenden daha az görüntülenip görüntülenilemeyebileceğini belirlemek için.|
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Yeniden boyutlandırma işlemleri sırasında çerçeve tarafından çağrılan outlook çubuğu sekmesi sayfa düğmelerinin şu anda görünenden daha fazla görüntülenip görüntülenilemeyebileceğini belirlemek için.|
|[CMFCOutlookBarTabCtrl::Oluştur](#create)|Outlook çubuğu sekmesi denetimini oluşturur.|
|`CMFCOutlookBarTabCtrl::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCOutlookBarTabCtrl::Etkinleştirme Animasyonu](#enableanimation)|Etkin sekmeler arasındaki geçiş sırasında oluşan animasyonun etkin olup olmadığını belirtir.|
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Kullanıcının Outlook çubuğunun sekme düğmelerinde metin etiketlerini değiştirip değiştiremeyeceğini belirtir. [(CMFCBaseTabCtrl geçersiz kılar::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|
|[CMFCOutlookBarTabCtrl::Düğmeleri Etkinleştir](#enablescrollbuttons)|Kullanıcının Outlook çubuğu bölmesindeki düğmeler arasında gezinmesini sağlayan düğmeleri etkinleştirmek için çerçeve tarafından çağrılır.|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Belirtilen bir nokta içeren bölmeyi tanımlar. [(CMFCBaseTabCtrl geçersiz kılar::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Outlook sekmesi denetiminin kenarlık boyutunu döndürür.|
|`CMFCOutlookBarTabCtrl::GetTabArea`|Sekme denetiminin sekme alanının boyutunu ve konumunu alır. [(CMFCBaseTabCtrl geçersiz kılar::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|
|`CMFCOutlookBarTabCtrl::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Etkin sekmeler arasındaki geçiş sırasında oluşan animasyonun etkin olup olmadığını belirler.|
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Outlook çubuğu sekmesi denetiminin Microsoft Outlook 2003'ü taklit eden bir modda olup olmadığını belirler.|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Bir noktanın sekme alanıiçinde olup olmadığını belirler. [(CMFCBaseTabCtrl geçersiz kılar::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Sekmenin çıkarılabilir olup olmadığını belirler. [(CMFCBaseTabCtrl geçersiz kılar::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Sekme eklendiğinde veya kaldırıldığında çerçeve tarafından çağrılır. (Geçersiz `CMFCBaseTabCtrl::OnChangeTabs`kılar .)|
|[CMFCOutlookBarTabCtrl::OnShowLessPageButtons](#onshowfewerpagebuttons)|Görünür sekme sayfası düğmelerinin sayısını azaltmak için çerçeve tarafından çağrılır.|
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Görünür sekme sayfası düğmelerinin sayısını artırmak için çerçeve tarafından çağrılır.|
|[CMFCOutlookBarTabCtrl::AçıkGösterim Seçenekleri](#onshowoptions)|Gezinti **Bölmesi Seçenekleri** iletişim kutusunu görüntüler.|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Sekme denetiminin iç düzenini yeniden hesaplar. [(CMFCBaseTabCtrl geçersiz kılar::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Etkin sekmeyi ayarlar. [(CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Outlook sekmesi denetiminin kenarlık boyutunu ayarlar.|
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Outlook çubuğunun sekme düğmelerinde metin etiketlerinin hizalanmasını ayarlar.|
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Outlook 2003 modunda Outlook çubuğunun alt kısmında görüntülenen simgeleri içeren bit eşlemi ayarlar (bkz. [CMFCOutlookBar Sınıfı).](../../mfc/reference/cmfcoutlookbar-class.md)|
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||

## <a name="remarks"></a>Açıklamalar

Yerleştirme desteği olan bir Outlook çubuğu oluşturmak `CMFCOutlookBar` için, Outlook çubuğu denetimine ev sahipliği yapmak için bir nesne kullanın. Daha fazla bilgi için [CMFCOutlookBar Sınıfı'na](../../mfc/reference/cmfcoutlookbar-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCOutlookBarTabCtrl` nesnenin nasıl başharfe atınır ve sınıfta çeşitli yöntemlerin nasıl kullanılacağını `CMFCOutlookBarTabCtrl` gösterir. Örnek, Outlook çubuğunun sekme sayfası düğmelerinde metin etiketinin yerinde düzenlemesini, animasyonu etkinleştirmeyi, kullanıcının Outlook çubuğu bölmesindeki düğmeler arasında gezinmesini sağlayan kaydırma tutamaçlarını etkinleştirmeyi, Outlook sekmesi denetiminin kenarlık boyutunu nasıl ayarlayacaklarını ve Outlook çubuğunun sekme düğmelerinde metin etiketlerinin hizalanmasını nasıl ayarlayacaklarını gösterir. Bu kod parçacığı Outlook Demo [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cmfcbasetabctrl](../../mfc/reference/cmfcbasetabctrl-class.md)

[Cmfcoutlookbartabctrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxoutlookbartabctrl.h

## <a name="cmfcoutlookbartabctrladdcontrol"></a><a name="addcontrol"></a>CMFCOutlookBarTabCtrl::AddControl

Outlook çubuğuna yeni bir sekme olarak Windows denetimi ekler.

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
[içinde] Eklemek için bir denetim için bir işaretçi.

*Lpszname*<br/>
[içinde] Sekme adını belirtir.

*bDetachable*<br/>
[içinde] TRUE ise, sayfa çıkarılabilir olarak oluşturulur.

*nImageID*<br/>
[içinde] Yeni sekmede görüntülenecek iç resim listesindeki görüntü dizini.

*dwControlBarStyle*<br/>
[içinde] Sarılmış yerleştirme bölmeleri için AFX_ CBRS_* stilini belirtir.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğunun yeni sayfası olarak denetim eklemek için bu işlevi kullanın.

Bu işlev [cmfcBaseTabCtrl'ı](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)dahili olarak çağırır::AddTab .

*bDetachable'ı* TRUE olarak `AddControl` ayarlarsanız, `CDockablePaneAdapter` dahili olarak bir nesne oluşturur ve eklenen denetimi sarar. Sekmeli pencerenin çalışma zamanı sınıfını otomatik olarak çalışma `CMFCOutlookBar` zamanı sınıfına ve kayan çerçevenin çalışma zamanı sınıfına `CMultiPaneFrameWnd`ayarlar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıfta `AddControl` nasıl `CMFCOutlookBarTabCtrl` kullanılacağını göstermektedir. Bu kod parçacığı Outlook Demo [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

## <a name="cmfcoutlookbartabctrlcanshowfewerpagebuttons"></a><a name="canshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowLessPageButtons

Yeniden boyutlandırma işlemleri sırasında çerçeve tarafından çağrılan outlook çubuğu sekmesi sayfa düğmelerinin şu anda görünenden daha az görüntülenip görüntülenemeyeceğini belirlemek için.

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birden fazla düğme varsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğu denetimi denetimi, kullanılabilir oda sayısına bağlı olarak sekmeleri ekrandan dinamik olarak ekler veya kaldırır. Bu yöntem, bu süreçte yardımcı olmak için çerçeve tarafından kullanılır.

## <a name="cmfcoutlookbartabctrlcanshowmorepagebuttons"></a><a name="canshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowMorePageButtons

Yeniden boyutlandırma işlemleri sırasında çerçeve tarafından çağrılan outlook çubuğu sekmesi sayfa düğmelerinin şu anda görünenden daha fazla görüntülenip görüntülenemeyeceğini belirlemek için.

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda görünmeyen düğmeler varsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğu denetimi denetimi, kullanılabilir alana bağlı olarak sekmeleri ekrandan dinamik olarak ekler veya kaldırır. Bu yöntem, bu süreçte yardımcı olmak için çerçeve tarafından kullanılır.

## <a name="cmfcoutlookbartabctrlcreate"></a><a name="create"></a>CMFCOutlookBarTabCtrl::Oluştur

Outlook çubuğu sekmesi denetimini oluşturur.

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[içinde] İlk boyutu ve konumu pikselolarak belirtir.

*pParentWnd*<br/>
[içinde] Üst pencereyi işaret ediyor. NULL olmamalıdır.

*Nıd*<br/>
[içinde] Kontrol kimliği.

### <a name="return-value"></a>Dönüş Değeri

Denetim başarıyla oluşturulduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genellikle [CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md) işlemin WM_CREATE iletisini denetlediğinde outlook çubuğu sekmesi denetimleri oluşturulur.

## <a name="cmfcoutlookbartabctrlenableanimation"></a><a name="enableanimation"></a>CMFCOutlookBarTabCtrl::Etkinleştirme Animasyonu

Etkin sekmeler arasındaki geçiş sırasında oluşan animasyonun etkin olup olmadığını belirtir.

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Animasyonun etkin mi yoksa devre dışı mı olması gerektiğini belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyonu etkinleştirmek ve devre dışı kalmak için bu işlevi çağırın. Kullanıcı bir sekme sayfası açtığında, animasyon etkinse sayfanın altyazı aşağı veya yukarı kaydırılır. Animasyon devre dışı bırakılırsa, sayfa hemen etkin hale gelir.

Varsayılan olarak, animasyon etkinleştirilir.

## <a name="cmfcoutlookbartabctrlenableinplaceedit"></a><a name="enableinplaceedit"></a>CMFCOutlookBarTabCtrl::EnableInPlaceEdit

Kullanıcının Outlook çubuğunun sekme sayfası düğmelerinde metin etiketlerini değiştirip değiştiremeyeceğini belirtir.

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
TRUE ise, metin etiketinin yerinde düzenlemesini etkinleştirin. YANLIŞ ise, yerinde düzenlemeyi devre dışı bırakın.

### <a name="remarks"></a>Açıklamalar

Sekme sayfası düğmelerinde metin etiketlerinin yerinde düzenlemesini etkinleştirmek veya devre dışı kalmak için bu işlevi arayın. Varsayılan olarak yerinde düzenleme devre dışı bırakılır.

## <a name="cmfcoutlookbartabctrlenablescrollbuttons"></a><a name="enablescrollbuttons"></a>CMFCOutlookBarTabCtrl::Düğmeleri Etkinleştir

Kullanıcının Outlook çubuğu bölmesindeki düğmeler arasında gezinmesini sağlayan kaydırma tutamaçlarını etkinleştirmek için çerçeve tarafından çağrılır.

```cpp
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Kaydırma düğmelerinin görüntülenip görüntülenmediğini belirler.

*bIsUp*<br/>
[içinde] Üst kaydırma çubuğunun görüntülenip görüntülenmediğini belirler.

*bIsDown*<br/>
[içinde] Alt kaydırma çubuğunun görüntülenip görüntülenmediğini belirler.

### <a name="remarks"></a>Açıklamalar

Kaydırma düğmelerinin görüntülenmesini sağlar. Kaydırma düğmelerini geri yüklemek için etkin sekme değiştiğinde, bu yöntem çerçeve tarafından çağrılır.

## <a name="cmfcoutlookbartabctrlgetbordersize"></a><a name="getbordersize"></a>CMFCOutlookBarTabCtrl::GetBorderSize

Outlook sekmesi denetiminin kenarlık boyutunu döndürür.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kenarlık boyutu, piksel olarak.

## <a name="cmfcoutlookbartabctrlgetvisiblepagebuttons"></a><a name="getvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::GetVisiblePageButtons

```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcoutlookbartabctrlisanimation"></a><a name="isanimation"></a>CMFCOutlookBarTabCtrl::IsAnimation

Etkin sekmeler arasındaki geçiş sırasında oluşan animasyonun etkin olup olmadığını belirtir.

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon etkinse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Animasyonu etkinleştirmek veya devre dışı kakmak için [CMFCOutlookBarTabCtrl::Animasyonu Etkinleştir](#enableanimation) işlevini çağırın.

## <a name="cmfcoutlookbartabctrlismode2003"></a><a name="ismode2003"></a>CMFCOutlookBarTabCtrl::IsMode2003

Outlook çubuğu sekmesi denetiminin Microsoft Outlook 2003'ü taklit eden bir modda olup olmadığını belirler.

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook çubuğu sekmesi denetimi Outlook 2003 modundaysa TRUE; aksi takdirde YANLIŞ;

### <a name="remarks"></a>Açıklamalar

Bu değer [CMFCOutlookBar tarafından ayarlanır::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).

## <a name="cmfcoutlookbartabctrlonshowfewerpagebuttons"></a><a name="onshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowLessPageButtons

Görünür sekme sayfası düğmelerinin sayısını azaltmak için çerçeve tarafından çağrılır.

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetim yeniden boyutlandırıldığında görünür sayfa sekmesi düğmelerinin sayısını ayarlar.

## <a name="cmfcoutlookbartabctrlonshowmorepagebuttons"></a><a name="onshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowMorePageButtons

Görünür sekme sayfası düğmelerinin sayısını artırmak için çerçeve tarafından çağrılır.

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, denetim yeniden boyutlandırıldığında görünen sekme sayfası düğmelerinin sayısını ayarlayın.

## <a name="cmfcoutlookbartabctrlonshowoptions"></a><a name="onshowoptions"></a>CMFCOutlookBarTabCtrl::AçıkGösterim Seçenekleri

Gezinti **Bölmesi Seçenekleri** iletişim kutusunu görüntüler.

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>Açıklamalar

**Gezinti Bölmesi Seçenekleri** iletişim kutusu, kullanıcının hangi sekme sayfası düğmelerinin görüntüleneceğini ve bunların görüntülenme sırasını seçmesine olanak tanır.

Bu yöntem, kullanıcı denetimin özelleştirme menüsünden **Gezinti Bölmesi Seçenekleri** menü öğesini seçtiğinde çerçeve tarafından çağrılır.

## <a name="cmfcoutlookbartabctrlsetactivetab"></a><a name="setactivetab"></a>CMFCOutlookBarTabCtrl::SetActiveTab

Etkin sekmeyi ayarlar. Etkin sekme, içeriği görünür olan açık sekmedir.

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>Parametreler

*ıtab*<br/>
[içinde] Açılacak bir sekmenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sekme başarıyla açılmışsa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Etkin sekmeyi ayarlamanın görsel etkisi animasyonu etkinleştirip etkinleştirmediğinize bağlıdır. Daha fazla bilgi için [cmfcOutlookBarTabCtrl::EnableAnimation'a](#enableanimation)bakın.

## <a name="cmfcoutlookbartabctrlsetbordersize"></a><a name="setbordersize"></a>CMFCOutlookBarTabCtrl::SetBorderSize

Outlook sekmesi denetiminin kenarlık boyutunu ayarlar.

```cpp
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>Parametreler

*nBorderSize*<br/>
[içinde] Yeni kenarlık boyutunu pikselolarak belirtir.

### <a name="remarks"></a>Açıklamalar

Yeni kenarlık boyutunu ayarlar ve görünüm penceresi düzenini yeniden hesaplar.

## <a name="cmfcoutlookbartabctrlsetpagebuttontextalign"></a><a name="setpagebuttontextalign"></a>CMFCOutlookBarTabCtrl::SetPageButtonTextAlign

Outlook çubuğunun sekme düğmelerinde metin etiketlerinin hizalanmasını ayarlar.

```cpp
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*uiAlign*<br/>
[içinde] Metin hizalamasını belirtir.

*bRedraw*<br/>
[içinde] TRUE ise, görünüm penceresi yeniden çizilir.

### <a name="remarks"></a>Açıklamalar

Sayfa düğmeleri için metin hizalamasını değiştirmek için bu işlevi kullanın.

*uiAlign* aşağıdaki değerlerden biri olabilir:

|Sabit|Anlamı|
|--------------|-------------|
|TA_LEFT|Sol hizalama|
|TA_CENTER|Orta hizalama|
|TA_RIGHT|Doğru hizalama|

Varsayılan değer TA_CENTER.

## <a name="cmfcoutlookbartabctrlsettoolbarimagelist"></a><a name="settoolbarimagelist"></a>CMFCOutlookBarTabCtrl::SetToolbarImageList

Outlook 2003 modunda Outlook çubuğunun alt kısmında görüntülenen simgeleri içeren bit eşlemi ayarlar.

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[içinde] Yüklenmesi için görüntünün kaynak kimliğini belirtir.

*Cx*<br/>
[içinde] Görüntü listesindeki görüntünün genişliğini piksel olarak belirtir.

*clrTransp*<br/>
[içinde] Saydam rengi belirten bir RGB değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE döndürür; aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Resimleri Microsoft Office 2003 modunda araç çubuğu düğmelerinde görüntülenecek bir resim listesi eklemek için bu işlevi kullanın. Görüntü dizinleri sayfa dizinlerine karşılık vermelidir.

Microsoft Office 2003 modunda değilse, bu yöntem çağrılmamalıdır. Daha fazla bilgi için [CMFCOutlookBar Sınıfı'na](../../mfc/reference/cmfcoutlookbar-class.md)bakın.

## <a name="cmfcoutlookbartabctrlsetvisiblepagebuttons"></a><a name="setvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::SetVisiblePageButtons

```cpp
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>Parametreler

[içinde] *nVisiblePageButtons*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCBaseTabCtrl Sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarPane Sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md)
