---
description: 'Daha fazla bilgi edinin: CMFCAutoHideButton sınıfı'
title: CMFCAutoHideButton sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
helpviewer_keywords:
- CMFCAutoHideButton [MFC], BringToTop
- CMFCAutoHideButton [MFC], Create
- CMFCAutoHideButton [MFC], GetAlignment
- CMFCAutoHideButton [MFC], GetAutoHideWindow
- CMFCAutoHideButton [MFC], GetParentToolBar
- CMFCAutoHideButton [MFC], GetRect
- CMFCAutoHideButton [MFC], GetSize
- CMFCAutoHideButton [MFC], GetTextSize
- CMFCAutoHideButton [MFC], HighlightButton
- CMFCAutoHideButton [MFC], IsActive
- CMFCAutoHideButton [MFC], IsHighlighted
- CMFCAutoHideButton [MFC], IsHorizontal
- CMFCAutoHideButton [MFC], IsTop
- CMFCAutoHideButton [MFC], IsVisible
- CMFCAutoHideButton [MFC], Move
- CMFCAutoHideButton [MFC], OnDraw
- CMFCAutoHideButton [MFC], OnDrawBorder
- CMFCAutoHideButton [MFC], OnFillBackground
- CMFCAutoHideButton [MFC], ReplacePane
- CMFCAutoHideButton [MFC], ShowAttachedWindow
- CMFCAutoHideButton [MFC], ShowButton
- CMFCAutoHideButton [MFC], UnSetAutoHideMode
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
ms.openlocfilehash: 9d100417193ea8a757b02b9cc8fad0cdedf668f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336577"
---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton sınıfı

