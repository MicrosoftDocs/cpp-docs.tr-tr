---
title: CMFCAutoHideButton Sınıfı
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
ms.openlocfilehash: 3ea6ce13b8cca7e0130fe14459a832b476391b0c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751677"
---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton Sınıfı

Gizlemek üzere yapılandırılan bir [CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md) görüntüleyen veya gizleyen düğme.

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCAutoHideButton::Bringtotop](#bringtotop)||
|[CMFCAutoHideButton::Oluştur](#create)|Otomatik gizleme düğmesini oluşturur ve başharfe ait hale.|
|[CMFCAutoHideButton::GetAlignment](#getalignment)|Otomatik gizleme düğmesinin hizalanmasını alır.|
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|Otomatik gizleme düğmesiyle ilişkili [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesini döndürür.|
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton::GetRect](#getrect)||
|[CMFCAutoHideButton::GetSize](#getsize)|Otomatik gizleme düğmesinin boyutunu belirler.|
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|Otomatik gizleme düğmesi için metin etiketinin boyutunu döndürür.|
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|Otomatik gizleme düğmesini vurgular.|
|[CMFCAutoHideButton::Etkin](#isactive)|Otomatik gizleme düğmesinin etkin olup olmadığını gösterir.|
|[CMFCAutoHideButton::Vurgulanmış](#ishighlighted)|Otomatik gizle düğmesinin vurgu durumunu döndürür.|
|[CMFCAutoHideButton::Yatay](#ishorizontal)|Otomatik gizleme düğmesinin yatay mı yoksa dikey mi olduğunu belirler.|
|[CMFCAutoHideButton::Istop](#istop)||
|[CMFCAutoHideButton::Visible](#isvisible)|Düğmenin görünür olup olmadığını gösterir.|
|[CMFCAutoHideButton::Hareket et](#move)||
|[CMFCAutoHideButton::OnDraw](#ondraw)|Framework, otomatik gizleme düğmesini çizerken bu yöntemi çağırır.|
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|Framework, otomatik gizleme düğmesinin kenarlığını çizdiğinde bu yöntemi çağırır.|
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|Framework, otomatik gizleme düğmesinin arka planını doldururken bu yöntemi çağırır.|
|[CMFCAutoHideButton::ReplacePane](#replacepane)||
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|İlişkili [CDockablePane Sınıfını](../../mfc/reference/cdockablepane-class.md)gösterir veya gizler.|
|[CMFCAutoHideButton::ShowButton](#showbutton)|Otomatik gizleme düğmesini gösterir veya gizler.|
|[CMFCAutoHideButton::UnsetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>Açıklamalar

Oluşturma da, `CMFCAutoHideButton` nesne [cdockablePane Sınıfına](../../mfc/reference/cdockablepane-class.md)eklenir. Kullanıcı `CDockablePane` `CMFCAutoHideButton` nesneyle etkileşimde olarak nesne gizlenir veya görüntülenir.

Varsayılan olarak, kullanıcı otomatik gizlemeyi açtığında çerçeve otomatik olarak bir `CMFCAutoHideButton` araç oluşturur. Çerçeve, sınıf yerine özel bir kullanıcı arası `CMFCAutoHideButton` arası sınıfının bir öğesini oluşturabilir. Çerçevenin hangi özel Kullanıcı Arası Bilgisi sınıfı nın `CMFCAutoHideBar::m_pAutoHideButtonRTS` kullanılması gerektiğini belirtmek için statik üye değişkeni özel Kullanıcı Sınıfı sınıfına eşit olarak ayarlayın. Varsayılan olarak, bu değişken `CMFCAutoHideButton`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCAutoHideButton` nesnenin nasıl oluşturup sınıfta `CMFCAutoHideButton` çeşitli yöntemler kullanılacağını göstermektedir. Örnek, bir `CMFCAutoHideButton` nesneyi yöntemini kullanarak `Create` nasıl başharflere ait hale getirmek, ilişkili `CDockablePane` sınıfı göstermek ve otomatik gizle düğmesini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxautohidebutton.h

## <a name="cmfcautohidebuttonbringtotop"></a><a name="bringtotop"></a>CMFCAutoHideButton::Bringtotop

```cpp
void BringToTop();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttoncreate"></a><a name="create"></a>CMFCAutoHideButton::Oluştur

Otomatik gizleme düğmesi oluşturur ve baş harfe ait hale rürtir.

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*pParentBar*<br/>
[içinde] Ana araç çubuğuna işaretçi.

*pAutoHideWnd*<br/>
[içinde] [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesine işaretçi. Bu otomatik gizleme düğmesi gizler `CDockablePane`ve gösterir ki.

*dwHizalama*<br/>
[içinde] Düğmenin ana çerçeve penceresiyle hizalanmasını belirten bir değer.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCAutoHideButton` nesne oluşturduğunuzda, otomatik gizleme düğmesini belirli `CDockablePane`bir . Kullanıcı, ilişkili `CDockablePane`yi gizlemek ve göstermek için otomatik gizleme düğmesini kullanabilir.

*dwAlignment* parametresi, otomatik gizleme düğmesinin uygulamada nerede bulunduğunu gösterir. Parametre aşağıdaki değerlerden biri olabilir:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetalignment"></a><a name="getalignment"></a>CMFCAutoHideButton::GetAlignment

Otomatik gizleme düğmesinin hizalanmasını alır.

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizle düğmesinin geçerli hizalanmasını içeren bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

Otomatik gizleme düğmesinin hizalaması, düğmenin uygulamada nerede bulunduğunu gösterir. Aşağıdaki değerlerden herhangi biri olabilir:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetautohidewindow"></a><a name="getautohidewindow"></a>CMFCAutoHideButton::GetAutoHideWindow

Otomatik gizleme düğmesiyle ilişkili [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesini döndürür.

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlişkili `CDockablePane` nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Otomatik gizleme düğmesini `CDockablePane` `CDockablePane` [CMFCAutoHideButton'a](#create) parametre olarak geçirin: yöntem oluştur.

## <a name="cmfcautohidebuttongetparenttoolbar"></a><a name="getparenttoolbar"></a>CMFCAutoHideButton::GetParentToolBar

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttongetrect"></a><a name="getrect"></a>CMFCAutoHideButton::GetRect

```
CRect GetRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttongetsize"></a><a name="getsize"></a>CMFCAutoHideButton::GetSize

Otomatik gizleme düğmesinin boyutunu belirler.

```
CSize GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme `CSize` boyutunu içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Hesaplanan boyut, otomatik gizleme düğmesinin kenarlığını içerir.

## <a name="cmfcautohidebuttongettextsize"></a><a name="gettextsize"></a>CMFCAutoHideButton::GetTextSize

Otomatik gizleme düğmesi için metin etiketinin boyutunu döndürür.

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme düğmesi için metnin boyutunu içeren bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.

## <a name="cmfcautohidebuttonisactive"></a><a name="isactive"></a>CMFCAutoHideButton::Etkin

Otomatik gizleme düğmesinin etkin olup olmadığını gösterir.

```
BOOL IsActive() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme düğmesi etkinse TRUE; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

İlişkili [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) penceresi gösterildiğinde otomatik gizleme düğmesi etkindir.

## <a name="cmfcautohidebuttonishorizontal"></a><a name="ishorizontal"></a>CMFCAutoHideButton::Yatay

Otomatik gizleme düğmesinin yatay mı yoksa dikey mi olduğunu belirler.

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme yataysa sıfırsız; 0 aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Çerçeve, oluşturduğunuzda [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) nesnesinin yönünü ayarlar.  [CMFCAutoHideButton'daki](#create) *dwAlignment* parametresini kullanarak yönlendirmeyi kontrol edebilirsiniz::Oluşturma yöntemi.

## <a name="cmfcautohidebuttonistop"></a><a name="istop"></a>CMFCAutoHideButton::Istop

```
BOOL IsTop() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonisvisible"></a><a name="isvisible"></a>CMFCAutoHideButton::Visible

Otomatik gizleme düğmesinin görünür olup olmadığını gösterir.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme görünürse DOĞRU; YANLIŞ aksi takdirde.

## <a name="cmfcautohidebuttonondraw"></a><a name="ondraw"></a>CMFCAutoHideButton::OnDraw

Framework, otomatik gizleme düğmesini çizerken bu yöntemi çağırır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki otomatik gizleme düğmelerinin görünümünü özelleştirmek istiyorsanız, türetilmiş yeni `CMFCAutoHideButton`bir sınıf oluşturun. Türemiş sınıfınızda bu yöntemi geçersiz kılın.

## <a name="cmfcautohidebuttonondrawborder"></a><a name="ondrawborder"></a>CMFCAutoHideButton::OnDrawBorder

Framework, otomatik gizleme düğmesinin kenarlığını çizdiğinde bu yöntemi çağırır.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*rektBounds*<br/>
[içinde] Otomatik gizleme düğmesinin sınırlayıcı dikdörtgeni.

*rectBorderSize*<br/>
[içinde] Otomatik gizleme düğmesinin her iki tarafı için kenarlık kalınlığı.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki her otomatik gizleme düğmesinin kenarlığını özelleştirmek istiyorsanız, `CMFCAutoHideButton`'den türetilen yeni bir sınıf oluşturun. Türemiş sınıfınızda bu yöntemi geçersiz kılın.

## <a name="cmfcautohidebuttononfillbackground"></a><a name="onfillbackground"></a>CMFCAutoHideButton::OnFillBackground

Framework, otomatik gizleme düğmesinin arka planını doldururken bu yöntemi çağırır.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Otomatik gizleme düğmesinin sınırlayıcı dikdörtgeni.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki otomatik gizleme düğmeleri için arka planı özelleştirmek istiyorsanız, `CMFCAutoHideButton`'den türetilen yeni bir sınıf oluşturun. Türemiş sınıfınızda bu yöntemi geçersiz kılın.

## <a name="cmfcautohidebuttonshowattachedwindow"></a><a name="showattachedwindow"></a>CMFCAutoHideButton::ShowAttachedWindow

İlişkili [CDockablePane Sınıfını](../../mfc/reference/cdockablepane-class.md)gösterir veya gizler.

```cpp
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
[içinde] Bu yöntemin ekli'ni `CDockablePane`gösterip göstermediğini belirten bir Boolean.

## <a name="cmfcautohidebuttonshowbutton"></a><a name="showbutton"></a>CMFCAutoHideButton::ShowButton

Otomatik gizleme düğmesini gösterir veya gizler.

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
[içinde] Otomatik gizleme düğmesini gösterip göstermeyeceğini belirten bir Boolean.

## <a name="cmfcautohidebuttonmove"></a><a name="move"></a>CMFCAutoHideButton::Hareket et

```cpp
void Move(int nOffset);
```

### <a name="parameters"></a>Parametreler

[içinde] *nOffset*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonreplacepane"></a><a name="replacepane"></a>CMFCAutoHideButton::ReplacePane

```cpp
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pNewBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonunsetautohidemode"></a><a name="unsetautohidemode"></a>CMFCAutoHideButton::UnsetAutoHideMode

Otomatik gizleme modunu devre dışı kılabilir.

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>Parametreler

*pFirstBarInGroup*<br/>
[içinde] Gruptaki ilk çubuk için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonhighlightbutton"></a><a name="highlightbutton"></a>CMFCAutoHideButton::HighlightButton

Otomatik gizleme düğmesini vurgular.

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bVurgu*<br/>
Yeni otomatik gizle düğmesi durumunu belirtir. TRUE düğmenin vurgulandığına, FALSE düğmenin vurgulanmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebuttonishighlighted"></a><a name="ishighlighted"></a>CMFCAutoHideButton::Vurgulanmış

Otomatik gizle düğmesinin vurgu durumunu döndürür.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizle düğmesi vurgulanırsa TRUE döndürür; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAutoHideBar Sınıfı](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[CAutoHideDockSite Sınıfı](../../mfc/reference/cautohidedocksite-class.md)
