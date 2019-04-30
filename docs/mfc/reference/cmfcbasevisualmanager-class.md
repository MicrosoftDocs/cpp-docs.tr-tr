---
title: CMFCBaseVisualManager sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
ms.openlocfilehash: 0c26c0c9c9026f8312218b2ac15f83a50a67be79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403860"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager sınıfı

Türetilmiş görsel yöneticiler Windows teması API'si arasında bir katmanı.

`CMFCBaseVisualManager` varsa UxTheme.dll, yükler ve Windows teması API yöntemleri erişimini yönetir.

Bu sınıf, yalnızca dahili kullanım içindir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|Oluşturur ve başlatır bir `CMFCBaseVisualManager` nesne.|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|Onay kutusu denetimi, geçerli Windows teması kullanarak çizer.|
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Geçerli Windows teması kullanarak bir birleşik giriş kutusu kenarlığı çizer.|
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Birleşik giriş kutusu açılan düğmesi geçerli Windows teması kullanarak çizer.|
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Bir itme düğmesi geçerli Windows teması kullanarak çizer.|
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Bir radyo düğmesi denetimini geçerli Windows teması kullanarak çizer.|
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Bir ilerleme çubuğu bir durum çubuğu denetimi çizen ( [CMFCStatusBar sınıfı](../../mfc/reference/cmfcstatusbar-class.md)) kullanarak geçerli Windows teması.|
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Çubuk barınağı denetiminin arka plan, geçerli Windows teması kullanarak doldurur.|
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Geçerli Windows temayı alır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|Çağrıları `CloseThemeData` için tüm işleyicileri elde `UpdateSystemColors`.|
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Çağrıları `OpenThemeData` çeşitli denetimleri çizmek için tutamaçları almak için: windows, araç çubukları, düğmeler ve benzeri.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın nesneleri doğrudan örneği gerekmez.

Tüm görsel Yöneticiler için temel sınıf olduğundan, yalnızca çağırabilirsiniz [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)için geçerli Visual Yöneticisi bir işaretçi alma ve yöntemleri için erişim `CMFCBaseVisualManager` bu işaretçiyi kullanarak. Geçerli Windows teması kullanarak bir denetimi görüntülenecek varsa, ancak bunu kullanmak en iyisidir `CMFCVisualManagerWindows` arabirimi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxvisualmanager.h

##  <a name="cleanupthemes"></a>  CMFCBaseVisualManager::CleanUpThemes

Çağrıları `CloseThemeData` için tüm işleyicileri elde `UpdateSystemColors`.

```
void CleanUpThemes();
```

### <a name="remarks"></a>Açıklamalar

Yalnızca iç kullanım içindir.

##  <a name="cmfcbasevisualmanager"></a>  CMFCBaseVisualManager::CMFCBaseVisualManager

Oluşturur ve başlatır bir `CMFCBaseVisualManager` nesne.

```
CMFCBaseVisualManager();
```

##  <a name="drawcheckbox"></a>  CMFCBaseVisualManager::DrawCheckBox

Onay kutusu denetimi, geçerli Windows teması kullanarak çizer.

