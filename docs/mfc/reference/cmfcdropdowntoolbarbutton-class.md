---
title: CMFCDropDownToolbarButton Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
ms.openlocfilehash: f09a2f3fe66abb86a8f220dbdf6744813ad9db0d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752399"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton Sınıfı

Tıklatıldığında normal bir düğme gibi görünen araç çubuğu düğmesi türü. Ancak, açılır araç çubuğunu açar (kullanıcı araç çubuğu düğmesine basıp basılı tutarsa [CMFCDropDownToolBar Class.](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="syntax"></a>Sözdizimi

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Bir `CMFCDropDownToolbarButton` nesne inşa eder.|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDropDropToolbarButton::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar. [(CMFCToolBarButton geçersiz kılar::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCDropDownToolbarButton::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Açılır araç çubuğu açılır.|
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Araç çubuğu düğmesinden menüye metni kopyalar. [(Overrides CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Düğmeyle ilişkili açılır araç çubuğunu alır.|
|`CMFCDropDownToolbarButton::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCDropDropToolbarButton::IsDropDown](#isdropdown)|Açılan araç çubuğunun şu anda açık olup olmadığını belirler.|
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Düğmenin genişletilmiş kenarlıkla görüntülenip görüntülenemeyeceğini belirler. [(Overrides CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|Belirtilen aygıt bağlamı ve yerleştirme durumu için düğmenin boyutunu hesaplamak için çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|`CMFCDropDownToolbarButton::OnCancelMode`|[WM_CANCELMODE](/windows/win32/winmsg/wm-cancelmode) iletisini işlemek için çerçeve tarafından çağrılır. (Geçersiz `CMCToolBarButton::OnCancelMode`kılar .)|
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Düğme yeni bir araç çubuğuna takıldığında çerçeve tarafından çağrılır. [(Üstyüklemeler CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCDropDownToolbarButton::Tıklayın](#onclick)|Kullanıcı fare düğmesini tıklattığında çerçeve tarafından çağrılır. [(Overrides CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Kullanıcı fare düğmesini serbest bıraktığunda çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|
|[CMFCDropDropToolbarButton::OnContextHelp](#oncontexthelp)|Üst araç çubuğu bir WM_HELPHITTEST iletisi işlediğinde çerçeve tarafından çağrılır. [(Overrides CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Uygulama ana araç çubuğunda bir kısayol menüsü görüntülendiğinde sağlanan menüyü değiştirir. (Geçersiz kılar [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|Belirtilen stilleri ve seçenekleri kullanarak düğmeyi çizmek için çerçeve tarafından çağrılır. [(CMFCToolBarButton geçersiz kılar::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|**Özelleştir** iletişim kutusunun **Komutlar** bölmesinde düğmeyi çizmek için çerçeve tarafından çağrılır. [(Overrides CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCDropDownToolbarButton::Serialize](#serialize)|Bu nesneyi arşivden okur veya arşive yazar. [(CMFCToolBarButton geçersiz kılar::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Kullanıcı düğmeyi tıklattığında çerçevenin kullandığı varsayılan komutu ayarlar.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Açılan araç çubuğu görünmeden önce kullanıcının fare düğmesini basılı tutması gereken süreyi belirtir.|

## <a name="remarks"></a>Açıklamalar

A, `CMFCDropDownToolBarButton` düğmenin sağ alt köşesinde küçük bir ok olması nedeniyle sıradan bir düğmeden farklıdır. Kullanıcı açılır araç çubuğundan bir düğme seçtikten sonra, çerçeve simgesini üst düzey araç çubuğu düğmesinde (sağ alt köşedeki küçük oklu düğme) görüntüler.

Açılır araç çubuğunun nasıl uygulanacağı hakkında bilgi için [CMFCDropDownToolBar Class'a](../../mfc/reference/cmfcdropdowntoolbar-class.md)bakın.

Nesne `CMFCDropDownToolBarButton` [cmfcToolBarMenuButton Sınıf](../../mfc/reference/cmfctoolbarmenubutton-class.md) nesnesine dışa aktarılabilir ve açılır menülü bir menü düğmesi olarak görüntülenebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCDropDropToolbarButton::CopyFrom

Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[içinde] Kopyalamak için kaynak düğmesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Başka bir araç çubuğu düğmesini bu araç çubuğu düğmesine kopyalamak için bu yöntemi arayın. *src* türünde `CMFCDropDownToolbarButton`olmalıdır.

## <a name="cmfcdropdowntoolbarbuttoncmfcdropdowntoolbarbutton"></a><a name="cmfcdropdowntoolbarbutton"></a>CMFCDropDownToolbarButton::CMFCDropDownToolbarButton

Bir `CMFCDropDownToolbarButton` nesne inşa eder.

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
[içinde] Düğmenin varsayılan metni.

*pToolBar*<br/>
[içinde] Kullanıcı düğmeye `CMFCDropDownToolBar` bastığında görüntülenen nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Oluşturucu kopyaların ikinci aşırı yükü, *pToolBar'ın* belirttiği araç çubuğundan ilk düğmeyi açılır düğmeye basılır.

Genellikle, açılır araç çubuğu *düğmesi, pToolBar'ın* belirttiği araç çubuğunda en son kullanılan düğmedeki metni kullanır. Düğme bir menü düğmesine dönüştürüldüğünde veya **Özelleştir** iletişim kutusunun **Komutlar** sekmesinde görüntülendiğinde *lpszName* tarafından belirtilen metni kullanır. **Özelleştir** iletişim kutusu hakkında daha fazla bilgi için [CMFCToolBarsCustomizeDialog Class'a](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCDropDownToolbarButton` nasıl inşa edilebildiğini gösterir. Bu kod snippet [Visual Studio Demo örnek](../../overview/visual-cpp-samples.md)parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

## <a name="cmfcdropdowntoolbarbuttondropdowntoolbar"></a><a name="dropdowntoolbar"></a>CMFCDropDownToolbarButton::DropDownToolbar

Açılır araç çubuğu açılır.

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Açılır çerçevenin üst penceresi veya açılır araç çubuğunun üst penceresini kullanmak için NULL.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[CMFCDropDropToolbarButton::OnClick](#onclick) yöntemi, kullanıcı araç çubuğu düğmesine bastığında ve basılı tuttuğunda açılır araç çubuğunu açmak için bu yöntemi çağırır.

Bu [yöntem, CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create) yöntemini kullanarak açılır araç çubuğunu oluşturur. Üst araç çubuğu dikey olarak sabitlenirse, bu yöntem, açılan araç çubuğunu sığmaya bağlı olarak üst araç çubuğunun sol veya sağ tarafına yerlebir olur. Aksi takdirde, bu yöntem açılır araç çubuğunu üst araç çubuğunun altına yerlebir olur.

*PWnd* NULL ise ve açılır araç çubuğu düğmesinde üst pencere yoksa bu yöntem başarısız olur.

## <a name="cmfcdropdowntoolbarbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCDropDownToolbarButton::ExportToMenuButton

Araç çubuğu düğmesinden menüye metni kopyalar.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parametreler

*menüDüğme*<br/>
[içinde] Hedef menü düğmesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem taban sınıf uygulamasını [(CMFCToolBarButton::ExportToMenuButton)](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)çağırır ve ardından hedef menüye eklenen bu düğmedeki her araç çubuğu menü öğesini içeren bir açılır menü ekler. Bu yöntem, alt menüleri açılır menüye eklemiyor.

Ana araç çubuğu, `m_pToolBar`NULL ise veya taban sınıf uygulaması FALSE döndürür, bu yöntem başarısız olur.

## <a name="cmfcdropdowntoolbarbuttongetdropdowntoolbar"></a><a name="getdropdowntoolbar"></a>CMFCDropDownToolbarButton::GetDropDownToolBar

Düğmeyle ilişkili açılır araç çubuğunu alır.

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeyle ilişkili açılır araç çubuğu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `m_pToolBar` veri üyesidöndürür.

## <a name="cmfcdropdowntoolbarbuttonisdropdown"></a><a name="isdropdown"></a>CMFCDropDropToolbarButton::IsDropDown

Açılan araç çubuğunun şu anda açık olup olmadığını belirler.

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan araç çubuğu şu anda açıksa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çerçeve [CMFCDropDropToolbarButton::DropDownToolbar](#dropdowntoolbar) yöntemini kullanarak açılır araç çubuğunu açar. Kullanıcı açılır araç çubuğunun istemci olmayan alanında sol fare düğmesine bastığında çerçeve açılır araç çubuğunu kapatır.

## <a name="cmfcdropdowntoolbarbuttonisextrasize"></a><a name="isextrasize"></a>CMFCDropDownToolbarButton::IsExtraSize

Düğmenin genişletilmiş kenarlıkla görüntülenip görüntülenemeyeceğini belirler.

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç çubuğu düğmesi genişletilmiş kenarlıkla görüntülenebiliyorsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş kenarlıklar hakkında daha fazla bilgi için [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize)' a bakın.

## <a name="cmfcdropdowntoolbarbuttonm_uishowbardelay"></a><a name="m_uishowbardelay"></a>CMFCDropDownToolbarButton::m_uiShowBarDelay

Açılan araç çubuğu görünmeden önce kullanıcının fare düğmesini basılı tutması gereken süreyi belirtir.

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>Açıklamalar

Gecikme süresi milisaniye cinsinden ölçülür. Varsayılan değer 500'dür. Bu paylaşılan veri üyesinin değerini değiştirerek başka bir gecikme ayarlayabilirsiniz.

## <a name="cmfcdropdowntoolbarbuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFCDropDownToolbarButton::OnCalculateSize

Belirtilen aygıt bağlamı ve yerleştirme durumu için düğmenin boyutunu hesaplamak için çerçeve tarafından çağrılır.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğmeyi görüntüleyen aygıt bağlamı.

*boyutVarsayılan*<br/>
[içinde] Düğmenin varsayılan boyutu.

*bHorz*<br/>
[içinde] Ana araç çubuğunun dock durumu. Araç çubuğu yatay olarak kenetlenmişse veya kayarsa bu parametre DOĞRUDUR veya araç çubuğu dikey olarak kenetlenmişse FALSE.

### <a name="return-value"></a>Dönüş Değeri

Pikselolarak düğmenin boyutlarını içeren bir `SIZE` yapı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, açılan ok genişliğini düğme boyutunun yatay boyutuna ekleyerek taban sınıf uygulamasını [(CMFCToolBarButton::OnCalculateSize)](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)genişletir.

## <a name="cmfcdropdowntoolbarbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCDropDownToolbarButton::OnChangeParentWnd

Düğme yeni bir araç çubuğuna takıldığında çerçeve tarafından çağrılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Yeni ana pencere.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, metin etiketini ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) temizleyerek ve [CMFCToolBarButton:m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) ve [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) veri üyelerini FALSE'a ayarlayarak taban sınıf uygulamasını [(CMFCToolBarButton::OnChangeParentWnd)](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)geçersiz kılar.

## <a name="cmfcdropdowntoolbarbuttononclick"></a><a name="onclick"></a>CMFCDropDownToolbarButton::Tıklayın

Kullanıcı fare düğmesini tıklattığında çerçeve tarafından çağrılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Araç çubuğu düğmesinin ana penceresi.

*bGecikme*<br/>
[içinde] İleti bir gecikme ile ele alınması gerekiyorsa TRUE.

### <a name="return-value"></a>Dönüş Değeri

Düğme tıklama iletisini işlerse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem taban sınıf uygulamasını genişletir, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), açılır araç çubuğunun durumunu güncelleştirerek.

Bir kullanıcı araç çubuğu düğmesini tıklattığında, bu yöntem [CMFCDropDropToolbarButton](#m_uishowbardelay) tarafından belirtilen süreyi bekleyen bir zamanlayıcı oluşturur::m_uiShowBarDelay veri üyesi ve ardından [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) yöntemini kullanarak açılır araç çubuğunu açar. Bu yöntem, kullanıcı araç çubuğu düğmesini ikinci kez tıklatıldığında açılır araç çubuğunu kapatır.

## <a name="cmfcdropdowntoolbarbuttononclickup"></a><a name="onclickup"></a>CMFCDropDownToolbarButton::OnClickUp

Kullanıcı fare düğmesini serbest bıraktığunda çerçeve tarafından çağrılır.

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>Dönüş Değeri

Düğme tıklama iletisini işlerse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem taban sınıf uygulamasını genişletir, [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), açılır araç çubuğunun durumunu güncelleştirerek.

Bu yöntem, etkinse açılır araç çubuğu zamanlayıcısını durdurur. Açılır araç çubuğu açıksa kapatır.

Açılan araç çubuğu ve açılır araç çubuğu zamanlayıcısı hakkında daha fazla bilgi için [CMFCDropDropToolbarButton:OnClick](#onclick)' e bakın.

## <a name="cmfcdropdowntoolbarbuttononcontexthelp"></a><a name="oncontexthelp"></a>CMFCDropDropToolbarButton::OnContextHelp

Üst araç çubuğu bir WM_HELPHITTEST iletisi işlediğinde çerçeve tarafından çağrılır.

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Araç çubuğu düğmesinin ana penceresi.

### <a name="return-value"></a>Dönüş Değeri

Düğme yardım iletisini işlerse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu [yöntem, CMFCDropDropToolbarButton::OnClick](#onclick) yöntemi niFALSE *olarak* ayarlanmış olarak çağırarak taban sınıf uygulamasını [(CMFCToolBarButton::OnContextHelp)](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)genişletir. Bu yöntem [CMFCDropDropToolbarButton](#onclick)tarafından döndürülen değeri döndürür::OnClick .

WM_HELPHITTEST iletisi hakkında daha fazla bilgi için Bkz. [TN028: Bağlam Duyarlı Yardım Desteği.](../../mfc/tn028-context-sensitive-help-support.md)

## <a name="cmfcdropdowntoolbarbuttononcustomizemenu"></a><a name="oncustomizemenu"></a>CMFCDropDownToolbarButton::OnCustomizeMenu

Uygulama ana araç çubuğunda bir kısayol menüsü görüntülendiğinde sağlanan menüyü değiştirir.

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Parametreler

*pMenü*<br/>
[içinde] Özelleştirilen menü.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, aşağıdaki menü öğelerini devre dışı bırakarak taban sınıf uygulamasını [(CMFCToolBarButton::OnCustomizeMenu)](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)genişletir:

- **Kopya düğmesi Görüntüsü**

- **Düğme Görünümü**

- **Görüntü**

- **Metin**

- **Resim ve Metin**

Çerçevenin özelleştirme modunda görüntülenebilen kısayol menüsünü değiştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfcdropdowntoolbarbuttonondraw"></a><a name="ondraw"></a>CMFCDropDownToolbarButton::OnDraw

Belirtilen stilleri ve seçenekleri kullanarak düğmeyi çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğmeyi görüntüleyen aygıt bağlamı.

*Rect*<br/>
[içinde] Düğmenin sınırlayıcı dikdörtgeni.

*pImages*<br/>
[içinde] Düğmeyle ilişkili araç çubuğu görüntülerinin toplanması.

*bHorz*<br/>
[içinde] Ana araç çubuğunun dock durumu. Bu parametre, düğme yatay olarak kenetlendiğinde DOĞRU, düğme dikey olarak kenetlendiğinde FALSE'dir.

*bCustomizeMode*<br/>
[içinde] Araç çubuğunun özelleştirme modunda olup olmadığını belirtir. Araç çubuğu özelleştirme modundayken bu parametre TRUE ve araç çubuğu özelleştirme modunda olmadığında FALSE'dur.

*bVurgu*<br/>
[içinde] Düğmenin vurgulanıp vurgulanmayacağını belirtir. Bu parametre, düğme vurgulandığında DOĞRU, düğme vurgulanmadığında FALSE'dir.

*bDrawBorder*<br/>
[içinde] Düğmenin kenarlığını gösterip göstermeyeceğini belirtir. Bu parametre, düğme kenarlığını görüntülemesi gerektiğinde doğru, düğme kenarlıkını ise FALSE'da görüntülenir.

*bGrayDisabledButtons*<br/>
[içinde] Devre dışı bırakılan düğmeleri gölgeleyip gölgelemeyeceğiniz veya devre dışı bırakılan görüntüler koleksiyonunu kullanıp kullanmayacağını belirtir. Devre dışı bırakılan düğmeler gölgelendirilmeli ve bu yöntem devre dışı bırakılan görüntüler koleksiyonunu kullanmalıdır bu parametre DOĞRUDUR.

### <a name="remarks"></a>Açıklamalar

Araç çubuğu düğme çizimini özelleştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfcdropdowntoolbarbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCDropDownToolbarButton::OnDrawOnCustomizeList

**Özelleştir** iletişim kutusunun **Komutlar** bölmesinde düğmeyi çizmek için çerçeve tarafından çağrılır.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğmeyi görüntüleyen aygıt bağlamı.

*Rect*<br/>
[içinde] Düğmenin sınırlayıcı dikdörtgeni.

*bSelected*<br/>
[içinde] Düğmenin seçilip seçilmediği. Bu parametre TRUE ise, düğme seçilir. Bu parametre FALSE ise, düğme seçilmez.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen aygıt bağlamında düğmenin piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, düğmenin kendisini sahip-çizim listesi kutusunda görüntülemesi gerektiğinde özelleştirme iletişim kutusu **(Komutlar** sekmesi) tarafından çağrılır.

Bu yöntem, düğmenin metin etiketini düğmenin adıyla (yani oluşturucuya geçtiğiniz *lpszName* parametresinin değerine) değiştirerek taban sınıf uygulamasını [(CMFCToolBarButton::OnDrawOnCustomizeList)](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)genişletir.

## <a name="cmfcdropdowntoolbarbuttonserialize"></a><a name="serialize"></a>CMFCDropDownToolbarButton::Serialize

Bu nesneyi arşivden okur veya arşive yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
[içinde] Hangi `CArchive` veya serihale nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ana araç çubuğunun kaynak kimliğini serileştirerek taban sınıf uygulamasını [(CMFCToolBarButton::Serialize)](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)genişletir. Arşiv yüklenirken [(CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) sıfır olmayan bir değer `m_pToolBar` döndürür), bu yöntem veri üyesini serileştirilmiş kaynak kimliğini içeren araç çubuğuna ayarlar.

## <a name="cmfcdropdowntoolbarbuttonsetdefaultcommand"></a><a name="setdefaultcommand"></a>CMFCDropDownToolbarButton::SetDefaultCommand

Kullanıcı düğmeyi tıklattığında çerçevenin kullandığı varsayılan komutu ayarlar.

```cpp
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*uiCmd*<br/>
[içinde] Varsayılan komutun kimliği.

### <a name="remarks"></a>Açıklamalar

Kullanıcı düğmeyi tıklattığında çerçevenin çalıştırdığı varsayılan komutu belirtmek için bu yöntemi çağırın. *uiCmd* tarafından belirtilen komut kimliğine sahip bir öğe, üst açılır araç çubuğunda bulunmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolToolBar Sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarMenuButton Sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
