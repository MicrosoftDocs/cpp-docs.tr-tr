---
title: CMFCAutoHideButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92f7875620f6cc3efee77094fcae80de83f6db1b
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056080"
---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton sınıfı

Görüntüleyen veya gizleyen bir düğme bir [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) gizlenmek üzere yapılandırılmış.

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

## <a name="syntax"></a>Sözdizimi

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAutoHideButton::BringToTop](#bringtotop)||
|[CMFCAutoHideButton::Create](#create)|Oluşturur ve Otomatik Gizle düğmesi başlatır.|
|[CMFCAutoHideButton::GetAlignment](#getalignment)|Otomatik Gizle düğmesi hizalamasını alır.|
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|Döndürür [CDockablePane](../../mfc/reference/cdockablepane-class.md) otomatik gizle düğmesi ile ilişkili nesne.|
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton::GetRect](#getrect)||
|[CMFCAutoHideButton::GetSize](#getsize)|Otomatik Gizle düğmesi boyutunu belirler.|
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|Otomatik Gizle düğmesi metin etiketi boyutunu döndürür.|
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|Otomatik Gizle düğmesi olarak vurgular.|
|[CMFCAutoHideButton::IsActive](#isactive)|Otomatik Gizle düğmesi etkin olup olmadığını gösterir.|
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|Otomatik Gizle düğmesi durumunu döndürür vurgulayın.|
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|Otomatik Gizle düğmesi yatay veya dikey olup olmadığını belirler.|
|[CMFCAutoHideButton::IsTop](#istop)||
|[CMFCAutoHideButton::IsVisible](#isvisible)|Düğmenin görünür olup olmadığını gösterir.|
|[CMFCAutoHideButton::Move](#move)||
|[CMFCAutoHideButton::OnDraw](#ondraw)|Otomatik Gizle düğmesi çizdiğinde framework bu yöntemi çağırır.|
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|Otomatik Gizle düğmesi kenarlığını çizdiğinde framework bu yöntemi çağırır.|
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|Otomatik Gizle düğmesi arka planını doldururken framework bu yöntemi çağırır.|
|[CMFCAutoHideButton::ReplacePane](#replacepane)||
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|Gösterir veya gizler ilişkili [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md).|
|[CMFCAutoHideButton::ShowButton](#showbutton)|Otomatik Gizle düğmesi gizler veya gösterir.|
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>Açıklamalar

Oluşturma, `CMFCAutoHideButton` nesne eklendiği bir [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md). `CDockablePane` Nesne gizli ya da kullanıcının etkileşime olarak görüntülendiğini `CMFCAutoHideButton` nesne.

Varsayılan olarak, çerçeve otomatik olarak oluşturur bir `CMFCAutoHideButton` kullanıcı otomatik gizleme üzerinde ne zaman kapatır. Bir öğe yerine özel bir kullanıcı Arabirimi sınıfının framework oluşturabilirsiniz `CMFCAutoHideButton` sınıfı. Framework kullanması gereken hangi özel kullanıcı Arabirimi sınıfı belirtmek için statik üye değişkenini `CMFCAutoHideBar::m_pAutoHideButtonRTS` özel kullanıcı Arabirimi sınıfı eşittir. Varsayılan olarak, bu değişkeni ayarlamak `CMFCAutoHideButton`.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCAutoHideButton` nesne ve çeşitli yöntemlerle kullanma `CMFCAutoHideButton` sınıfı. Örnek nasıl başlatılacağını gösterir bir `CMFCAutoHideButton` nesnesini kullanarak kendi `Create` yöntemi, ilişkili Göster `CDockablePane` sınıfı ve Otomatik Gizle düğmesi gösterin.

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxautohidebutton.h

##  <a name="bringtotop"></a>  CMFCAutoHideButton::BringToTop

```
void BringToTop();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="create"></a>  CMFCAutoHideButton::Create

Oluşturur ve Otomatik Gizle düğmesi başlatır.

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*pParentBar*<br/>
[in] Üst araç çubuğunda bir işaretçi.

*pAutoHideWnd*<br/>
[in] Bir işaretçi bir [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesne. Bu otomatik gizle düğmesi gizler ve gösteren `CDockablePane`.

*dwAlignment*<br/>
[in] Ana çerçeve penceresi ile düğme hizalamasını belirten bir değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluştururken bir `CMFCAutoHideButton` nesnesi ile belirli bir Otomatik Gizle düğmesi ilişkilendirmeniz gerekir `CDockablePane`. Kullanıcı ilişkili gösterme ve gizleme için Otomatik Gizle düğmesi kullanabilir `CDockablePane`.

*DwAlignment* parametresi gösterir otomatik gizle düğmesi uygulamayı bulunduğu. Parametre aşağıdaki değerlerden biri olabilir:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

##  <a name="getalignment"></a>  CMFCAutoHideButton::GetAlignment

Otomatik Gizle düğmesi hizalamasını alır.

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik Gizle düğmesi geçerli hizalamasını içeren bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

Düğme, uygulama üzerinde bulunduğu otomatik gizle düğmesi hizalamasını belirtir. Bu, aşağıdaki değerlerden biri olabilir:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

##  <a name="getautohidewindow"></a>  CMFCAutoHideButton::GetAutoHideWindow

Döndürür [CDockablePane](../../mfc/reference/cdockablepane-class.md) otomatik gizle düğmesi ile ilişkili nesne.

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlişkili bir işaretçiye `CDockablePane` nesne.

### <a name="remarks"></a>Açıklamalar

Bir Otomatik Gizle düğmesi ile ilişkilendirilecek bir `CDockablePane`, geçmesi `CDockablePane` bir parametre olarak [CMFCAutoHideButton::Create](#create) yöntemi.

##  <a name="getparenttoolbar"></a>  CMFCAutoHideButton::GetParentToolBar

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getrect"></a>  CMFCAutoHideButton::GetRect

```
CRect GetRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getsize"></a>  CMFCAutoHideButton::GetSize

Otomatik Gizle düğmesi boyutunu belirler.

```
CSize GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `CSize` düğme boyutu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Hesaplanan boyuta otomatik gizle düğmesi kenarlığını boyutunu içerir.

##  <a name="gettextsize"></a>  CMFCAutoHideButton::GetTextSize

Otomatik Gizle düğmesi metin etiketi boyutunu döndürür.

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

A [CSize](../../atl-mfc-shared/reference/csize-class.md) otomatik gizle düğmesi için metin boyutunu içeren nesne.

##  <a name="isactive"></a>  CMFCAutoHideButton::IsActive

Otomatik Gizle düğmesi etkin olup olmadığını gösterir.

```
BOOL IsActive() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik Gizle düğmesi etkinse TRUE; FALSE Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Otomatik Gizle düğmesi etkinse ilişkili [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) penceresi görüntülenir.

##  <a name="ishorizontal"></a>  CMFCAutoHideButton::IsHorizontal

Otomatik Gizle düğmesi yatay veya dikey olup olmadığını belirler.

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin yatay olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Framework yönünü ayarlar bir [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) nesnesi oluşturduğunuzda.  Yönlendirmeyi kullanarak denetleyebilirsiniz *dwAlignment* parametresinde [CMFCAutoHideButton::Create](#create) yöntemi.

##  <a name="istop"></a>  CMFCAutoHideButton::IsTop

```
BOOL IsTop() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="isvisible"></a>  CMFCAutoHideButton::IsVisible

Otomatik Gizle düğmesi görünür olup olmadığını gösterir.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin görünür ise TRUE; FALSE Aksi takdirde.

##  <a name="ondraw"></a>  CMFCAutoHideButton::OnDraw

Otomatik Gizle düğmesi çizdiğinde framework bu yöntemi çağırır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Otomatik gizleme düğmeleri, uygulamanızın görünümünü özelleştirmek istiyorsanız, türetilen yeni bir sınıf oluşturun `CMFCAutoHideButton`. Bu yöntem, türetilen bir sınıfta geçersiz.

##  <a name="ondrawborder"></a>  CMFCAutoHideButton::OnDrawBorder

Otomatik Gizle düğmesi kenarlığını çizdiğinde framework bu yöntemi çağırır.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*rectBounds*<br/>
[in] Otomatik Gizle düğmesi sınırlayıcı dikdörtgenini.

*rectBorderSize*<br/>
[in] Otomatik Gizle düğmesi her iki tarafındaki için kenarlık kalınlığı.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki her otomatik gizle düğmesi kenarlığını özelleştirmek istiyorsanız, türetilen yeni bir sınıf oluşturun `CMFCAutoHideButton`. Bu yöntem, türetilen bir sınıfta geçersiz.

##  <a name="onfillbackground"></a>  CMFCAutoHideButton::OnFillBackground

Otomatik Gizle düğmesi arka planını doldururken framework bu yöntemi çağırır.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Otomatik Gizle düğmesi sınırlayıcı dikdörtgenini.

### <a name="remarks"></a>Açıklamalar

Uygulamanızdaki otomatik gizleme düğmelerinin arka plan özelleştirmek istiyorsanız, türetilen yeni bir sınıf oluşturun `CMFCAutoHideButton`. Bu yöntem, türetilen bir sınıfta geçersiz.

##  <a name="showattachedwindow"></a>  CMFCAutoHideButton::ShowAttachedWindow

Gösterir veya gizler ilişkili [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md).

```
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bBilgi Göster*<br/>
[in] Bu yöntem ekli gösterip göstermediğini belirten Boolean bir değer `CDockablePane`.

##  <a name="showbutton"></a>  CMFCAutoHideButton::ShowButton

Otomatik Gizle düğmesi gizler veya gösterir.

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bBilgi Göster*<br/>
[in] Otomatik Gizle düğmesi görüntülenip görüntülenmeyeceğini belirten bir Boole değeri.

##  <a name="move"></a>  CMFCAutoHideButton::Move

```
void Move(int nOffset);
```

### <a name="parameters"></a>Parametreler

[in] *nOffset*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="replacepane"></a>  CMFCAutoHideButton::ReplacePane

```
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>Parametreler

[in] *pNewBar*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="unsetautohidemode"></a>  CMFCAutoHideButton::UnSetAutoHideMode

Otomatik gizleme modu devre dışı bırakın.

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>Parametreler

*pFirstBarInGroup*<br/>
[in] İlk çubuğunda bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="highlightbutton"></a>  CMFCAutoHideButton::HighlightButton

Otomatik Gizle düğmesi vurgular.

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bHighlight*<br/>
Yeni Otomatik Gizle düğmesi durumunda belirtir. DOĞRU düğmesi vurgulanmış gösterir, düğmeyi Vurgulanmayan false değerini gösterir.

### <a name="remarks"></a>Açıklamalar

##  <a name="ishighlighted"></a>  CMFCAutoHideButton::IsHighlighted

Otomatik Gizle düğmesi vurgulama durumunu döndürür.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik Gizle düğmesi, TRUE döndürür vurgulanana; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAutoHideBar Sınıfı](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[CAutoHideDockSite Sınıfı](../../mfc/reference/cautohidedocksite-class.md)
