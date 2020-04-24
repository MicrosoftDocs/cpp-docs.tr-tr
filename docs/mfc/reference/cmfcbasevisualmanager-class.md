---
title: CMFCBaseVisualManager Sınıfı
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
ms.openlocfilehash: ac64a3feac5d124c2bfa67fc857dad5045c2dd28
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754880"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager Sınıfı

Türetilen görsel yöneticiler ve Windows Tema API arasında bir katman.

`CMFCBaseVisualManager`varsa UxTheme.dll yükler ve Windows Tema API yöntemlerine erişimi yönetir.

Bu sınıf yalnızca dahili kullanım içindir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|Bir `CMFCBaseVisualManager` nesne yi inşa eder ve başharfe ait hale raz.|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|Geçerli Windows tesini kullanarak bir onay kutusu denetimi çizer.|
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Geçerli Windows tesini kullanarak açılan kutu kenarlığı çizer.|
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Geçerli Windows tesini kullanarak açılan kutu açılır düğmesini çizer.|
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Geçerli Windows tesini kullanarak bir basma düğmesi çizer.|
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Geçerli Windows tesini kullanarak bir radyo düğmesi denetimi çizer.|
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Geçerli Windows tesini kullanarak durum çubuğu denetiminde [(CMFCStatusBar Class)](../../mfc/reference/cmfcstatusbar-class.md)bir ilerleme çubuğu çizer.|
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Geçerli Windows tesini kullanarak demir çubuğu denetiminin arka planını doldurur.|
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Geçerli Windows tesini alır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCBaseVisualManager::Temizleme Temaları](#cleanupthemes)|'de `CloseThemeData` `UpdateSystemColors`elde edilen tüm tutamaçları n için çağrılar.|
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Pencereler, araç çubukları, düğmeler ve benzeri gibi çeşitli denetimler çizmek için tutamaçları elde etmek için çağrılar. `OpenThemeData`|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın nesnelerini doğrudan anlık olarak annızı sağlamak zorunda değildir.

Tüm görsel yöneticiler için bir taban sınıf olduğundan, [cmfcvisualmanager'ı arayabilirsiniz::GetInstance,](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)geçerli Visual Manager'a bir işaretçi edinin ve bu işaretçiyi kullanma yöntemlerine erişebilirsiniz. `CMFCBaseVisualManager` Ancak, geçerli Windows temasını kullanarak bir denetim görüntülemeniz gerekiyorsa, `CMFCVisualManagerWindows` arabirimi kullanmak daha iyidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxvisualmanager.h

## <a name="cmfcbasevisualmanagercleanupthemes"></a><a name="cleanupthemes"></a>CMFCBaseVisualManager::Temizleme Temaları

'de `CloseThemeData` `UpdateSystemColors`elde edilen tüm tutamaçları n için çağrılar.

```cpp
void CleanUpThemes();
```

### <a name="remarks"></a>Açıklamalar

Yalnızca dahili kullanım içindir.

## <a name="cmfcbasevisualmanagercmfcbasevisualmanager"></a><a name="cmfcbasevisualmanager"></a>CMFCBaseVisualManager::CMFCBaseVisualManager

Bir `CMFCBaseVisualManager` nesne yi inşa eder ve başharfe ait hale raz.

```
CMFCBaseVisualManager();
```

## <a name="cmfcbasevisualmanagerdrawcheckbox"></a><a name="drawcheckbox"></a>CMFCBaseVisualManager::DrawCheckBox

Geçerli Windows tesini kullanarak bir onay kutusu denetimi çizer.

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

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi

*Rect*<br/>
[içinde] Onay kutusunun sınırlayıcı dikdörtgeni.

*bVurgulu*<br/>
[içinde] Onay kutusunun vurgulanıp vurgulanmayacağını belirtir.

*Nstate*<br/>
[in] 0 işaretsiz için, 1 normal kontrol için,

Karışık normal için 2.

*bEtkin*<br/>
[içinde] Onay kutusunun etkin olup olmadığını belirtir.

*bPressed*<br/>
[içinde] Onay kutusuna basılıp basılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API'sı etkinse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

*nState* değerleri aşağıdaki onay kutusu stillerine karşılık gelir.

|Nstate|Kutu stilini işaretle|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

## <a name="cmfcbasevisualmanagerdrawcomboborder"></a><a name="drawcomboborder"></a>CMFCBaseVisualManager::DrawComboBorder

Geçerli Windows tesini kullanarak açılan kutu kenarlığı çizer.

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Açılan kutu kenarlığı sınırlayıcı dikdörtgen.

*bDevre dışı*<br/>
[içinde] Açılan kutu kenarlığı devre dışı kalıp olmadığını belirtir.

*bIsDropped*<br/>
[içinde] Açılan kutu kenarlığı bırakılıp bırakılmadığını belirtir.

*bIsVurgulu*<br/>
[içinde] Açılan kutu kenarlığı vurgulanıp vurgulanmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API'sı etkinse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cmfcbasevisualmanagerdrawcombodropbutton"></a><a name="drawcombodropbutton"></a>CMFCBaseVisualManager::DrawComboDropButton

Geçerli Windows tesini kullanarak açılan kutu açılır düğmesini çizer.

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
|*Pdc*|[içinde] Aygıt bağlamına işaretçi.|
|*Rect*|[içinde] Açılan kutu açılır düğmesinin sınırlayıcı dikdörtgeni.|
|*bDevre dışı*|[içinde] Açılan kutu açılır düğmesinin devre dışı bırakılıp devre dışı bırakılmadığını belirtir.|
|*bIsDropped*|[içinde] Açılan kutu açılır düğmesinin aşağı düşüp düşmediğini belirtir.|
|*bIsVurgulu*|[içinde] Açılan kutu açılır düğmesinin vurgulanıp vurgulanmayacağını belirtir.|

### <a name="return-value"></a>Dönüş Değeri

Tema API'sı etkinse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cmfcbasevisualmanagerdrawpushbutton"></a><a name="drawpushbutton"></a>CMFCBaseVisualManager::DrawPushButton

Geçerli Windows tesini kullanarak bir basma düğmesi çizer.

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Basma düğmesinin sınırlayıcı dikdörtgeni.

*pDüğme*<br/>
[içinde] CMFCButton [Sınıf](../../mfc/reference/cmfcbutton-class.md) nesnesine çizilen bir işaretçi.

*uiState*<br/>
[içinde] Göz ardı. Durum *pButton*alınır.

### <a name="return-value"></a>Dönüş Değeri

Tema API'sı etkinse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cmfcbasevisualmanagerdrawradiobutton"></a><a name="drawradiobutton"></a>CMFCBaseVisualManager::DrawRadioButton

Geçerli Windows tesini kullanarak bir radyo düğmesi denetimi çizer.

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

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Radyo düğmesinin sınırlayıcı dikdörtgeni.

*bVurgulu*<br/>
[içinde] Radyo düğmesinin vurgulanıp vurgulanmayacağını belirtir.

*bKontrol edildi*<br/>
[içinde] Radyo düğmesinin kontrol edilip edilemeyeceğini belirtir.

*bEtkin*<br/>
[içinde] Radyo düğmesinin etkin olup olmadığını belirtir.

*bPressed*<br/>
[içinde] Radyo düğmesine basılıp basılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API'sı etkinse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cmfcbasevisualmanagerdrawstatusbarprogress"></a><a name="drawstatusbarprogress"></a>CMFCBaseVisualManager::DrawStatusBarProgress

Geçerli Windows tesini kullanarak durum çubuğu denetiminde [(CMFCStatusBar Class)](../../mfc/reference/cmfcstatusbar-class.md)ilerleme çubuğu çizer.

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

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*pStatusBar*<br/>
[içinde] Durum çubuğuna işaretçi. Bu değer yoksayılır.

*rektİlerleme*<br/>
[içinde] *PDC* koordinatlarında ilerleme çubuğunun sınırlayıcı dikdörtgeni.

*nProgressTotal*<br/>
[içinde] Toplam ilerleme değeri.

*nProgressCurr*<br/>
[içinde] Geçerli ilerleme değeri.

*clrBar*<br/>
[içinde] Başlangıç rengi. `CMFCBaseVisualManager`bunu göz ardı eder. Türemiş sınıflar renk degradeleri için kullanabilirsiniz.

*clrProgressBarDest*<br/>
[içinde] Son renk. `CMFCBaseVisualManager`bunu göz ardı eder. Türemiş sınıflar renk degradeleri için kullanabilirsiniz.

*clrProgressText*<br/>
[içinde] İlerleme metin rengi. `CMFCBaseVisualManager`bunu göz ardı eder. Metin rengi ile `afxGlobalData.clrBtnText`tanımlanır.

*bProgressText*<br/>
[içinde] İlerleme metninin görüntülenip görüntülenip görüntülenmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tema API'sı etkinse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cmfcbasevisualmanagerfillrebarpane"></a><a name="fillrebarpane"></a>CMFCBaseVisualManager::FillReBarPane

Geçerli Windows tesini kullanarak demir çubuğu denetiminin arka planını doldurur.

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*pBar*<br/>
[içinde] Arka planı çizilmesi gereken bir bölmeiçin işaretçi.

*rectClient*<br/>
[içinde] Doldurulacak alanın sınırlayıcı dikdörtgeni.

### <a name="return-value"></a>Dönüş Değeri

Tema API'sı etkinse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cmfcbasevisualmanagergetstandardwindowstheme"></a><a name="getstandardwindowstheme"></a>CMFCBaseVisualManager::GetStandardWindowsTheme

Geçerli Windows tesini alır.

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili Windows Tema rengi. Aşağıdaki numaralandırılmış değerlerden biri olabilir:

- `WinXpTheme_None`- etkin bir tema yok.

- `WinXpTheme_NonStandard`- standart olmayan tema seçilir (bir tema seçilir, ancak aşağıdaki listeden hiçbiri seçilir).

- `WinXpTheme_Blue`- mavi tema (Luna).

- `WinXpTheme_Olive`- zeytin teması.

- `WinXpTheme_Silver`- gümüş tema.

## <a name="cmfcbasevisualmanagerupdatesystemcolors"></a><a name="updatesystemcolors"></a>CMFCBaseVisualManager::UpdateSystemColors

Pencereler, araç çubukları, düğmeler ve benzeri gibi çeşitli denetimler çizmek için tutamaçları elde etmek için çağrılar. `OpenThemeData`

```cpp
void UpdateSystemColors();
```

### <a name="remarks"></a>Açıklamalar

Yalnızca dahili kullanım içindir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
