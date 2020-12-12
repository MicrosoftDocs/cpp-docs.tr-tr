---
description: 'Daha fazla bilgi edinin: CMFCBaseVisualManager sınıfı'
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
ms.openlocfilehash: 14727eea4bcefdc7b7de53f19f188d7cb9c528c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284986"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager sınıfı

Türetilmiş görsel Yöneticiler ve Windows teması API 'SI arasında bir katman.

`CMFCBaseVisualManager` , varsa UxTheme.dll yükler ve Windows teması API yöntemlerine erişimi yönetir.

Bu sınıf yalnızca iç kullanım içindir.

## <a name="syntax"></a>Syntax

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|[CMFCBaseVisualManager:: CMFCBaseVisualManager](#cmfcbasevisualmanager)|Bir nesnesi oluşturur ve başlatır `CMFCBaseVisualManager` .|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCBaseVisualManager::D rawCheckBox](#drawcheckbox)|Geçerli Windows temasını kullanarak bir onay kutusu denetimi çizer.|
|[CMFCBaseVisualManager::D rawComboBorder](#drawcomboborder)|Geçerli Windows temasını kullanarak bir Birleşik giriş kutusu kenarlığı çizer.|
|[CMFCBaseVisualManager::D rawComboDropButton](#drawcombodropbutton)|Geçerli Windows temasını kullanarak bir açılan kutu açılır düğmesi çizer.|
|[CMFCBaseVisualManager::D Bwpushbutton](#drawpushbutton)|Geçerli Windows temasını kullanarak bir itme düğmesi çizer.|
|[CMFCBaseVisualManager::D rawRadioButton](#drawradiobutton)|Geçerli Windows temasını kullanarak bir radyo düğmesi denetimi çizer.|
|[CMFCBaseVisualManager::D rawStatusBarProgress](#drawstatusbarprogress)|Geçerli Windows temasını kullanarak bir durum çubuğu denetiminde ( [CMFCStatusBar sınıfı](../../mfc/reference/cmfcstatusbar-class.md)) bir ilerleme çubuğu çizer.|
|[CMFCBaseVisualManager:: FillReBarPane](#fillrebarpane)|Geçerli Windows temasını kullanarak yeniden çubuk denetiminin arka planını doldurur.|
|[CMFCBaseVisualManager:: GetStandardWindowsTheme](#getstandardwindowstheme)|Geçerli Windows temasını alır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCBaseVisualManager:: CleanUpThemes](#cleanupthemes)|`CloseThemeData`İçinde edinilen tüm işleyiciler için çağrılar `UpdateSystemColors` .|
|[CMFCBaseVisualManager:: UpdateSystemColors](#updatesystemcolors)|`OpenThemeData`Çeşitli denetimleri çizme tutamaçları elde etmek için çağrılar: pencereler, araç çubukları, düğmeler ve benzeri.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın nesnelerini doğrudan örneklemek zorunda değilsiniz.

Tüm görsel Yöneticiler için bir temel sınıf olduğundan, yalnızca [CMFCVisualManager:: GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)' ı çağırabilir, geçerli görsel yöneticiye bir işaretçi edinebilir ve `CMFCBaseVisualManager` Bu işaretçiyi kullanma yöntemlerine erişebilirsiniz. Ancak, geçerli Windows temasını kullanarak bir denetimi görüntülemesi gerekiyorsa, arabirimi kullanmak daha iyidir `CMFCVisualManagerWindows` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxvisualmanager. h

## <a name="cmfcbasevisualmanagercleanupthemes"></a><a name="cleanupthemes"></a> CMFCBaseVisualManager:: CleanUpThemes

`CloseThemeData`İçinde edinilen tüm işleyiciler için çağrılar `UpdateSystemColors` .

```cpp
void CleanUpThemes();
```

### <a name="remarks"></a>Açıklamalar

Yalnızca dahili kullanım içindir.

## <a name="cmfcbasevisualmanagercmfcbasevisualmanager"></a><a name="cmfcbasevisualmanager"></a> CMFCBaseVisualManager:: CMFCBaseVisualManager

Bir nesnesi oluşturur ve başlatır `CMFCBaseVisualManager` .

```
CMFCBaseVisualManager();
```

## <a name="cmfcbasevisualmanagerdrawcheckbox"></a><a name="drawcheckbox"></a> CMFCBaseVisualManager::D rawCheckBox

Geçerli Windows temasını kullanarak bir onay kutusu denetimi çizer.

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

*Kökündeki*<br/>
'ndaki Cihaz bağlamı işaretçisi

*Rect*<br/>
'ndaki Onay kutusunun sınırlayıcı dikdörtgeni.

*Bvurgulu*<br/>
'ndaki Onay kutusunun vurgulanıp vurgulanmayacağını belirtir.

*nDurum*<br/>
[in] işaretlenmemiş için 0, denetlenen normal için 1

2 karışık normal.

*bEnabled*<br/>
'ndaki Onay kutusunun etkin olup olmadığını belirtir.

*Bbasılmış*<br/>
'ndaki Onay kutusunun basılı olup olmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API 'SI etkinse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

*NState* değerleri aşağıdaki onay kutusu stillerine karşılık gelir.

|nDurum|Onay kutusu stili|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

## <a name="cmfcbasevisualmanagerdrawcomboborder"></a><a name="drawcomboborder"></a> CMFCBaseVisualManager::D rawComboBorder

Geçerli Windows temasını kullanarak Birleşik giriş kutusu kenarlığını çizer.

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Birleşik giriş kutusu kenarlığının sınırlayıcı dikdörtgeni.

*bDisabled*<br/>
'ndaki Birleşik giriş kutusu kenarlığının devre dışı bırakılıp bırakılmadığını belirtir.

*Bisbırakılan*<br/>
'ndaki Birleşik giriş kutusu kenarlığının aşağı bırakılıp bırakılmadığını belirtir.

*Bisvurgulu*<br/>
'ndaki Birleşik giriş kutusu kenarlığının vurgulanıp vurgulanmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API 'SI etkinse doğru; Aksi halde yanlış.

## <a name="cmfcbasevisualmanagerdrawcombodropbutton"></a><a name="drawcombodropbutton"></a> CMFCBaseVisualManager::D rawComboDropButton

Geçerli Windows temasını kullanarak bir açılan kutu açılır düğmesi çizer.

```
virtual BOOL DrawComboDropButton(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*\
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*\
'ndaki Birleşik giriş kutusu açılır düğmesinin sınırlayıcı dikdörtgeni.

*bDisabled*\
'ndaki Birleşik giriş kutusu açılır düğmesinin devre dışı bırakılıp bırakılmadığını belirtir.

*Bisbırakılan*\
'ndaki Birleşik giriş kutusu açılır düğmesinin aşağı bırakılıp bırakılmadığını belirtir.

*Bisvurgulu*\
'ndaki Birleşik giriş kutusu açılır düğmesinin vurgulanıp vurgulanmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API 'SI etkinse doğru; Aksi halde yanlış.

## <a name="cmfcbasevisualmanagerdrawpushbutton"></a><a name="drawpushbutton"></a> CMFCBaseVisualManager::D Bwpushbutton

Geçerli Windows temasını kullanarak bir itme düğmesi çizer.

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Basma düğmesinin sınırlayıcı dikdörtgeni.

*pButton*<br/>
'ndaki Çizilecek [CMFCButton sınıf](../../mfc/reference/cmfcbutton-class.md) nesnesine yönelik bir işaretçi.

*uiState*<br/>
'ndaki LIP. Durum *pButton*'dan alınır.

### <a name="return-value"></a>Dönüş Değeri

Tema API 'SI etkinse doğru; Aksi halde yanlış.

## <a name="cmfcbasevisualmanagerdrawradiobutton"></a><a name="drawradiobutton"></a> CMFCBaseVisualManager::D rawRadioButton

Geçerli Windows temasını kullanarak bir radyo düğmesi denetimi çizer.

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

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Radyo düğmesinin sınırlayıcı dikdörtgeni.

*Bvurgulu*<br/>
'ndaki Radyo düğmesinin vurgulanıp vurgulanmayacağını belirtir.

*bChecked*<br/>
'ndaki Radyo düğmesinin işaretli olup olmadığını belirtir.

*bEnabled*<br/>
'ndaki Radyo düğmesinin etkinleştirilip etkinleştirilmeyeceğini belirtir.

*Bbasılmış*<br/>
'ndaki Radyo düğmesine basıldığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API 'SI etkinse doğru; Aksi halde yanlış.

## <a name="cmfcbasevisualmanagerdrawstatusbarprogress"></a><a name="drawstatusbarprogress"></a> CMFCBaseVisualManager::D rawStatusBarProgress

Geçerli Windows temasını kullanarak durum çubuğu denetiminde ( [CMFCStatusBar sınıfı](../../mfc/reference/cmfcstatusbar-class.md)) ilerleme çubuğunu çizer.

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

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*pStatusBar*<br/>
'ndaki Durum çubuğu işaretçisi. Bu değer yoksayılır.

*rectProgress*<br/>
'ndaki *PDC* koordinatlarındaki ilerleme çubuğunun sınırlayıcı dikdörtgeni.

*nProgressTotal*<br/>
'ndaki Toplam ilerleme değeri.

*nProgressCurr*<br/>
'ndaki Geçerli ilerleme değeri.

*clrBar*<br/>
'ndaki Başlangıç rengi. `CMFCBaseVisualManager` Bunu yoksayar. Türetilmiş sınıflar, renk degradeleri için kullanabilir.

*clrProgressBarDest*<br/>
'ndaki Bitiş rengi. `CMFCBaseVisualManager` Bunu yoksayar. Türetilmiş sınıflar, renk degradeleri için kullanabilir.

*clrProgressText*<br/>
'ndaki İlerleme metni rengi. `CMFCBaseVisualManager` Bunu yoksayar. Metin rengi tarafından tanımlanır `afxGlobalData.clrBtnText` .

*bProgressText*<br/>
'ndaki İlerleme metninin görüntülenip görüntülenmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API 'SI etkinse doğru; Aksi halde yanlış.

## <a name="cmfcbasevisualmanagerfillrebarpane"></a><a name="fillrebarpane"></a> CMFCBaseVisualManager:: FillReBarPane

Geçerli Windows temasını kullanarak yeniden çubuk denetiminin arka planını doldurur.

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*pBar*<br/>
'ndaki Arka planının çizilmesi gereken bölmeye yönelik bir işaretçi.

*rectClient*<br/>
'ndaki Doldurulacak alanın sınırlayıcı dikdörtgeni.

### <a name="return-value"></a>Dönüş Değeri

Tema API 'SI etkinse doğru; Aksi halde yanlış.

## <a name="cmfcbasevisualmanagergetstandardwindowstheme"></a><a name="getstandardwindowstheme"></a> CMFCBaseVisualManager:: GetStandardWindowsTheme

Geçerli Windows temasını alır.

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan Windows teması rengi. , Aşağıdaki numaralandırılmış değerlerden biri olabilir:

- `WinXpTheme_None` -etkin tema yok.

- `WinXpTheme_NonStandard` -Standart olmayan Tema seçilidir (bir tema seçildiğinde, ancak aşağıdaki listeden hiçbir öğe seçilmediği anlamına gelir).

- `WinXpTheme_Blue` -Mavi Tema (Luna).

- `WinXpTheme_Olive` -Zeytin teması.

- `WinXpTheme_Silver` -Gümüş tema.

## <a name="cmfcbasevisualmanagerupdatesystemcolors"></a><a name="updatesystemcolors"></a> CMFCBaseVisualManager:: UpdateSystemColors

`OpenThemeData`Çeşitli denetimleri çizme tutamaçları elde etmek için çağrılar: pencereler, araç çubukları, düğmeler ve benzeri.

```cpp
void UpdateSystemColors();
```

### <a name="remarks"></a>Açıklamalar

Yalnızca dahili kullanım içindir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