```
virtual BOOL DrawCheckBox(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    int nState,
    BOOL bEnabled,
    BOOL bPressed);

);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi

*Rect*<br/>
[in] Onay kutusu sınırlayıcı dikdörtgenini.

*bHighlighted*<br/>
[in] Onay kutusunu vurgulanır olup olmadığını belirtir.

*nDurum*<br/>
[in] 0 işaretli normal işaretli 1

karma normal için 2.

*bEtkin*<br/>
[in] Onay kutusunu etkin olup olmadığını belirtir.

*bPressed*<br/>
[in] Onay kutusunu basılı olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API etkinse TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Değerlerini *nDurum* için aşağıdaki onay kutusu stilleri karşılık gelir.

|nDurum|Onay kutusu stili|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1.|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

##  <a name="drawcomboborder"></a>  CMFCBaseVisualManager::DrawComboBorder

Birleşik giriş kutusu kenarlığı geçerli Windows teması kullanarak çizer.

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Sınırlayıcı dikdörtgeni birleşik giriş kutusu kenarlığın kalınlığı.

*bDevre Dışı*<br/>
[in] Birleşik giriş kutusu kenarlığı devre dışı bırakılıp bırakılmadığını belirtir.

*bIsDropped*<br/>
[in] Birleşik giriş kutusu kenarlığı açılmış olup olmadığını belirtir.

*bIsHighlighted*<br/>
[in] Birleşik giriş kutusu kenarlığı vurgulanır olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API etkinse TRUE; Aksi durumda FALSE.

##  <a name="drawcombodropbutton"></a>  CMFCBaseVisualManager::DrawComboDropButton

Birleşik giriş kutusu açılan düğmesi geçerli Windows teması kullanarak çizer.

```
virtual BOOL DrawComboDropButton(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pDC*|[in] Bir cihaz bağlamı için bir işaretçi.|
|*Rect*|[in] Birleşik giriş kutusu açılan düğmeyi sınırlayıcı dikdörtgenini.|
|*bDevre Dışı*|[in] Birleşik giriş kutusu açılan düğmeyi devre dışı bırakılıp bırakılmadığını belirtir.|
|*bIsDropped*|[in] Birleşik giriş kutusu açılan düğmeyi açılmış olup olmadığını belirtir.|
|*bIsHighlighted*|[in] Birleşik giriş kutusu açılan düğmesi vurgulanmış olup olmadığını belirtir.|

### <a name="return-value"></a>Dönüş Değeri

Tema API etkinse TRUE; Aksi durumda FALSE.

##  <a name="drawpushbutton"></a>  CMFCBaseVisualManager::DrawPushButton

Bir itme düğmesi geçerli Windows teması kullanarak çizer.

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Düğme sınırlayıcı dikdörtgenini.

*pButton*<br/>
[in] Bir işaretçi [CMFCButton sınıfı](../../mfc/reference/cmfcbutton-class.md) çizmek için kullanılan nesne.

*uiState*<br/>
[in] Yoksayıldı. Durumu alınır *pButton*.

### <a name="return-value"></a>Dönüş Değeri

Tema API etkinse TRUE; Aksi durumda FALSE.

##  <a name="drawradiobutton"></a>  CMFCBaseVisualManager::DrawRadioButton

Bir radyo düğmesi denetimini geçerli Windows teması kullanarak çizer.

```
virtual BOOL DrawRadioButton(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    BOOL bChecked,
    BOOL bEnabled,
    BOOL bPressed);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Dikdörtgen radyo düğmesinin.

*bHighlighted*<br/>
[in] Radyo düğmesi vurgulanmış olup olmadığını belirtir.

*bChecked*<br/>
[in] Radyo düğmesinin işaretli olup olmadığını belirtir.

*bEtkin*<br/>
[in] Radyo düğmesi etkin olup olmadığını belirtir.

*bPressed*<br/>
[in] Radyo düğmesini basılı olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API etkinse TRUE; Aksi durumda FALSE.

##  <a name="drawstatusbarprogress"></a>  CMFCBaseVisualManager::DrawStatusBarProgress

İlerleme çubuğu üzerinde durum çubuğu denetimi çizen ( [CMFCStatusBar sınıfı](../../mfc/reference/cmfcstatusbar-class.md)) kullanarak geçerli Windows teması.

```
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,
    CMFCStatusBar* pStatusBar,
    CRect rectProgress,
    int nProgressTotal,
    int nProgressCurr,
    COLORREF clrBar,
    COLORREF clrProgressBarDest,
    COLORREF clrProgressText,
    BOOL bProgressText);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*pStatusBar*<br/>
[in] Durum çubuğu için bir işaretçi. Bu değer yoksayılır.

*rectProgress*<br/>
[in] İlerleme çubuğunda sınırlayıcı dikdörtgenini *pDC* koordinatları.

*nProgressTotal*<br/>
[in] Toplam devam eden değer.

*nProgressCurr*<br/>
[in] Geçerli ilerleme değeri.

*clrBar*<br/>
[in] Başlangıç rengi. `CMFCBaseVisualManager` Bu yok sayar. Türetilen sınıflar, renk gradyanlar için kullanabilirsiniz.

*clrProgressBarDest*<br/>
[in] Bitiş rengi. `CMFCBaseVisualManager` Bu yok sayar. Türetilen sınıflar, renk gradyanlar için kullanabilirsiniz.

*clrProgressText*<br/>
[in] İlerleme metin rengi. `CMFCBaseVisualManager` Bu yok sayar. Metin rengi tarafından tanımlanan `afxGlobalData.clrBtnText`.

*bProgressText*<br/>
[in] İlerleme metni görüntülenip görüntülenmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API etkinse TRUE; Aksi durumda FALSE.

##  <a name="fillrebarpane"></a>  CMFCBaseVisualManager::FillReBarPane

Çubuk barınağı denetiminin arka plan, geçerli Windows teması kullanarak doldurur.

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*pBar*<br/>
[in] Arka planının çizilmesi gerektiğini bölme için bir işaretçi.

*rectClient*<br/>
[in] Doldurulması için alan sınırlayıcı dikdörtgenini.

### <a name="return-value"></a>Dönüş Değeri

Tema API etkinse TRUE; Aksi durumda FALSE.

##  <a name="getstandardwindowstheme"></a>  CMFCBaseVisualManager::GetStandardWindowsTheme

Geçerli Windows temayı alır.

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>Dönüş Değeri

Seçili Windows Tema rengi. Aşağıdaki numaralandırılmış değerlerden biri olabilir:

- `WinXpTheme_None` -etkin bir teması yok yoktur.

- `WinXpTheme_NonStandard` -Standart olmayan bir tema seçili (Tema işaretli, ancak hiçbiri aşağıdaki listeden anlamına gelir).

- `WinXpTheme_Blue` -mavi tema (Luna).

- `WinXpTheme_Olive` -Zeytin tema.

- `WinXpTheme_Silver` -Gümüş tema.

##  <a name="updatesystemcolors"></a>  CMFCBaseVisualManager::UpdateSystemColors

Çağrıları `OpenThemeData` çeşitli denetimleri çizmek için tutamaçları almak için: windows, araç çubukları, düğmeler ve benzeri.

```
void UpdateSystemColors();
```

### <a name="remarks"></a>Açıklamalar

Yalnızca iç kullanım içindir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
