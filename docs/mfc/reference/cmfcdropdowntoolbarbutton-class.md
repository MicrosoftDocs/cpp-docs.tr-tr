---
title: CMFCDropDownToolbarButton sınıfı
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
ms.openlocfilehash: fcfb521e309463da81d0064451297b3b73610d2f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505327"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton sınıfı

Tıklandığı zaman normal düğme gibi davranan bir araç çubuğu düğmesi türü. Ancak, Kullanıcı araç çubuğu düğmesini aşağı basarsa ve tutuyorsa bir açılan araç çubuğu ( [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md) ) açar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDropDownToolbarButton:: CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Bir `CMFCDropDownToolbarButton` nesnesi oluşturur.|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDropDownToolbarButton:: CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar. ( [CMFCToolBarButton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCDropDownToolbarButton::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCDropDownToolbarButton::D ropDownToolbar](#dropdowntoolbar)|Açılan araç çubuğunu açar.|
|[CMFCDropDownToolbarButton:: Exporttomenubtan](#exporttomenubutton)|Araç çubuğu düğmesinden bir menüye metin kopyalar. ( [CMFCToolBarButton:: Exporttomenubtan](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)geçersiz kılar.)|
|[CMFCDropDownToolbarButton:: GetDropDownToolBar](#getdropdowntoolbar)|Düğmeyle ilişkili açılan araç çubuğunu alır.|
|`CMFCDropDownToolbarButton::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCDropDownToolbarButton:: IsDropDown](#isdropdown)|Açılan araç çubuğunun Şu anda açık olup olmadığını belirler.|
|[CMFCDropDownToolbarButton:: IsExtraSize](#isextrasize)|Düğmenin genişletilmiş bir kenarlıkla görüntülenip görüntülenemeyeceğini belirler. ( [CMFCToolBarButton:: IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize)geçersiz kılar.)|
|[CMFCDropDownToolbarButton:: OnCalculateSize](#oncalculatesize)|Belirtilen cihaz bağlamı ve yerleştirme durumu için düğmenin boyutunu hesaplamak üzere Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).) öğesini geçersiz kılar|
|`CMFCDropDownToolbarButton::OnCancelMode`|[WM_CANCELMODE](/windows/win32/winmsg/wm-cancelmode) iletisini işlemek için Framework tarafından çağırılır. (Geçersiz `CMCToolBarButton::OnCancelMode`kılmalar.)|
|[CMFCDropDownToolbarButton:: OnChangeParentWnd](#onchangeparentwnd)|Düğme yeni bir araç çubuğuna eklendiğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)geçersiz kılar.)|
|[CMFCDropDownToolbarButton:: OnClick](#onclick)|Kullanıcı fare düğmesine tıkladığında Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)geçersiz kılar.)|
|[CMFCDropDownToolbarButton:: OnClickUp](#onclickup)|Kullanıcı fare düğmesini bıraktığında Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)geçersiz kılar.)|
|[CMFCDropDownToolbarButton:: OnContextHelp](#oncontexthelp)|Ana araç çubuğu bir WM_HELPHITTEST iletisini işlediğinde Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)geçersiz kılar.)|
|[CMFCDropDownToolbarButton:: OnCustomizeMenu](#oncustomizemenu)|Uygulama üst araç çubuğunda bir kısayol menüsü görüntülediğinde, belirtilen menüyü değiştirir. ( [CMFCToolBarButton:: OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).) öğesini geçersiz kılar|
|[CMFCDropDownToolbarButton:: OnDraw](#ondraw)|Belirtilen stilleri ve seçenekleri kullanarak düğmeyi çizmek için Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw)geçersiz kılar.)|
|[CMFCDropDownToolbarButton:: OnDrawOnCustomizeList](#ondrawoncustomizelist)|**Özelleştirme** Iletişim kutusunun **Komutlar** bölmesinde düğme çizmek için Framework tarafından çağırılır. ( [CMFCToolBarButton:: OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).) öğesini geçersiz kılar|
|[CMFCDropDownToolbarButton:: serileştirme](#serialize)|Bu nesneyi bir arşivden okur veya bir arşive yazar. ( [CMFCToolBarButton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)geçersiz kılar.)|
|[CMFCDropDownToolbarButton:: SetDefaultCommand](#setdefaultcommand)|Bir Kullanıcı düğmeye tıkladığında çerçevenin kullandığı varsayılan komutu ayarlar.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDropDownToolbarButton:: m_uiShowBarDelay](#m_uishowbardelay)|Bir kullanıcının, açılan araç çubuğunun görünmesi için fare düğmesini aşağı tutması gereken süre uzunluğunu belirtir.|

## <a name="remarks"></a>Açıklamalar

, Düğmenin sağ alt köşesinde küçük bir oka sahip olan sıradan bir düğmeden farklıdır.`CMFCDropDownToolBarButton` Kullanıcı açılan araç çubuğundan bir düğme seçtikten sonra çerçeve, üst düzey araç çubuğu düğmesinde (sağ alt köşedeki küçük oka sahip düğme) kendi simgesini görüntüler.

Açılan araç çubuğunun nasıl uygulanacağı hakkında daha fazla bilgi için bkz. [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md).

Nesne bir [cmfctoolbarmenubtan Class](../../mfc/reference/cmfctoolbarmenubutton-class.md) nesnesine aktarılabilir ve açılır menü ile bir menü düğmesi olarak görüntülenebilir. `CMFCDropDownToolBarButton`

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdropdowntoolbar. h

##  <a name="copyfrom"></a>CMFCDropDownToolbarButton:: CopyFrom

Başka bir araç çubuğu düğmesinin özelliklerini geçerli düğmeye kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*YN*<br/>
'ndaki Kopyalanacak kaynak düğmesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu araç çubuğu düğmesine başka bir araç çubuğu düğmesi kopyalamak için bu yöntemi çağırın. *src* türünde `CMFCDropDownToolbarButton`olmalıdır.

##  <a name="cmfcdropdowntoolbarbutton"></a>CMFCDropDownToolbarButton:: CMFCDropDownToolbarButton

Bir `CMFCDropDownToolbarButton` nesnesi oluşturur.

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
'ndaki Düğmenin varsayılan metni.

*pToolBar*<br/>
'ndaki Kullanıcı düğmeye bastığında görüntülenen `CMFCDropDownToolBar` nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun ikinci aşırı yüklemesi, *pToolBar* 'ın belirttiği araç çubuğundan ilk düğme açılan düğmesine kopyalar.

Genellikle, açılan araç çubuğu düğmesi, *pToolBar* 'ın belirttiği araç çubuğundaki en son kullanılan düğmeden metni kullanır. Düğme bir menü düğmesine dönüştürüldüğünde veya **Özelleştir** Iletişim kutusunun **Komutlar** sekmesinde görüntülendiğinde, *lpszName* tarafından belirtilen metni kullanır. **Özelleştirme** iletişim kutusu hakkında daha fazla bilgi için bkz. [CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCDropDownToolbarButton` sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir. Bu kod parçacığı, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

##  <a name="dropdowntoolbar"></a>CMFCDropDownToolbarButton::D ropDownToolbar

Açılan araç çubuğunu açar.

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Aşağı açılan araç çubuğu düğmesinin ana penceresini kullanmak için açılır çerçevenin üst penceresi veya NULL.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[CMFCDropDownToolbarButton:: OnClick](#onclick) yöntemi, Kullanıcı araç çubuğu düğmesini aşağı bastığında ve elinde tuttuğunda açılan araç çubuğunu açmak için bu yöntemi çağırır.

Bu yöntemler [CMFCDropDownFrame:: Create](../../mfc/reference/cmfcdropdownframe-class.md#create) metodunu kullanarak açılan araç çubuğunu oluşturur. Ana araç çubuğu dikey olarak yerleştirilmişse, bu yöntem aşağı açılan araç çubuğunu üst araç çubuğunun sol veya sağ tarafına, pencereye göre konumlandırır. Aksi takdirde, bu yöntem ana araç çubuğunun altındaki açılan araç çubuğunu konumlandırır.

*PWnd* null ise ve açılan araç çubuğu düğmesi bir üst pencere içermiyorsa, bu yöntem başarısız olur.

##  <a name="exporttomenubutton"></a>CMFCDropDownToolbarButton:: Exporttomenubtan

Araç çubuğu düğmesinden bir menüye metin kopyalar.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parametreler

*menuButton*<br/>
'ndaki Hedef menü düğmesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, temel sınıf uygulamasını çağırır ( [CMFCToolBarButton:: Exporttomenubtan](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) ve ardından hedef menü düğmesine, Bu düğmedeki her bir araç çubuğu menü öğesini içeren bir açılır menü düğmesine ekler. Bu yöntem, açılır menüye alt menüler eklemez.

Ana araç çubuğu `m_pToolBar`, null ise veya temel sınıf uygulama yanlış döndürürse bu yöntem başarısız olur.

##  <a name="getdropdowntoolbar"></a>CMFCDropDownToolbarButton:: GetDropDownToolBar

Düğmeyle ilişkili açılan araç çubuğunu alır.

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeyle ilişkili açılan araç çubuğu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `m_pToolBar` veri üyesini döndürür.

##  <a name="isdropdown"></a>CMFCDropDownToolbarButton:: IsDropDown

Açılan araç çubuğunun Şu anda açık olup olmadığını belirler.

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan araç çubuğu açık ise sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Framework, [CMFCDropDownToolbarButton::D ropDownToolbar](#dropdowntoolbar) yöntemini kullanarak açılan araç çubuğunu açar. Kullanıcı açılan araç çubuğunun istemci olmayan alanındaki sol fare düğmesine bastığında çerçeve açılan araç çubuğunu kapatır.

##  <a name="isextrasize"></a>CMFCDropDownToolbarButton:: IsExtraSize

Düğmenin genişletilmiş bir kenarlıkla görüntülenip görüntülenemeyeceğini belirler.

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç çubuğu düğmesi genişletilmiş bir kenarlıkla görüntülenebiliyorsanız sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş kenarlıklar hakkında daha fazla bilgi için bkz. [CMFCToolBarButton:: IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).

##  <a name="m_uishowbardelay"></a>CMFCDropDownToolbarButton:: m_uiShowBarDelay

Bir kullanıcının, açılan araç çubuğunun görünmesi için fare düğmesini aşağı tutması gereken süre uzunluğunu belirtir.

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>Açıklamalar

Gecikme süresi milisaniye cinsinden ölçülür. Varsayılan değer 500'dür. Bu paylaşılan veri üyesinin değerini değiştirerek başka bir gecikme da ayarlayabilirsiniz.

##  <a name="oncalculatesize"></a>CMFCDropDownToolbarButton:: OnCalculateSize

Belirtilen cihaz bağlamı ve yerleştirme durumu için düğmenin boyutunu hesaplamak üzere Framework tarafından çağırılır.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Düğmeyi görüntüleyen cihaz bağlamı.

*sizeDefault*<br/>
'ndaki Düğmenin varsayılan boyutu.

*bHorz*<br/>
'ndaki Üst araç çubuğunun yerleştirme durumu. Bu parametre, araç çubuğu yatay olarak yuvalanmışsa veya yüzer ise TRUE, araç çubuğu dikey olarak yuvalanmışsa FALSE 'TUR.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin `SIZE` boyutlarını piksel cinsinden içeren bir yapı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, aşağı açılan okun genişliğini düğme boyutunun yatay boyutuna ekleyerek temel sınıf uygulamasını ( [CMFCToolBarButton:: OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)) genişletir.

##  <a name="onchangeparentwnd"></a>CMFCDropDownToolbarButton:: OnChangeParentWnd

Düğme yeni bir araç çubuğuna eklendiğinde Framework tarafından çağırılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Yeni üst pencere.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, metin etiketini temizleyerek (CMFCToolBarButton:: [m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) ve [CMFCToolBarButton:: M_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) ve CMFCToolBarButton 'ı ayarlayarak temel sınıf uygulamasını ( [CMFCToolBarButton:: OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) geçersiz kılar [ :: m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) veri üyeleri false olarak ayarlandı.

##  <a name="onclick"></a>CMFCDropDownToolbarButton:: OnClick

Kullanıcı fare düğmesine tıkladığında Framework tarafından çağırılır.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Araç çubuğu düğmesinin üst penceresi.

*bDelay*<br/>
'ndaki İleti bir gecikmeyle işlenirse doğru.

### <a name="return-value"></a>Dönüş Değeri

Düğme tıklama iletisini işliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, açılan araç çubuğunun durumunu güncelleştirerek [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)temel sınıf uygulamasını genişletir.

Kullanıcı araç çubuğu düğmesine tıkladığında, bu yöntem [CMFCDropDownToolbarButton:: m_uiShowBarDelay](#m_uishowbardelay) veri üyesi tarafından belirtilen sürenin uzunluğunu bekleyen bir zamanlayıcı oluşturur ve ardından [CMFCDropDownToolBarButton kullanarak açılır araç çubuğunu açar ::D ropDownToolbar](#dropdowntoolbar) yöntemi. Bu yöntem, Kullanıcı araç çubuğu düğmesine tıkladığında ikinci kez açılan araç çubuğunu kapatır.

##  <a name="onclickup"></a>CMFCDropDownToolbarButton:: OnClickUp

Kullanıcı fare düğmesini bıraktığında Framework tarafından çağırılır.

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>Dönüş Değeri

Düğme tıklama iletisini işliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, açılan araç çubuğunun durumunu güncelleştirerek [CMFCToolBarButton:: OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)temel sınıf uygulamasını genişletir.

Bu yöntem etkinse, açılan araç çubuğu zamanlayıcısını sonlandırır. Açık ise, açılan araç çubuğunu kapatır.

Açılan araç çubuğu ve açılan araç çubuğu Zamanlayıcısı hakkında daha fazla bilgi için bkz. [CMFCDropDownToolbarButton:: OnClick](#onclick).

##  <a name="oncontexthelp"></a>CMFCDropDownToolbarButton:: OnContextHelp

Ana araç çubuğu bir WM_HELPHITTEST iletisini işlediğinde Framework tarafından çağırılır.

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Araç çubuğu düğmesinin üst penceresi.

### <a name="return-value"></a>Dönüş Değeri

Düğme, yardım iletisini işliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *bDelay* 'i false olarak ayarlayarak [CMFCDropDownToolbarButton:: OnClick](#onclick) metodunu çağırarak temel sınıf uygulamasını ( [CMFCToolBarButton:: OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) genişletir. Bu yöntem, [CMFCDropDownToolbarButton:: OnClick](#onclick)tarafından döndürülen değeri döndürür.

WM_HELPHITTEST iletisi hakkında daha fazla bilgi için bkz [. TN028: Bağlama duyarlı yardım desteği](../../mfc/tn028-context-sensitive-help-support.md).

##  <a name="oncustomizemenu"></a>CMFCDropDownToolbarButton:: OnCustomizeMenu

Uygulama üst araç çubuğunda bir kısayol menüsü görüntülediğinde, belirtilen menüyü değiştirir.

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Parametreler

*pMenu*<br/>
'ndaki Özelleştirilecek menü.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, aşağıdaki menü öğelerini devre dışı bırakarak temel sınıf uygulamasını ( [CMFCToolBarButton:: OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) genişletir:

- **Düğme görüntüsünü Kopyala**

- **Düğme görünümü**

- **Görüntü**

- **Metin**

- **Resim ve metin**

Framework 'ün özelleştirme modunda görüntülediği kısayol menüsünü değiştirmek için bu yöntemi geçersiz kılın.

##  <a name="ondraw"></a>CMFCDropDownToolbarButton:: OnDraw

Belirtilen stilleri ve seçenekleri kullanarak düğmeyi çizmek için Framework tarafından çağırılır.

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

*Kökündeki*<br/>
'ndaki Düğmeyi görüntüleyen cihaz bağlamı.

*Rect*<br/>
'ndaki Düğmenin sınırlayıcı dikdörtgeni.

*Pımages*<br/>
'ndaki Düğmeyle ilişkili araç çubuğu görüntülerinin koleksiyonu.

*bHorz*<br/>
'ndaki Üst araç çubuğunun yerleştirme durumu. Bu parametre, düğme yatay olarak yerleştirildiğinde TRUE, düğme dikey olarak yuvalandığında FALSE 'TUR.

*bCustomizeMode*<br/>
'ndaki Araç çubuğunun özelleştirme modunda olup olmadığını belirtir. Araç çubuğu özelleştirme modundayken ve araç çubuğu özelleştirme modunda olmadığında, bu parametre TRUE şeklindedir.

*bHighlight*<br/>
'ndaki Düğmenin vurgulanıp vurgulanmadığını belirtir. Düğme vurgulandığında Bu parametre TRUE, düğme vurgulanmamışsa FALSE.

*bDrawBorder*<br/>
'ndaki Düğmenin kenarlığını görüntülemesi gerekip gerekmediğini belirtir. Bu parametre, düğmenin kenarlığını görüntülemesi gerektiğinde TRUE, düğme kenarlığını göstermemelidir.

*Bgride Disabledbutton*<br/>
'ndaki Devre dışı bırakılan düğmeleri gölgelendirip gölgeedilmeyeceğini veya devre dışı bırakılan görüntüler koleksiyonunu kullanmayı belirtir. Devre dışı bırakılan düğmeler gölgeli ve bu yöntemin devre dışı görüntüler koleksiyonunu kullanması gerektiğinde FALSE olduğunda bu parametre TRUE şeklindedir.

### <a name="remarks"></a>Açıklamalar

Araç çubuğu düğme çizimini özelleştirmek için bu yöntemi geçersiz kılın.

##  <a name="ondrawoncustomizelist"></a>CMFCDropDownToolbarButton:: OnDrawOnCustomizeList

**Özelleştirme** Iletişim kutusunun **Komutlar** bölmesinde düğme çizmek için Framework tarafından çağırılır.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Düğmeyi görüntüleyen cihaz bağlamı.

*Rect*<br/>
'ndaki Düğmenin sınırlayıcı dikdörtgeni.

*bSelected*<br/>
'ndaki Düğme seçili olup olmadığı. Bu parametre TRUE ise düğme seçilidir. Bu parametre FALSE ise, düğme seçili değildir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen cihaz bağlamındaki düğmenin piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, düğme kendisini sahip çizimi liste kutusunda görüntülemesi gerektiğinde özelleştirme iletişim kutusu ( **Komutlar** sekmesi) tarafından çağrılır.

Bu yöntem, düğmenin metin etiketini düğme adına (yani, oluşturucuya geçirmekte olduğunuz *lpszName* parametresinin değerine) değiştirerek temel sınıf uygulamasını ( [CMFCToolBarButton:: OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) genişletir. ).

##  <a name="serialize"></a>CMFCDropDownToolbarButton:: serileştirme

Bu nesneyi bir arşivden okur veya bir arşive yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
'ndaki İçinden seri hale getirilecek nesne.`CArchive`

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ana araç çubuğunun kaynak KIMLIĞINI serileştirerek temel sınıf uygulamasını ( [CMFCToolBarButton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) genişletir. Arşiv yüklenirken ( [CArchive:: ısyükleme](../../mfc/reference/carchive-class.md#isloading) sıfır dışında bir değer döndürürse), bu yöntem `m_pToolBar` veri üyesini serileştirilmiş kaynak kimliğini içeren araç çubuğuna ayarlar.

##  <a name="setdefaultcommand"></a>CMFCDropDownToolbarButton:: SetDefaultCommand

Bir Kullanıcı düğmeye tıkladığında çerçevenin kullandığı varsayılan komutu ayarlar.

```
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*Uımd*<br/>
'ndaki Varsayılan komutun KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Kullanıcı düğmeyi tıkladığında çerçevenin yürüttüğü varsayılan bir komut belirtmek için bu yöntemi çağırın. *Uııcmd* tarafından BELIRTILEN komut kimlikli bir öğe, üst açılan araç çubuğunda bulunmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar Sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarMenuButton Sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
