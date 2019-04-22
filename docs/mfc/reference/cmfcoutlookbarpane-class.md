---
title: CMFCOutlookBarPane sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
ms.openlocfilehash: b23aa9e30c130cea8c84290b62cc19794376d4c1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773443"
---
# <a name="cmfcoutlookbarpane-class"></a>CMFCOutlookBarPane sınıfı

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

Öğesinden türetilen denetim [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) Outlook çubuğuna eklenebilir ( [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)). Outlook Çubuğu bölmesi büyük düğmeler bir sütun içerir. Bölmeden daha büyük olması durumunda kullanıcı düğme listesinin yukarı ve aşağı kaydırma yapabilir. Kullanıcı bir Outlook Çubuğu bölmesini Outlook çubuğundan ayırdığında kayan veya ana çerçeve penceresine yerleştirilebilir yükleyebilir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCOutlookBarPane : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Varsayılan Oluşturucu.|
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCOutlookBarPane::AddButton](#addbutton)|Outlook Çubuğu bölmesi için bir düğme ekler.|
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|Başka bir bölüm ya da çerçeve penceresi bölmesi yerleştirilmiş olup olmadığını belirler. (Geçersiz kılmaları [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|
|`CMFCOutlookBarPane::CanBeRestored`|Sistem bir araç çubuğunun özgün durumuna özelleştirme sonrasında geri yükleyebilirsiniz olup olmadığını belirler. (Geçersiz kılmaları [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCOutlookBarPane::ClearAll](#clearall)|Outlook Çubuğu bölmesi görüntüleri tarafından kullanılan kaynakları serbest bırakır.|
|[CMFCOutlookBarPane::Create](#create)|Outlook Çubuğu bölmesi oluşturur.|
|`CMFCOutlookBarPane::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|`CMFCOutlookBarPane::Dock`|Outlook Çubuğu bölmesi sabitlemek için framework tarafından çağırılır. (Geçersiz kılmaları `CPane::Dock`.)|
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|Outlook Çubuğu Bölmesi kaydırma oklar düğme listesinin sayfası veya düğme ilerleyin olup olmadığını belirtir.|
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Outlook Çubuğu bölmesi normal (seçili olmayan) metin rengini döndürür.|
|`CMFCOutlookBarPane::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Arka plan görüntüsü için Outlook Çubuğu bölmesi yüklü olup olmadığını belirler.|
|`CMFCOutlookBarPane::IsChangeState`|Bir kayan bölme başlığının yuvalanabilir olup olmadığını belirler. (Geçersiz kılmaları `CPane::IsChangeState`.)|
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Düğme kenarlığı bir düğmesi vurgulanmış ve arka plan görüntüsü görüntülendiğinde gölgeli olup olmadığını belirler.|
|`CMFCOutlookBarPane::OnBeforeFloat`|Kayan nokta bölme hakkında olduğunda framework tarafından çağırılır. (Geçersiz kılmaları [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|Belirtilen komut kimliği olan düğmeyi kaldırır|
|`CMFCOutlookBarPane::RestoreOriginalstate`|Bir araç çubuğunun özgün durumunu geri yükler. (Geçersiz kılmaları [CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Arka plan rengini ayarlar.|
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Arka plan resmini ayarlar.|
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Outlook Çubuğu bölmesi düğmelerinin özgün kümesine sıfırlar.|
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Outlook Çubuğu bölmesi düğmeleri etrafında kullanılan doldurma piksel sayısını ayarlar.|
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Outlook Çubuğu Bölmesi'nde normal ve vurgulanan metin rengini ayarlar.|
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Outlook Çubuğu bölmesi saydam rengini belirler.|
|`CMFCOutlookBarPane::SmartUpdate`|Outlook Çubuğu güncelleştirmek için dahili olarak kullanılır. (Geçersiz kılmaları `CMFCToolBar::SmartUpdate`.)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|Hangi kısayol menü öğelerini özelleştirme modda görüntüleneceğini belirtir.|
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Tüm düğmeleri Outlook Çubuğu Bölmesi'nden kaldırır. (Geçersiz kılmaları [CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|

## <a name="remarks"></a>Açıklamalar

Bir Outlook Çubuğu gerçekleştirme hakkında daha fazla bilgi için bkz. [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

OutlookDemo örnek proje bir Outlook çubuğu örneği için bkz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCOutlookBarPane` sınıfı. Örneğin, bir Outlook Çubuğu bölmesini oluşturmak, sayfa kaydırma modu etkinleştirme, yerleştirme etkinleştirmek ve Outlook çubuğu arka plan rengini ayarlamak gösterilmektedir. Bu kod parçacığı parçasıdır [Outlook çoklu görünümleri örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxoutlookbarpane.h

##  <a name="addbutton"></a>  CMFCOutlookBarPane::AddButton

Outlook Çubuğu bölmesi için bir düğme ekler.

```
BOOL AddButton(
    UINT uiImage,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    UINT uiImage,
    UINT uiLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    LPCTSTR szBmpFileName,
    LPCTSTR szLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HBITMAP hBmp,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HICON hIcon,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1,
    BOOL bAlphaBlend=FALSE);
```

### <a name="parameters"></a>Parametreler

*uiImage*<br/>
[in] Bir bit eşlemi kaynak tanımlayıcısını belirtir.

*lpszLabel*<br/>
[in] Düğmenin metni belirtir.

*iIdCommand*<br/>
[in] Düğme denetiminin kimliğini belirtir.

*iInsertAt*<br/>
[in] Outlook çubuğu sayfasında, düğme eklemek sıfır tabanlı dizinini belirtir.

*uiLabel*<br/>
[in] Bir dize kaynak kimliği

*szBmpFileName*<br/>
[in] Yüklemek için disk görüntü dosyasının adını belirtir.

*szLabel*<br/>
[in] Düğmenin metni belirtir.

*hBmp*<br/>
[in] Bir düğmenin bit eşlem işleyici.

*hIcon*<br/>
[in] Bir düğme simge tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Bir düğme başarıyla eklenmişse TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bir Outlook Çubuğu sayfasına yeni bir düğme eklemek için bu yöntemi kullanın. Düğmenin resim uygulama kaynaklarından veya bir disk dosyasından yüklenebilir.

Sayfa kimliği ile belirtilen *uiPageID* -1 ' dir düğmesine ilk sayfasına eklenir.

Belirtilen dizin *iInsertAt* -1, sayfanın sonunda düğme eklenir.

##  <a name="canbeattached"></a>  CMFCOutlookBarPane::CanBeAttached

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="clearall"></a>  CMFCOutlookBarPane::ClearAll

Outlook Çubuğu bölmesi görüntülerinde tarafından kullanılan kaynakları serbest bırakır.

```
void ClearAll();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem doğrudan çağıran [CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), Outlook Çubuğu bölmesi tarafından kullanılan görüntülerindeki çağrılır.

##  <a name="create"></a>  CMFCOutlookBarPane::Create

Outlook Çubuğu bölmesi oluşturur.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,
    UINT uiID=(UINT)-1,
    DWORD dwControlBarStyle=0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[in] Outlook Çubuğu bölmesi denetiminin üst penceresine belirtir. NULL olmamalıdır.

*dwStyle*<br/>
[in] Pencere stili.  Pencere stilleri bir listesi için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*uiID*<br/>
[in] Denetim kimliği. Etkinleştirmek için benzersiz olması gerekir denetimin durumunu kaydetme.

*dwControlBarStyle*<br/>
[in] Outlook Çubuğu'ndan ayrıldığında, Outlook Çubuğu bölmesi denetimi davranışını tanımlayan özel stilleri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Oluşturmak için bir `CMFCOutlookBarPane` nesne, ilk oluşturucusunu çağırın ve ardından çağrısı `Create`, Outlook Çubuğu bölmesi denetimi oluşturur ve ona ekler `CMFCOutlookBarPane` nesne.

Hakkında daha fazla bilgi için `dwControlBarStyle` bkz [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

##  <a name="enablecontextmenuitems"></a>  CMFCOutlookBarPane::EnableContextMenuItems

Hangi kısayol menü öğelerini özelleştirme modda görüntüleneceğini belirtir.

```
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,
    CMenu* pPopup);
```

### <a name="parameters"></a>Parametreler

*pButton*<br/>
[in] Bir kullanıcının bir araç çubuğu düğmesi için bir işaretçi.

*pPopup*<br/>
[in] Kısayol menüsüne bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Kısayol menüsünde görüntülenen TRUE döndürür; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Özelleştirme modu framework görüntüler framework standart kısayol menüsünü değiştirmek için bu yöntemi yok sayın.

Varsayılan uygulama özelleştirme modunu denetler ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) ve TRUE, devre dışı bırakır tüm kısayol menü öğeleri kümesi ise dışındaki **Sil**. Ardından, giriş parametreleri yalnızca geçirir `CMFCToolBar::EnableContextMenuItems`.

> [!NOTE]
> *Bağlam menüsü* kısayol menüsünü eşanlamlıdır.

##  <a name="enablepagescrollmode"></a>  CMFCOutlookBarPane::EnablePageScrollMode

Outlook Çubuğu Bölmesi kaydırma oklar düğme sayfa sayfa veya düğmesi tarafından düğme listesinin ilerleyin olup olmadığını belirtir.

```
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```

### <a name="parameters"></a>Parametreler

*bPageScroll*<br/>
[in] TRUE ise, sayfa kaydırma modu etkinleştirin. FALSE ise, sayfa kaydırma modu devre dışı bırakın.

##  <a name="getregularcolor"></a>  CMFCOutlookBarPane::GetRegularColor

Normal döndürür (diğer bir deyişle, seçili olmayan) Outlook Çubuğu bölmesi metin rengi.

```
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir RGB renk değeri olarak geçerli metin rengi.

### <a name="remarks"></a>Açıklamalar

Kullanım [CMFCOutlookBarPane::SetTextColor](#settextcolor) Outlook Çubuğu geçerli (normal ve seçili) metin rengini ayarlamak için. Varsayılan metin rengi çağırarak elde edebileceğiniz [GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor) işlevi COLOR_WINDOW dizine sahip.

##  <a name="isbackgroundtexture"></a>  CMFCOutlookBarPane::IsBackgroundTexture

Arka plan görüntüsü için Outlook Çubuğu bölmesi yüklü olup olmadığını belirler.

```
BOOL IsBackgroundTexture() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntülenecek arka plan görüntüsü ise TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Arka plan görüntüsü çağırarak ekleyebileceğiniz [CMFCOutlookBarPane::SetBackImage](#setbackimage) işlevi.

Arka plan görüntü varsa, arka plan kullanılarak belirtilen bir renk ile boyanır [CMFCOutlookBarPane::SetBackColor](#setbackcolor).

##  <a name="isdrawshadedhighlight"></a>  CMFCOutlookBarPane::IsDrawShadedHighlight

Düğme kenarlığı bir düğmesi vurgulanmış ve arka plan görüntüsü görüntülendiğinde gölgeli olup olmadığını belirler.

```
BOOL IsDrawShadedHighlight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin kenarlık gölgeli ise TRUE; Aksi durumda FALSE.

##  <a name="removeallbuttons"></a>  CMFCOutlookBarPane::RemoveAllButtons

Tüm düğmeleri Outlook Çubuğu Bölmesi'nden kaldırır.

```
virtual void RemoveAllButtons();
```

##  <a name="removebutton"></a>  CMFCOutlookBarPane::RemoveButton

Belirtilen komut kimliği olan düğmeyi kaldırır

```
BOOL RemoveButton(UINT iIdCommand);
```

### <a name="parameters"></a>Parametreler

*iIdCommand*<br/>
[in] Kaldırmak için bir düğme komut Kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Düğme başarıyla kaldırıldıysa TRUE; Belirtilen komut kimliği geçerli değilse FALSE.

##  <a name="setbackcolor"></a>  CMFCOutlookBarPane::SetBackColor

Outlook çubuğu arka plan rengini ayarlar.

```
void SetBackColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[in] Yeni arka plan rengini belirtir.

### <a name="remarks"></a>Açıklamalar

Outlook Çubuğu geçerli arka plan rengini ayarlamak için bu işlevi çağırın. Arka plan rengi, yalnızca arka plan görüntü olduğunda kullanılır.

##  <a name="setbackimage"></a>  CMFCOutlookBarPane::SetBackImage

Arka plan resmini ayarlar.

```
void SetBackImage(UINT uiImageID);
```

### <a name="parameters"></a>Parametreler

*uiImageID*<br/>
[in] Görüntü kaynak kimliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Outlook ayarlamak için bu yöntemi çağırın çubuğunun arka plan resmi. Arka plan görüntüleri listesi yönetilen katıştırılmış tarafından [Cmfctoolbarımages sınıfı](../../mfc/reference/cmfctoolbarimages-class.md) nesne.

##  <a name="setdefaultstate"></a>  CMFCOutlookBarPane::SetDefaultState

Outlook Çubuğu bölmesi düğmelerinin özgün kümesine sıfırlar.

```
void SetDefaultState();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, özgün kümesine Outlook çubuğu düğmelerinin geri yükler. Bu yöntem benzer `CMFCOutlookBarPane::RestoreOriginalstate`dışında bir Outlook Çubuğu bölmesinin güncellenmediğini tetiklemez.

##  <a name="setextraspace"></a>  CMFCOutlookBarPane::SetExtraSpace

Outlook Çubuğu bölmesi düğmeleri etrafında kullanılan doldurma piksel sayısını ayarlar.

```
void SetExtraSpace()
```

##  <a name="settextcolor"></a>  CMFCOutlookBarPane::SetTextColor

Outlook Çubuğu Bölmesi'nde normal ve vurgulanan metin rengini ayarlar.

```
void SetTextColor(
    COLORREF clrRegText,
    COLORREF clrSelText=0);
```

### <a name="parameters"></a>Parametreler

*clrRegText*<br/>
[in] Yeni seçili olmayan metin rengini belirtir.

*clrSelText*<br/>
[in] Seçili metin için yeni rengini belirtir.

##  <a name="settransparentcolor"></a>  CMFCOutlookBarPane::SetTransparentColor

Outlook Çubuğu bölmesi saydam rengini belirler.

```
void SetTransparentColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Yeni saydam rengini belirtir.

### <a name="remarks"></a>Açıklamalar

Saydam rengi saydam görüntüler için gereklidir. Tüm bu renk görüntünün tekrarını arka plan rengiyle yerine boyanır.  Hiç arka plan ve ön plan görüntülerini karışım yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarTabCtrl Sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
