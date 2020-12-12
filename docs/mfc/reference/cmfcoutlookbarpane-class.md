---
description: 'Daha fazla bilgi edinin: CMFCOutlookBarPane sınıfı'
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
ms.openlocfilehash: f1bcae298a9541920f6deeb9a3bce22e49222cb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265031"
---
# <a name="cmfcoutlookbarpane-class"></a>CMFCOutlookBarPane sınıfı

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

Bir Outlook çubuğuna eklenebilen [CMFCToolBar sınıfından](../../mfc/reference/cmfctoolbar-class.md) türetilmiş bir denetim ( [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)). Outlook çubuğu bölmesi, büyük düğmelerden oluşan bir sütun içerir. Kullanıcı, bölmeden daha büyükse düğme listesini yukarı ve aşağı kaydırabilirler. Kullanıcı Outlook çubuğu 'ndaki bir Outlook çubuğu bölmesini ayrıldığında, ana çerçeve penceresinde taşınabilir veya yuvaya yerleştirebilirsiniz.

## <a name="syntax"></a>Syntax

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
|[CMFCOutlookBarPane:: AddButton](#addbutton)|Outlook çubuğu bölmesine bir düğme ekler.|
|[CMFCOutlookBarPane:: Canbeekli](#canbeattached)|Bölmenin başka bir bölmeye veya çerçeve penceresine sabitlenebilir olup olmayacağını belirler. ( [CBasePane:: Canbeekli](../../mfc/reference/cbasepane-class.md#canbeattached)geçersiz kılar.)|
|`CMFCOutlookBarPane::CanBeRestored`|Sistemin özelleştirmeden sonra bir araç çubuğunu özgün durumuna geri yükleyip yükleyemeyeceğini belirler. ( [CMFCToolBar:: Canberesrimi](../../mfc/reference/cmfctoolbar-class.md#canberestored)geçersiz kılar.)|
|[CMFCOutlookBarPane:: ClearAll](#clearall)|Outlook çubuğu bölmesindeki görüntüler tarafından kullanılan kaynakları serbest bırakır.|
|[CMFCOutlookBarPane:: Create](#create)|Outlook çubuğu bölmesini oluşturur.|
|`CMFCOutlookBarPane::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CMFCOutlookBarPane::Dock`|Outlook çubuğu bölmesini yerleştirmek için Framework tarafından çağırılır. (Geçersiz kılmalar `CPane::Dock` .)|
|[CMFCOutlookBarPane:: EnablePageScrollMode](#enablepagescrollmode)|Outlook çubuğu bölmesindeki Kaydırma oklarının sayfa veya düğme listesine göre mi ilerlemediğini belirtir.|
|[CMFCOutlookBarPane:: GetRegularColor](#getregularcolor)|Outlook çubuğu bölmesinin normal (seçili olmayan) metin rengini döndürür.|
|`CMFCOutlookBarPane::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCOutlookBarPane:: ısbackgroundtexture](#isbackgroundtexture)|Outlook çubuğu bölmesi için bir arka plan resminin yüklenmiş olup olmadığını belirler.|
|`CMFCOutlookBarPane::IsChangeState`|Bir kayan bölmenin yerleştirilmiş olup olmadığını belirler. (Geçersiz kılmalar `CPane::IsChangeState` .)|
|[CMFCOutlookBarPane:: ısdrawshadedhighlight](#isdrawshadedhighlight)|Bir düğme vurgulandığında ve bir arka plan görüntüsü görüntülenirken düğme kenarlığının gölgeli olup olmayacağını belirler.|
|`CMFCOutlookBarPane::OnBeforeFloat`|Bir bölme, kaydırma yapmak üzereyken Framework tarafından çağırılır. ( [CPane:: OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat)geçersiz kılınır)|
|[CMFCOutlookBarPane:: RemoveButton](#removebutton)|Belirtilen komut KIMLIĞINE sahip olan düğmeyi kaldırır.|
|`CMFCOutlookBarPane::RestoreOriginalstate`|Bir araç çubuğunun özgün durumunu geri yükler. ( [CMFCToolBar:: RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).) öğesini geçersiz kılar|
|[CMFCOutlookBarPane:: SetBackColor](#setbackcolor)|Arka plan rengini ayarlar.|
|[CMFCOutlookBarPane:: SetBackImage](#setbackimage)|Arka plan resmini ayarlar.|
|[CMFCOutlookBarPane:: SetDefaultState](#setdefaultstate)|Outlook çubuğu bölmesini orijinal düğme kümesine sıfırlar.|
|[CMFCOutlookBarPane:: SetExtraSpace](#setextraspace)|Outlook çubuğu bölmesindeki düğmelerin etrafında kullanılan doldurma piksel sayısını belirler.|
|[CMFCOutlookBarPane:: SetTextColor](#settextcolor)|Outlook çubuğu bölmesinde normal ve vurgulanmış metnin renklerini ayarlar.|
|[CMFCOutlookBarPane:: SetTransparentColor](#settransparentcolor)|Outlook çubuğu bölmesinin saydam rengini ayarlar.|
|`CMFCOutlookBarPane::SmartUpdate`|Outlook çubuğunu güncelleştirmek için dahili olarak kullanılır. (Geçersiz kılmalar `CMFCToolBar::SmartUpdate` .)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCOutlookBarPane:: EnableContextMenuItems](#enablecontextmenuitems)|Özelleştirme modunda hangi kısayol menüsü öğelerinin görüntülendiğini belirtir.|
|[CMFCOutlookBarPane:: RemoveAllButtons](#removeallbuttons)|Tüm düğmeleri Outlook Çubuğu bölmesinden kaldırır. ( [CMFCToolBar:: Removealldüğmelerini](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

Outlook çubuğunun nasıl uygulanacağı hakkında daha fazla bilgi için bkz. [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

Outlook çubuğu örneği için, bkz. OutlookDemo örnek projesi.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, sınıfının çeşitli yöntemlerinin nasıl kullanılacağı gösterilmektedir `CMFCOutlookBarPane` . Örnek olarak, Outlook çubuğu bölmesinin nasıl oluşturulacağı, sayfa kaydırma modunun nasıl etkinleştirileceği, yerleştirmeyi etkinleştirileceği ve Outlook çubuğunun arka plan rengi nasıl ayarlanacağı gösterilmektedir. Bu kod parçacığı [Outlook çok görünümleri örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

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

**Üstbilgi:** afxoutlookbarpane. h

## <a name="cmfcoutlookbarpaneaddbutton"></a><a name="addbutton"></a> CMFCOutlookBarPane:: AddButton

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

*Uıımage*<br/>
'ndaki Bit eşlemin kaynak tanımlayıcısını belirtir.

*lpszLabel*<br/>
'ndaki Düğme metnini belirtir.

*ııdcommand*<br/>
'ndaki Düğme denetiminin KIMLIĞINI belirtir.

*ıınsertat*<br/>
'ndaki Outlook çubuğu sayfasında düğmenin ekleneceği sıfır tabanlı dizini belirtir.

*uiLabel*<br/>
'ndaki Bir dize kaynak KIMLIĞI.

*szBmpFileName*<br/>
'ndaki Yüklenecek disk görüntüsü dosyasının adını belirtir.

*szLabel*<br/>
'ndaki Düğme metnini belirtir.

*hBmp*<br/>
'ndaki Düğmenin bit eşlem tanıtıcısı.

*HICON*<br/>
'ndaki Düğmelerin simgesine yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Bir düğme başarıyla eklendiyse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Outlook Çubuğu sayfasına yeni bir düğme eklemek için bu yöntemi kullanın. Düğmenin görüntüsü uygulama kaynaklarından veya bir disk dosyasından yüklenebilir.

*Uııpageıd* tarafından BELIRTILEN sayfa kimliği-1 ise, düğme ilk sayfaya eklenir.

*Iınsertat* tarafından belirtilen dizin-1 ise, düğme sayfanın sonuna eklenir.

## <a name="cmfcoutlookbarpanecanbeattached"></a><a name="canbeattached"></a> CMFCOutlookBarPane:: Canbeekli

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcoutlookbarpaneclearall"></a><a name="clearall"></a> CMFCOutlookBarPane:: ClearAll

Outlook çubuğu bölmesindeki görüntüler tarafından kullanılan kaynakları serbest bırakır.

```cpp
void ClearAll();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Outlook çubuğu bölmesi tarafından kullanılan görüntülerde çağrılan [CMFCToolBarImages:: Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear)öğesini doğrudan çağırır.

## <a name="cmfcoutlookbarpanecreate"></a><a name="create"></a> CMFCOutlookBarPane:: Create

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
'ndaki Outlook çubuğu bölmesi denetiminin üst penceresini belirtir. NULL olmamalıdır.

*dwStyle*<br/>
'ndaki Pencere stili.  Pencere stillerinin listesi için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*Uııd*<br/>
'ndaki Denetim KIMLIĞI. Denetimin durumunun kaydedilmesini etkinleştirmek için benzersiz olmalıdır.

*dwControlBarStyle*<br/>
'ndaki Outlook çubuğu 'ndan ayrıldığında Outlook çubuğu bölmesi denetiminin davranışını tanımlayan özel stilleri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturmak için `CMFCOutlookBarPane` , önce oluşturucuyu çağırın ve sonra `Create` Outlook çubuğu bölmesi denetimini oluşturan ve bunu nesnesine ekleyen çağırın `CMFCOutlookBarPane` .

Daha fazla bilgi için `dwControlBarStyle` bkz. [CBasePane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex).

## <a name="cmfcoutlookbarpaneenablecontextmenuitems"></a><a name="enablecontextmenuitems"></a> CMFCOutlookBarPane:: EnableContextMenuItems

Özelleştirme modunda hangi kısayol menüsü öğelerinin görüntülendiğini belirtir.

```
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,
    CMenu* pPopup);
```

### <a name="parameters"></a>Parametreler

*pButton*<br/>
'ndaki Kullanıcının tıkladığını bir araç çubuğu düğmesine yönelik işaretçi.

*pPopup*<br/>
'ndaki Kısayol menüsüne yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Kısayol menüsünün görüntülenmesi gerekiyorsa, TRUE döndürür; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Framework 'ün özelleştirme modunda görüntülediği çerçeve standart kısayol menüsünü değiştirmek için bu yöntemi geçersiz kılın.

Varsayılan uygulama özelleştirme modunu denetler ( [CMFCToolBar:: IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) ve true olarak ayarlanırsa, **Sil** dışındaki tüm kısayol menü öğelerini devre dışı bırakır. Daha sonra, yalnızca giriş parametrelerini öğesine geçirir `CMFCToolBar::EnableContextMenuItems` .

> [!NOTE]
> *Bağlam menüsü* , kısayol menüsü için bir eş anlamlı.

## <a name="cmfcoutlookbarpaneenablepagescrollmode"></a><a name="enablepagescrollmode"></a> CMFCOutlookBarPane:: EnablePageScrollMode

Outlook çubuğu bölmesindeki Kaydırma oklarının, düğme sayfası veya düğme ölçütü düğme listesine mi ilerlemediğini belirtir.

```cpp
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```

### <a name="parameters"></a>Parametreler

*bPageScroll*<br/>
'ndaki DOĞRU ise sayfa kaydırma modunu etkinleştirin. YANLıŞSA, sayfa kaydırma modunu devre dışı bırakın.

## <a name="cmfcoutlookbarpanegetregularcolor"></a><a name="getregularcolor"></a> CMFCOutlookBarPane:: GetRegularColor

Outlook çubuğu bölmesinin normal (seçili olmayan) metin rengini döndürür.

```
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir RGB renk değeri olarak geçerli metin rengi.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğunun geçerli (normal ve seçili) metin rengini ayarlamak için [CMFCOutlookBarPane:: SetTextColor](#settextcolor) komutunu kullanın. [Getsysccolor](/windows/win32/api/winuser/nf-winuser-getsyscolor) işlevini COLOR_WINDOW diziniyle çağırarak varsayılan metin rengini elde edebilirsiniz.

## <a name="cmfcoutlookbarpaneisbackgroundtexture"></a><a name="isbackgroundtexture"></a> CMFCOutlookBarPane:: ısbackgroundtexture

Outlook çubuğu bölmesi için bir arka plan resminin yüklenmiş olup olmadığını belirler.

```
BOOL IsBackgroundTexture() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntülenecek arka plan resmi varsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

[CMFCOutlookBarPane:: SetBackImage](#setbackimage) işlevini çağırarak bir arka plan görüntüsü ekleyebilirsiniz.

Arka plan görüntüsü yoksa, arka plan [CMFCOutlookBarPane:: SetBackColor](#setbackcolor)kullanılarak belirtilen renkle boyanmıştır.

## <a name="cmfcoutlookbarpaneisdrawshadedhighlight"></a><a name="isdrawshadedhighlight"></a> CMFCOutlookBarPane:: ısdrawshadedhighlight

Bir düğme vurgulandığında ve bir arka plan görüntüsü görüntülenirken düğme kenarlığının gölgeli olup olmayacağını belirler.

```
BOOL IsDrawShadedHighlight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin kenarlıkları gölgeliyse doğru; Aksi halde yanlış.

## <a name="cmfcoutlookbarpaneremoveallbuttons"></a><a name="removeallbuttons"></a> CMFCOutlookBarPane:: RemoveAllButtons

Tüm düğmeleri Outlook Çubuğu bölmesinden kaldırır.

```
virtual void RemoveAllButtons();
```

## <a name="cmfcoutlookbarpaneremovebutton"></a><a name="removebutton"></a> CMFCOutlookBarPane:: RemoveButton

Belirtilen komut KIMLIĞINE sahip olan düğmeyi kaldırır.

```
BOOL RemoveButton(UINT iIdCommand);
```

### <a name="parameters"></a>Parametreler

*ııdcommand*<br/>
'ndaki Kaldırılacak düğmenin komut KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Düğme başarıyla kaldırıldıysa doğru; Belirtilen komut KIMLIĞI geçerli değilse FALSE.

## <a name="cmfcoutlookbarpanesetbackcolor"></a><a name="setbackcolor"></a> CMFCOutlookBarPane:: SetBackColor

Outlook çubuğunun arka plan rengini ayarlar.

```cpp
void SetBackColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Yeni arka plan rengini belirtir.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğu için geçerli arka plan rengini ayarlamak için bu işlevi çağırın. Arka plan rengi, yalnızca arka plan görüntüsü olmadığında kullanılır.

## <a name="cmfcoutlookbarpanesetbackimage"></a><a name="setbackimage"></a> CMFCOutlookBarPane:: SetBackImage

Arka plan resmini ayarlar.

```cpp
void SetBackImage(UINT uiImageID);
```

### <a name="parameters"></a>Parametreler

*Uıımageıd*<br/>
'ndaki Görüntü kaynak KIMLIĞINI belirtir.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğunun arka plan görüntüsünü ayarlamak için bu yöntemi çağırın. Arka plan görüntülerinin listesi, katıştırılmış [CMFCToolBarImages sınıfı](../../mfc/reference/cmfctoolbarimages-class.md) nesnesi tarafından yönetilir.

## <a name="cmfcoutlookbarpanesetdefaultstate"></a><a name="setdefaultstate"></a> CMFCOutlookBarPane:: SetDefaultState

Outlook çubuğu bölmesini orijinal düğme kümesine sıfırlar.

```cpp
void SetDefaultState();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Outlook çubuğu düğmelerini orijinal kümesine geri yükler. Bu yöntem `CMFCOutlookBarPane::RestoreOriginalstate` , Outlook çubuğu bölmesinin bir yeniden çizmesinin tetiklenmesi dışında, gibidir.

## <a name="cmfcoutlookbarpanesetextraspace"></a><a name="setextraspace"></a> CMFCOutlookBarPane:: SetExtraSpace

Outlook çubuğu bölmesindeki düğmelerin etrafında kullanılan doldurma piksel sayısını belirler.

```cpp
void SetExtraSpace()
```

## <a name="cmfcoutlookbarpanesettextcolor"></a><a name="settextcolor"></a> CMFCOutlookBarPane:: SetTextColor

Outlook çubuğu bölmesinde normal ve vurgulanmış metnin renklerini ayarlar.

```cpp
void SetTextColor(
    COLORREF clrRegText,
    COLORREF clrSelText=0);
```

### <a name="parameters"></a>Parametreler

*clrRegText*<br/>
'ndaki Seçili olmayan metnin yeni rengini belirtir.

*clrSelText*<br/>
'ndaki Seçilen metnin yeni rengini belirtir.

## <a name="cmfcoutlookbarpanesettransparentcolor"></a><a name="settransparentcolor"></a> CMFCOutlookBarPane:: SetTransparentColor

Outlook çubuğu bölmesinin saydam rengini ayarlar.

```cpp
void SetTransparentColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Yeni saydam rengi belirtir.

### <a name="remarks"></a>Açıklamalar

Saydam görüntüleri göstermek için saydam renk gereklidir. Bu rengin bir görüntüde herhangi bir oluşumu, bunun yerine arka plan rengiyle boyanmıştır.  Arka plan ve ön plan görüntülerinin karışımı yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarTabCtrl sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
