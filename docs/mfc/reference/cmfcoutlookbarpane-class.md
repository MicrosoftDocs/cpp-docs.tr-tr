---
title: CMFCOutlookBarPane Sınıfı
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
ms.openlocfilehash: 97c7edde26bdf13e899d823dcf88d143068d86a4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749612"
---
# <a name="cmfcoutlookbarpane-class"></a>CMFCOutlookBarPane Sınıfı

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

[CmFCToolBar Class'tan](../../mfc/reference/cmfctoolbar-class.md) türetilen ve Outlook çubuğuna [(CMFCOutlookBar Sınıfı)](../../mfc/reference/cmfcoutlookbar-class.md)eklenebilen bir denetim. Outlook çubuğu bölmesi büyük düğmelerden oluşan bir sütun içerir. Kullanıcı, bölmeden daha büyükse düğmeler listesini yukarı ve aşağı kaydırabilir. Kullanıcı Outlook çubuğundan bir Outlook çubuğu bölmesini ayırdığında, ana çerçeve penceresinde yüzebilir veya sabitlenebilir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCOutlookBarPane : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Varsayılan oluşturucu.|
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCOutlookBarPane::Ekle Düğmesi](#addbutton)|Outlook çubuğu bölmesine bir düğme ekler.|
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|Bölmenin başka bir bölmeye veya çerçeve penceresine sabitlenip yapıştırılamayacağını belirler. (Geçersiz Kılar [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|
|`CMFCOutlookBarPane::CanBeRestored`|Sistemin özelleştirmeden sonra bir araç çubuğunu özgün durumuna geri yükleyip geri yükleyemeyeceğini belirler. [(CmFCToolBar geçersiz kılar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCOutlookBarPane::ClearAll](#clearall)|Outlook çubuğu bölmesindeki resimler tarafından kullanılan kaynakları boşaltıyor.|
|[CMFCOutlookBarPane::Oluştur](#create)|Outlook çubuğu bölmesini oluşturur.|
|`CMFCOutlookBarPane::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CMFCOutlookBarPane::Dock`|Outlook çubuğu bölmesini yapıştırmak için çerçeve tarafından çağrılır. (Geçersiz `CPane::Dock`kılar .)|
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|Outlook çubuğu bölmesindeki kaydırma oklarının düğmeler listesini sayfa ya da düğmeyle ilerletip ilerletmediğini belirtir.|
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Outlook çubuğu bölmesinin normal (seçilmemiş) metin rengini verir.|
|`CMFCOutlookBarPane::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Outlook çubuğu bölmesi için yüklenmiş bir arka plan görüntüsü olup olmadığını belirler.|
|`CMFCOutlookBarPane::IsChangeState`|Kayan bölmenin kenetlenip kenetlenmeyeceğini belirler. (Geçersiz `CPane::IsChangeState`kılar .)|
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Bir düğme vurgulandığında ve arka plan görüntüsü görüntülendiğinde düğme kenarlığı gölgelendimi belirler.|
|`CMFCOutlookBarPane::OnBeforeFloat`|Bir bölme yüzmek üzereyken çerçeve tarafından çağrılır. [(Overrides CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|
|[CMFCOutlookBarPane::Düğmeyi Kaldır](#removebutton)|Belirtilen komut kimliğine sahip düğmeyi kaldırır.|
|`CMFCOutlookBarPane::RestoreOriginalstate`|Bir araç çubuğunun özgün durumunu geri yükler. [(CMFCToolBar geçersiz kılar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Arka plan rengini ayarlar.|
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Arka plan görüntüsünü ayarlar.|
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Outlook çubuğu bölmesini özgün düğme kümesine sıfırlar.|
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Outlook çubuğu bölmesindeki düğmelerin etrafında kullanılan dolgu pikselsayısını ayarlar.|
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Outlook çubuğu bölmesinde normal ve vurgulanan metnin renklerini ayarlar.|
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Outlook çubuğu bölmesi için saydam rengi ayarlar.|
|`CMFCOutlookBarPane::SmartUpdate`|Outlook çubuğunu güncelleştirmek için dahili olarak kullanılır. (Geçersiz `CMFCToolBar::SmartUpdate`kılar .)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|Özelleştirme modunda hangi kısayol menü öğelerinin görüntüleneceğini belirtir.|
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Outlook çubuğu bölmesinden tüm düğmeleri kaldırır. [(CMFCToolBar geçersiz kılar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|

## <a name="remarks"></a>Açıklamalar

Outlook çubuğunun nasıl uygulanacağı hakkında bilgi için [CMFCOutlookBar Sınıfı'na](../../mfc/reference/cmfcoutlookbar-class.md)bakın.

Outlook çubuğu örneği için OutlookDemo örnek projesine bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın çeşitli yöntemlerinin `CMFCOutlookBarPane` nasıl kullanılacağını göstermektedir. Örnek, Outlook çubuğu bölmesinin nasıl oluşturulacağı, sayfa kaydırma modunu etkinleştirmen, yerleştirmeyi nasıl etkinleştirilir ve Outlook çubuğunun arka plan rengini nasıl ayarlanacağını gösterir. Bu kod parçacığı Outlook Çok [Görünümler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[Cmfctoolbar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxoutlookbarpane.h

## <a name="cmfcoutlookbarpaneaddbutton"></a><a name="addbutton"></a>CMFCOutlookBarPane::Ekle Düğmesi

Outlook çubuğu bölmesine bir düğme ekler.

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
[içinde] Bitmap'in kaynak tanımlayıcısını belirtir.

*lpszEtiket*<br/>
[içinde] Düğmenin metnini belirtir.

*iIdCommand*<br/>
[içinde] Düğme denetiminin kimliğini belirtir.

*iInsertAt*<br/>
[içinde] Düğmeyi eklemek için outlook çubuğunun sayfasındasıfır tabanlı dizini belirtir.

*uiLabel*<br/>
[içinde] Dize kaynak kimliği.

*szBmpFileName*<br/>
[içinde] Yüklenmesi gereken disk görüntü dosyasının adını belirtir.

*szEtiket*<br/>
[içinde] Düğmenin metnini belirtir.

*hBmp*<br/>
[içinde] Düğmenin bit haritasına bir tutamaç.

*Hıcon*<br/>
[içinde] Düğmesimgesine bir tutamaç.

### <a name="return-value"></a>Dönüş Değeri

Bir düğme başarıyla eklendiyse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğunun sayfasına yeni bir düğme eklemek için bu yöntemi kullanın. Düğmenin görüntüsü uygulama kaynaklarından veya bir disk dosyasından yüklenebilir.

*uiPageID* tarafından belirtilen sayfa kimliği -1 ise, düğme ilk sayfaya eklenir.

*iInsertAt* tarafından belirtilen dizin -1 ise, sayfanın sonuna düğme eklenir.

## <a name="cmfcoutlookbarpanecanbeattached"></a><a name="canbeattached"></a>CMFCOutlookBarPane::CanBeAttached

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcoutlookbarpaneclearall"></a><a name="clearall"></a>CMFCOutlookBarPane::ClearAll

Outlook çubuğu bölmesindeki resimler tarafından kullanılan kaynakları boşaltıyor.

```cpp
void ClearAll();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem doğrudan [CMFCToolBarImages çağırır::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), Outlook çubuğu bölmesi tarafından kullanılan görüntülerde denir.

## <a name="cmfcoutlookbarpanecreate"></a><a name="create"></a>CMFCOutlookBarPane::Oluştur

Outlook çubuğu bölmesini oluşturur.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,
    UINT uiID=(UINT)-1,
    DWORD dwControlBarStyle=0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[içinde] Outlook çubuğu bölmesi denetiminin üst penceresini belirtir. NULL olmamalıdır.

*Dwstyle*<br/>
[içinde] Pencere stili.  Pencere stilleri listesi için [Bkz. Pencere Stilleri.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*uiID*<br/>
[içinde] Kontrol kimliği. Denetim durumunun kaydedilmesini sağlamak için benzersiz olmalıdır.

*dwControlBarStyle*<br/>
[içinde] Outlook çubuğundan ayrıldığında Outlook çubuğu bölme denetiminin davranışını tanımlayan özel stilleri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCOutlookBarPane` nesne oluşturmak için önce oluşturucuyu `Create`çağırın ve ardından Outlook çubuğu bölme denetimini `CMFCOutlookBarPane` oluşturan ve nesneye iliştiren " sözcük" deyin.

CBasePane `dwControlBarStyle` hakkında daha fazla bilgi [için:CreateEx](../../mfc/reference/cbasepane-class.md#createex).

## <a name="cmfcoutlookbarpaneenablecontextmenuitems"></a><a name="enablecontextmenuitems"></a>CMFCOutlookBarPane::EnableContextMenuItems

Özelleştirme modunda hangi kısayol menü öğelerinin görüntüleneceğini belirtir.

```
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,
    CMenu* pPopup);
```

### <a name="parameters"></a>Parametreler

*pDüğme*<br/>
[içinde] Kullanıcının tıklatdığı araç çubuğu düğmesine işaretçi.

*pPopup*<br/>
[içinde] Kısayol menüsüne işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Kısayol menüsü görüntülenecekse TRUE döndürür; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Çerçevenin özelleştirme modunda görüntülemesi çerçeve standart kısayol menüsünü değiştirmek için bu yöntemi geçersiz kılın.

Varsayılan uygulama özelleştirme modunu denetler ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) ve TRUE olarak ayarlanmışsa, Sil hariç tüm kısayol menü öğelerini devre dışı **kılabilir.** Sonra, sadece giriş parametrelerini `CMFCToolBar::EnableContextMenuItems`geçer .

> [!NOTE]
> *Bağlam menüsü* kısayol menüsü için eşanlamlıdır.

## <a name="cmfcoutlookbarpaneenablepagescrollmode"></a><a name="enablepagescrollmode"></a>CMFCOutlookBarPane::EnablePageScrollMode

Outlook çubuğu bölmesindeki kaydırma oklarının düğmeler listesini sayfa sayfa mı yoksa düğmeyle mi ilerletmeyeceğini belirtir.

```cpp
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```

### <a name="parameters"></a>Parametreler

*bPageScroll*<br/>
[içinde] TRUE ise, sayfa kaydırma modunu etkinleştirin. FALSE ise, sayfa kaydırma modunu devre dışı bırak.

## <a name="cmfcoutlookbarpanegetregularcolor"></a><a name="getregularcolor"></a>CMFCOutlookBarPane::GetRegularColor

Outlook çubuğu bölmesinin normal (yani seçili olmayan) metin rengini verir.

```
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

RGB renk değeri olarak geçerli metin rengi.

### <a name="remarks"></a>Açıklamalar

[CmFCOutlookBarPane::Outlook](#settextcolor) çubuğunun geçerli (normal ve seçili) metin rengini ayarlamak için SetTextColor'ı kullanın. COLOR_WINDOW dizini ile [GetSysColor](/windows/win32/api/winuser/nf-winuser-getsyscolor) işlevini arayarak varsayılan metin rengini elde edebilirsiniz.

## <a name="cmfcoutlookbarpaneisbackgroundtexture"></a><a name="isbackgroundtexture"></a>CMFCOutlookBarPane::IsBackgroundTexture

Outlook çubuğu bölmesi için yüklenmiş bir arka plan görüntüsü olup olmadığını belirler.

```
BOOL IsBackgroundTexture() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntülenecek arka plan görüntüsü varsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

[CMFCOutlookBarPane::SetBackImage](#setbackimage) işlevini arayarak arka plan görüntüsü ekleyebilirsiniz.

Arka plan görüntüsü yoksa, arka plan [CMFCOutlookBarPane::SetBackColor](#setbackcolor)kullanılarak belirtilen bir renkle boyanır.

## <a name="cmfcoutlookbarpaneisdrawshadedhighlight"></a><a name="isdrawshadedhighlight"></a>CMFCOutlookBarPane::IsDrawShadedHighlight

Bir düğme vurgulandığında ve arka plan görüntüsü görüntülendiğinde düğme kenarlığı gölgelendimi belirler.

```
BOOL IsDrawShadedHighlight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin kenarlıkları gölgelenmişse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cmfcoutlookbarpaneremoveallbuttons"></a><a name="removeallbuttons"></a>CMFCOutlookBarPane::RemoveAllButtons

Outlook çubuğu bölmesinden tüm düğmeleri kaldırır.

```
virtual void RemoveAllButtons();
```

## <a name="cmfcoutlookbarpaneremovebutton"></a><a name="removebutton"></a>CMFCOutlookBarPane::Düğmeyi Kaldır

Belirtilen komut kimliğine sahip düğmeyi kaldırır.

```
BOOL RemoveButton(UINT iIdCommand);
```

### <a name="parameters"></a>Parametreler

*iIdCommand*<br/>
[içinde] Kaldırılacak bir düğmenin komut kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Düğme başarıyla kaldırıldıysa TRUE; Belirtilen komut kimliği geçerli değilse FALSE.

## <a name="cmfcoutlookbarpanesetbackcolor"></a><a name="setbackcolor"></a>CMFCOutlookBarPane::SetBackColor

Outlook çubuğunun arka plan rengini ayarlar.

```cpp
void SetBackColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] Yeni arka plan rengini belirtir.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğunun geçerli arka plan rengini ayarlamak için bu işlevi arayın. Arka plan rengi yalnızca arka plan görüntüsü yoksa kullanılır.

## <a name="cmfcoutlookbarpanesetbackimage"></a><a name="setbackimage"></a>CMFCOutlookBarPane::SetBackImage

Arka plan görüntüsünü ayarlar.

```cpp
void SetBackImage(UINT uiImageID);
```

### <a name="parameters"></a>Parametreler

*uiImageID*<br/>
[içinde] Görüntü kaynağı kimliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğunun arka plan görüntüsünü ayarlamak için bu yöntemi arayın. Arka plan görüntüleri listesi gömülü [CMFCToolBarImages Sınıf](../../mfc/reference/cmfctoolbarimages-class.md) nesnesi tarafından yönetilir.

## <a name="cmfcoutlookbarpanesetdefaultstate"></a><a name="setdefaultstate"></a>CMFCOutlookBarPane::SetDefaultState

Outlook çubuğu bölmesini özgün düğme kümesine sıfırlar.

```cpp
void SetDefaultState();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Outlook çubuğu düğmelerini özgün kümeye geri yükler. Bu yöntem, `CMFCOutlookBarPane::RestoreOriginalstate`Outlook çubuğu bölmesinin yeniden çizini tetiklemediği dışında, aşağıdaki gibidir.

## <a name="cmfcoutlookbarpanesetextraspace"></a><a name="setextraspace"></a>CMFCOutlookBarPane::SetExtraSpace

Outlook çubuğu bölmesindeki düğmelerin etrafında kullanılan dolgu pikselsayısını ayarlar.

```cpp
void SetExtraSpace()
```

## <a name="cmfcoutlookbarpanesettextcolor"></a><a name="settextcolor"></a>CMFCOutlookBarPane::SetTextColor

Outlook çubuğu bölmesinde normal ve vurgulanan metnin renklerini ayarlar.

```cpp
void SetTextColor(
    COLORREF clrRegText,
    COLORREF clrSelText=0);
```

### <a name="parameters"></a>Parametreler

*clrRegText*<br/>
[içinde] Seçili olmayan metin için yeni rengi belirtir.

*clrSelText*<br/>
[içinde] Seçili metin için yeni rengi belirtir.

## <a name="cmfcoutlookbarpanesettransparentcolor"></a><a name="settransparentcolor"></a>CMFCOutlookBarPane::SetTransparentColor

Outlook çubuğu bölmesi için saydam rengi ayarlar.

```cpp
void SetTransparentColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
Yeni saydam rengi belirtir.

### <a name="remarks"></a>Açıklamalar

Saydam görüntüleri görüntülemek için saydam renk gereklidir. Görüntüdeki bu rengin herhangi bir oluşumu, bunun yerine arka plan rengiyle boyanır.  Arka plan ve ön plan görüntülerinin harmanlanması yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarTabCtrl Sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