Gizleyecek şekilde yapılandırılmış bir [CDockablePane sınıfını](../../mfc/reference/cdockablepane-class.md) görüntüleyen veya gizleyen düğme.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAutoHideButton:: BringToTop](#bringtotop)||
|[CMFCAutoHideButton:: Create](#create)|Otomatik gizleme düğmesini oluşturur ve başlatır.|
|[CMFCAutoHideButton:: Gethizalaması](#getalignment)|Otomatik Gizle düğmesinin hizalamasını alır.|
|[CMFCAutoHideButton:: GetAutoHideWindow](#getautohidewindow)|Otomatik Gizle düğmesiyle ilişkili [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesini döndürür.|
|[CMFCAutoHideButton:: GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton:: GetRect](#getrect)||
|[CMFCAutoHideButton:: GetSize](#getsize)|Otomatik Gizle düğmesinin boyutunu belirler.|
|[CMFCAutoHideButton:: GetTextSize](#gettextsize)|Otomatik Gizle düğmesi için metin etiketinin boyutunu döndürür.|
|[CMFCAutoHideButton:: HighlightButton](#highlightbutton)|Vurgu otomatik gizle düğmesi.|
|[CMFCAutoHideButton:: IsActive](#isactive)|Otomatik gizleme düğmesinin etkin olup olmadığını gösterir.|
|[CMFCAutoHideButton:: ısvurgulu](#ishighlighted)|Otomatik Gizle düğmesinin vurgulama durumunu döndürür.|
|[CMFCAutoHideButton:: ısyatay](#ishorizontal)|Otomatik gizleme düğmesinin yatay mı yoksa dikey mi olduğunu belirler.|
|[CMFCAutoHideButton:: ıstop](#istop)||
|[CMFCAutoHideButton:: IsVisible](#isvisible)|Düğmenin görünür olup olmadığını gösterir.|
|[CMFCAutoHideButton:: Move](#move)||
|[CMFCAutoHideButton:: OnDraw](#ondraw)|Çerçeve, otomatik gizleme düğmesini çizerken bu yöntemi çağırır.|
|[CMFCAutoHideButton:: OnDrawBorder](#ondrawborder)|Çerçeve, bir otomatik gizleme düğmesinin kenarlığını çizerken bu yöntemi çağırır.|
|[CMFCAutoHideButton:: OnFillBackground](#onfillbackground)|Çerçeve, otomatik gizleme düğmesinin arka planını doldururken bu yöntemi çağırır.|
|[CMFCAutoHideButton:: ReplacePane](#replacepane)||
|[CMFCAutoHideButton:: ShowAttachedWindow](#showattachedwindow)|İlişkili [CDockablePane sınıfını](../../mfc/reference/cdockablepane-class.md)gösterir veya gizler.|
|[CMFCAutoHideButton:: ShowButton](#showbutton)|Otomatik gizleme düğmesini gösterir veya gizler.|
|[CMFCAutoHideButton:: UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>Açıklamalar

Oluşturma sırasında `CMFCAutoHideButton` nesne bir [CDockablePane sınıfına](../../mfc/reference/cdockablepane-class.md)eklenir. `CDockablePane`Kullanıcı nesneyle etkileşime geçtiğinde nesne gizlenir veya görüntülenir `CMFCAutoHideButton` .

Varsayılan olarak, `CMFCAutoHideButton` Kullanıcı otomatik gizlemeyi açtığında çerçeve otomatik olarak bir oluşturur. Çerçeve, sınıfı yerine özel bir UI sınıfının bir öğesini oluşturabilir `CMFCAutoHideButton` . Framework 'ün hangi özel UI sınıfını kullanması gerektiğini belirtmek için, statik üye değişkenini `CMFCAutoHideBar::m_pAutoHideButtonRTS` Özel UI sınıfına eşit olarak ayarlayın. Varsayılan olarak, bu değişken olarak ayarlanır `CMFCAutoHideButton` .

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `CMFCAutoHideButton` ve sınıfında çeşitli yöntemleri nasıl kullanacağınızı gösterir `CMFCAutoHideButton` . Örnek, `CMFCAutoHideButton` yöntemini kullanarak bir nesnenin nasıl başlatılacağını `Create` , ilişkili sınıfın nasıl gösterileceğini `CDockablePane` ve otomatik gizleme düğmesini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxoto HideButton. h

## <a name="cmfcautohidebuttonbringtotop"></a><a name="bringtotop"></a> CMFCAutoHideButton:: BringToTop

```cpp
void BringToTop();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttoncreate"></a><a name="create"></a> CMFCAutoHideButton:: Create

Otomatik gizleme düğmesi oluşturur ve başlatır.

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*pParentBar*<br/>
'ndaki Üst araç çubuğuna yönelik bir işaretçi.

*pAutoHideWnd*<br/>
'ndaki [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesine yönelik bir işaretçi. Bu otomatik gizleme düğmesi gizlenir ve bunu gösterir `CDockablePane` .

*Dwhizalaması*<br/>
'ndaki Ana çerçeve penceresi ile düğmenin hizalamasını belirten bir değer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCAutoHideButton` nesne oluşturduğunuzda otomatik gizleme düğmesini belirli bir ile ilişkilendirmeniz gerekir `CDockablePane` . Kullanıcı, ilişkili öğesini gizlemek ve göstermek için otomatik gizleme düğmesini kullanabilir `CDockablePane` .

*Dwhizalaması* parametresi, otomatik gizleme düğmesinin uygulamada nerede olduğunu gösterir. Parametresi aşağıdaki değerlerden herhangi biri olabilir:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetalignment"></a><a name="getalignment"></a> CMFCAutoHideButton:: Gethizalaması

Otomatik Gizle düğmesinin hizalamasını alır.

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme düğmesinin geçerli hizalamasını içeren bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

Otomatik gizleme düğmesinin hizalaması, düğmenin uygulamada nerede olduğunu gösterir. Aşağıdaki değerlerden herhangi biri olabilir:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetautohidewindow"></a><a name="getautohidewindow"></a> CMFCAutoHideButton:: GetAutoHideWindow

Otomatik Gizle düğmesiyle ilişkili [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesini döndürür.

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlişkili nesneye yönelik bir işaretçi `CDockablePane` .

### <a name="remarks"></a>Açıklamalar

Bir otomatik gizleme düğmesini ile ilişkilendirmek için `CDockablePane` `CDockablePane` [CMFCAutoHideButton:: Create](#create) yöntemine bir parametre olarak geçirin.

## <a name="cmfcautohidebuttongetparenttoolbar"></a><a name="getparenttoolbar"></a> CMFCAutoHideButton:: GetParentToolBar

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttongetrect"></a><a name="getrect"></a> CMFCAutoHideButton:: GetRect

```
CRect GetRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttongetsize"></a><a name="getsize"></a> CMFCAutoHideButton:: GetSize

Otomatik Gizle düğmesinin boyutunu belirler.

```
CSize GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CSize`Düğme boyutunu içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Hesaplanan boyut, otomatik gizleme düğmesi kenarlığının boyutunu içerir.

## <a name="cmfcautohidebuttongettextsize"></a><a name="gettextsize"></a> CMFCAutoHideButton:: GetTextSize

Otomatik Gizle düğmesi için metin etiketinin boyutunu döndürür.

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme düğmesine ait metnin boyutunu içeren [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.

## <a name="cmfcautohidebuttonisactive"></a><a name="isactive"></a> CMFCAutoHideButton:: IsActive

Otomatik gizleme düğmesinin etkin olup olmadığını gösterir.

```
BOOL IsActive() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik Gizle düğmesi etkinse doğru; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

İlişkili [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) penceresi gösterildiğinde otomatik gizleme düğmesi etkin olur.

## <a name="cmfcautohidebuttonishorizontal"></a><a name="ishorizontal"></a> CMFCAutoHideButton:: ısyatay

Otomatik gizleme düğmesinin yatay mı yoksa dikey mi olduğunu belirler.

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme yataysa sıfır dışı; 0 Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Framework, bir [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) nesnesinin bir yönünü oluşturduğunuz sırada belirler.  [CMFCAutoHideButton:: Create](#create) yöntemi Içindeki *dwhizalaması* parametresini kullanarak yönlendirmeyi denetleyebilirsiniz.

## <a name="cmfcautohidebuttonistop"></a><a name="istop"></a> CMFCAutoHideButton:: ıstop

```
BOOL IsTop() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonisvisible"></a><a name="isvisible"></a> CMFCAutoHideButton:: IsVisible

Otomatik gizleme düğmesinin görünür olup olmadığını gösterir.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme görünür durumdaysa doğru; Aksi takdirde FALSE.

## <a name="cmfcautohidebuttonondraw"></a><a name="ondraw"></a> CMFCAutoHideButton:: OnDraw

Çerçeve, otomatik gizleme düğmesini çizerken bu yöntemi çağırır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki otomatik gizleme düğmelerinin görünümünü özelleştirmek istiyorsanız, öğesinden türetilmiş yeni bir sınıf oluşturun `CMFCAutoHideButton` . Türetilmiş sınıfınıza bu yöntemi geçersiz kılın.

## <a name="cmfcautohidebuttonondrawborder"></a><a name="ondrawborder"></a> CMFCAutoHideButton:: OnDrawBorder

Çerçeve, bir otomatik gizleme düğmesinin kenarlığını çizerken bu yöntemi çağırır.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rectsınır*<br/>
'ndaki Otomatik gizleme düğmesinin sınırlayıcı dikdörtgeni.

*Rectborderboyutu*<br/>
'ndaki Otomatik Gizle düğmesinin her bir kenarının kenarlık kalınlığı.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki her bir otomatik gizleme düğmesinin kenarlığını özelleştirmek istiyorsanız, öğesinden türetilmiş yeni bir sınıf oluşturun `CMFCAutoHideButton` . Türetilmiş sınıfınıza bu yöntemi geçersiz kılın.

## <a name="cmfcautohidebuttononfillbackground"></a><a name="onfillbackground"></a> CMFCAutoHideButton:: OnFillBackground

Çerçeve, otomatik gizleme düğmesinin arka planını doldururken bu yöntemi çağırır.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Otomatik gizleme düğmesinin sınırlayıcı dikdörtgeni.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki otomatik gizleme düğmelerinin arka planını özelleştirmek istiyorsanız, öğesinden türetilmiş yeni bir sınıf oluşturun `CMFCAutoHideButton` . Türetilmiş sınıfınıza bu yöntemi geçersiz kılın.

## <a name="cmfcautohidebuttonshowattachedwindow"></a><a name="showattachedwindow"></a> CMFCAutoHideButton:: ShowAttachedWindow

İlişkili [CDockablePane sınıfını](../../mfc/reference/cdockablepane-class.md)gösterir veya gizler.

```cpp
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Bu yöntemin ekli olup olmadığını belirten bir Boole değeri `CDockablePane` .

## <a name="cmfcautohidebuttonshowbutton"></a><a name="showbutton"></a> CMFCAutoHideButton:: ShowButton

Otomatik gizleme düğmesini gösterir veya gizler.

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Otomatik gizleme düğmesinin gösterilip gösterilmeyeceğini belirten bir Boole değeri.

## <a name="cmfcautohidebuttonmove"></a><a name="move"></a> CMFCAutoHideButton:: Move

```cpp
void Move(int nOffset);
```

### <a name="parameters"></a>Parametreler

'ndaki *nKonum*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonreplacepane"></a><a name="replacepane"></a> CMFCAutoHideButton:: ReplacePane

```cpp
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pNewBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonunsetautohidemode"></a><a name="unsetautohidemode"></a> CMFCAutoHideButton:: UnSetAutoHideMode

Otomatik gizleme modunu devre dışı bırakın.

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>Parametreler

*pFirstBarInGroup*<br/>
'ndaki Gruptaki ilk çubuğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonhighlightbutton"></a><a name="highlightbutton"></a> CMFCAutoHideButton:: HighlightButton

Otomatik Gizle düğmesini vurgular.

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bHighlight*<br/>
Yeni otomatik gizleme düğmesi durumunu belirtir. DOĞRU düğmenin vurgulandığını gösterir, FALSE düğmenin vurgulanmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonishighlighted"></a><a name="ishighlighted"></a> CMFCAutoHideButton:: ısvurgulu

Otomatik Gizle düğmesinin vurgulama durumunu döndürür.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik Gizle düğmesi vurgulanmışsa, doğru döndürür. Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAutoHideBar sınıfı](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[CAutoHideDockSite sınıfı](../../mfc/reference/cautohidedocksite-class.md)
