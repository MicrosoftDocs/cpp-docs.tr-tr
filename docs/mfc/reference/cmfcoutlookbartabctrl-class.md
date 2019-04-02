---
title: CMFCOutlookBarTabCtrl Class
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
ms.openlocfilehash: c791f3988c7257ed7d188917394e74a6dbeca98b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776810"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class

Öğesinin görsel görünümüne sahip sekme denetimi **Gezinti bölmesinde** Microsoft Outlook.
Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.
## <a name="syntax"></a>Sözdizimi

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
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Yeni bir sekmede Outlook çubuğu olarak bir Windows denetimini ekler.|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Framework tarafından çağırılır kullanıcı görüntülendiğinde düzenleme kutusunun boyutları belirlemek için bir sekme yeniden adlandırır. (Geçersiz kılmaları `CMFCBaseTabCtrl::CalcRectEdit`.)|
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Yeniden boyutlandırma işlemleri sırasında görüntülenmekte olan daha az Outlook Çubuğu sekmesinde sayfa düğmelerini görüntülenebilen belirlemek için framework tarafından çağırılır.|
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Yeniden boyutlandırma işlemleri sırasında daha fazla Outlook Çubuğu sekmesinde sayfa düğmelerini görüntülenebilir, görüntülenmekte olan daha belirlemek için framework tarafından çağırılır.|
|[CMFCOutlookBarTabCtrl::Create](#create)|Outlook Çubuğu sekme denetimi oluşturur.|
|`CMFCOutlookBarTabCtrl::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Etkin sekmeler arasında geçiş sırasında gerçekleşen animasyonu etkinleştirilip etkinleştirilmeyeceğini belirtir.|
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Bir kullanıcıya Outlook Çubuğu sekme düğmelerinin metin etiketlerini değiştirip değiştiremeyeceğini belirtir. (Geçersiz kılmaları [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Outlook Çubuğu bölmesi düğmelerini kaydırmak kullanıcının olanak tanıyan düğmelerini etkinleştirmek için framework tarafından çağırılır.|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Belirli bir noktaya içeren bölme tanımlar. (Geçersiz kılmaları [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Outlook sekme denetiminin kenarlık boyutunu döndürür.|
|`CMFCOutlookBarTabCtrl::GetTabArea`|Sekme denetimi sekme alanının konumunu ve boyutunu alır. (Geçersiz kılmaları [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|
|`CMFCOutlookBarTabCtrl::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Etkin sekmeler arasında geçiş sırasında gerçekleşen animasyonu etkin olup olmadığını belirler.|
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Outlook Çubuğu sekme denetimi, Microsoft Outlook 2003 öykünen bir modda olup olmadığını belirler.|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Bir sekme alanı içinde olup olmadığını belirler. (Geçersiz kılmaları [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Bir sekme çıkarılabilir olup olmadığını belirler. (Geçersiz kılmaları [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Bir sekme eklenen veya kaldırılan framework tarafından çağırılır. (Geçersiz kılmaları `CMFCBaseTabCtrl::OnChangeTabs`.)|
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Görülebilir sekmesinde sayfa düğmelerini sayısını azaltmak için framework tarafından çağırılır.|
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Görülebilir sekmesinde sayfa düğmelerini sayısını artırmak için framework tarafından çağırılır.|
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Görüntüler **Gezinti Bölmesi Seçenekleri** iletişim.|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Sekme denetimi iç düzenini yeniden hesaplar. (Geçersiz kılmaları [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Etkin sekmede ayarlar. (Geçersiz kılmaları [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Outlook sekme denetiminin kenarlık boyutunu ayarlar.|
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Outlook çubuğu üzerinde sekme düğmelerinin metin etiketlerini hizalamasını ayarlar.|
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Outlook 2003 modunda Outlook çubuğu altındaki görüntülenen simgeler içeren bir bit eşlemi ayarlar (bkz [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)).|
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||

## <a name="remarks"></a>Açıklamalar

Yerleştirme desteği olan bir Outlook çubuğu oluşturmak için bir `CMFCOutlookBar` Outlook Çubuğu Sekme denetimini barındırmak için nesne. Daha fazla bilgi için [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl başlatılacağını gösterir. bir `CMFCOutlookBarTabCtrl` nesne ve çeşitli yöntemlerle kullanma `CMFCOutlookBarTabCtrl` sınıfı. Örnek Outlook Çubuğu sekmesinde sayfa düğmelerini üzerindeki metin etiketinin yerinde düzenlemeyi etkinleştir, animasyon etkinleştirmek için kullanıcının Outlook Çubuğu bölmesi düğmelerini kaydırmak Outlook sekmesini devamı kenarlık boyutunu ayarlayın kaydırma tanıtıcıları etkinleştirme nasıl gösterir Rol ve Outlook Çubuğu sekme düğmelerinin metin etiketlerini hizalamasını ayarlama. Bu kod parçacığı parçasıdır [Outlook gösterim örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)

[CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxoutlookbartabctrl.h

##  <a name="addcontrol"></a>  CMFCOutlookBarTabCtrl::AddControl

Yeni bir sekmede Outlook çubuğu olarak bir Windows denetimini ekler.

```
void AddControl(
    CWnd* pWndCtrl,
    LPCTSTR lpszName,
    int nImageID=-1,
    BOOL bDetachable=TRUE,
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```

### <a name="parameters"></a>Parametreler

*pWndCtrl*<br/>
[in] Bir denetim eklemek için bir işaretçi.

*lpszName*<br/>
[in] Sekme adını belirtir.

*bDetachable*<br/>
[in] TRUE ise, sayfa gibi çıkarılabilir oluşturulur.

*nImageID*<br/>
[in] Yeni sekmede gösterilecek görüntü için iç görüntü listesinden görüntü dizini.

*dwControlBarStyle*<br/>
[in] Sarmalanan yerleştirme bölmesine AFX_ CBRS_ * stilini belirtir.

### <a name="remarks"></a>Açıklamalar

Yeni bir outlook çubuğu sayfa olarak bir denetim eklemek için bu işlevi kullanın.

Bu işlev üzerinde çağrısı [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).

Ayarlarsanız *bDetachable* true olarak `AddControl` dahili oluşturur bir `CDockablePaneAdapter` nesne ve eklenen denetimini sarar. Otomatik olarak çalışma zamanı sınıfı için sekmeli pencere çalışma zamanı sınıfının ayarlar `CMFCOutlookBar` ve kayan çerçevenin çalışma zamanı sınıfının `CMultiPaneFrameWnd`.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `AddControl` yönteminde `CMFCOutlookBarTabCtrl` sınıfı. Bu kod parçacığı parçasıdır [Outlook gösterim örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

##  <a name="canshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowFewerPageButtons

Yeniden boyutlandırma sırasında daha az Outlook Çubuğu sekmesinde sayfa düğmelerini görüntülenmekte olan daha gösterilip gösterilemeyeceğini belirlemek için işlemleri framework tarafından çağırılır.

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birden fazla düğmesini ise TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Outlook Çubuğu sekme denetimi dinamik olarak ekler veya ne kadar kullanılabilir yer bağlı olarak görünen sekmeler kaldırır. Bu yöntem, bu işlemde yardımcı olmak için framework tarafından kullanılır.

##  <a name="canshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowMorePageButtons

Daha fazla Outlook Çubuğu sekmesinde sayfa düğmelerini görüntülenmekte olan daha gösterilip gösterilemeyeceğini belirlemek için operations yeniden boyutlandırma sırasında framework tarafından çağırılır.

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda görünür olmayan düğmeler ise TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Outlook Çubuğu sekme denetimi dinamik olarak ekler veya sekmeleri ne kadar kullanılabilir yer bağlı olarak bu görünümden kaldırır. Bu yöntem, bu işlemde yardımcı olmak için framework tarafından kullanılır.

##  <a name="create"></a>  CMFCOutlookBarTabCtrl::Create

Outlook Çubuğu sekme denetimi oluşturur.

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[in] Başlangıç boyutu ve konumu, piksel cinsinden belirtir.

*pParentWnd*<br/>
[in] Üst pencere işaret eder. NULL olmamalıdır.

*nID*<br/>
[in] Denetim kimliği.

### <a name="return-value"></a>Dönüş Değeri

Denetim başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Genellikle, outlook çubuğu sekme denetimleri oluşturulur [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md) işleminin WM_CREATE ileti denetler.

##  <a name="enableanimation"></a>  CMFCOutlookBarTabCtrl::EnableAnimation

Etkin sekmeler arasında geçiş sırasında gerçekleşen animasyonu etkinleştirilip etkinleştirilmeyeceğini belirtir.

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Animasyon etkin veya devre dışı olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Enable ve disable animasyon için bu işlevi çağırın. Bir sekme sayfası kullanıcı oturum açtığında, animasyon etkinse, sayfanın başlığı yukarı veya aşağı çıkar. Animasyon devre dışıysa, sayfa hemen etkin hale gelir.

Varsayılan olarak, animasyon etkinleştirilir.

##  <a name="enableinplaceedit"></a>  CMFCOutlookBarTabCtrl::EnableInPlaceEdit

Bir kullanıcıya Outlook Çubuğu sekme sayfası düğmelerinin metin etiketlerini değiştirip değiştiremeyeceğini belirtir.

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
TRUE ise, yerinde düzenleme metin etiketi sağlar. FALSE ise, yerinde düzenleme devre dışı bırakın.

### <a name="remarks"></a>Açıklamalar

Etkinleştirmek veya devre dışı sekme sayfası düğmelerin üzerinde metin etiketlerin yerinde düzenleme için bu işlevi çağırın. Varsayılan olarak, yerinde düzenleme devre dışı bırakıldı.

##  <a name="enablescrollbuttons"></a>  CMFCOutlookBarTabCtrl::EnableScrollButtons

Outlook Çubuğu bölmesi düğmelerini kaydırmak kullanıcının olanak tanıyan kaydırma tanıtıcıları etkinleştirmek için framework tarafından çağırılır.

```
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Kaydırma düğmelerine görüntülenip görüntülenmeyeceğini belirler.

*bIsUp*<br/>
[in] Üst ScrollBar'ın görüntülenip görüntülenmeyeceğini belirler.

*bIsDown*<br/>
[in] Alt ScrollBar'ın görüntülenip görüntülenmeyeceğini belirler.

### <a name="remarks"></a>Açıklamalar

Kaydırma düğmelerine görüntülenmesini sağlar. Bu yöntem etkin sekmede kaydırma düğmelerine geri yüklemek için değiştiğinde framework tarafından çağırılır.

##  <a name="getbordersize"></a>  CMFCOutlookBarTabCtrl::GetBorderSize

Outlook sekme denetiminin kenarlık boyutunu döndürür.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kenarlığın piksel cinsinden boyutu.

##  <a name="getvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::GetVisiblePageButtons

```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="isanimation"></a>  CMFCOutlookBarTabCtrl::IsAnimation

Etkin sekmeler arasında geçiş sırasında gerçekleşen animasyonu etkinleştirilip etkinleştirilmeyeceğini belirtir.

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon etkin olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağrı [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) etkinleştirme veya devre dışı animasyon işlevi.

##  <a name="ismode2003"></a>  CMFCOutlookBarTabCtrl::IsMode2003

Outlook Çubuğu sekme denetimi, Microsoft Outlook 2003 öykünen bir modda olup olmadığını belirler.

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook Çubuğu sekme denetimi Outlook 2003 modundaysa TRUE; Aksi takdirde FALSE;

### <a name="remarks"></a>Açıklamalar

Bu değer ayarlanır [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).

##  <a name="onshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowFewerPageButtons

Görülebilir sekmesinde sayfa düğmelerini sayısını azaltmak için framework tarafından çağırılır.

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>Açıklamalar

Denetimi yeniden boyutlandırdığınızda bu yöntem sekme düğmelerinin görünür sayfa sayısını ayarlar.

##  <a name="onshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowMorePageButtons

Görülebilir sekmesinde sayfa düğmelerini sayısını artırmak için framework tarafından çağırılır.

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem denetimi yeniden boyutlandırdığınızda görünür olan sayfa düğmelerini sekmesini sayısını ayarlayın.

##  <a name="onshowoptions"></a>  CMFCOutlookBarTabCtrl::OnShowOptions

Görüntüler **Gezinti Bölmesi Seçenekleri** iletişim kutusu.

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>Açıklamalar

**Gezinti Bölmesi Seçenekleri** iletişim kutusu, kullanıcının sekme sayfası düğmelerinin görüntüleneceği seçin ve, bunların görüntülenme sırasını sağlar.

Bu yöntem, kullanıcı seçtiğinde framework tarafından çağrılır **Gezinti Bölmesi Seçenekleri** denetimin özelleştirme menüsünü menü öğesi.

##  <a name="setactivetab"></a>  CMFCOutlookBarTabCtrl::SetActiveTab

Etkin sekmede ayarlar. Etkin sekmede görünür içeriği ile açık olan bir bileşendir.

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>Parametreler

*iTab*<br/>
[in] Bir sekmede açılacak sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sekme başarıyla açılmış olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Etkin sekmede ayarlamanın görsel efekt animasyonu olup etkinleştirdiyseniz üzerinde bağlıdır. Daha fazla bilgi için [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).

##  <a name="setbordersize"></a>  CMFCOutlookBarTabCtrl::SetBorderSize

Outlook sekme denetiminin kenarlık boyutunu ayarlar.

```
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>Parametreler

*nBorderSize*<br/>
[in] Yeni sınır boyutunu piksel cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

Yeni sınır boyutu ayarlar ve outlook pencere düzenini yeniden hesaplar.

##  <a name="setpagebuttontextalign"></a>  CMFCOutlookBarTabCtrl::SetPageButtonTextAlign

Outlook çubuğu üzerinde sekme düğmelerinin metin etiketlerini hizalamasını ayarlar.

```
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*uiAlign*<br/>
[in] Metin hizalamasını belirtir.

*bRedraw*<br/>
[in] TRUE ise outlook penceresi çizilir.

### <a name="remarks"></a>Açıklamalar

Sayfa düğmelerini metin hizalamasını değiştirmek için bu işlevi kullanın.

*uiAlign* aşağıdaki değerlerden biri olabilir:

|Sabit|Açıklama|
|--------------|-------------|
|TA_LEFT|Sola hizalama|
|TA_CENTER|Ortala|
|TA_RIGHT|Sağa hizalama|

TA_CENTER varsayılan değerdir.

##  <a name="settoolbarimagelist"></a>  CMFCOutlookBarTabCtrl::SetToolbarImageList

Outlook 2003 modunda Outlook çubuğu altındaki görüntülenen simgeler içeren bir bit eşlemi ayarlar.

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[in] Yüklenecek görüntünün kaynak Kimliğini belirtir.

*cx*<br/>
[in] Piksel cinsinden görüntü listesinden görüntü genişliğini belirtir.

*clrTransp*<br/>
[in] Saydam rengini belirtir bir RGB değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sahipse TRUE değerini döndürür; Aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Microsoft Office 2003 modunda araç çubuğu düğmeleri görüntüleri görüntülenecek bir görüntü listesi eklemek için bu işlevi kullanın. Görüntü dizini sayfasını dizine karşılık gelmelidir.

Microsoft Office 2003 modundaysa değil, bu yöntem çağrılmamalıdır. Daha fazla bilgi için [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

##  <a name="setvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::SetVisiblePageButtons

```
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>Parametreler

[in] *nVisiblePageButtons*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCBaseTabCtrl Sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarPane Sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md)
