---
title: CMFCBaseVisualManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 496c6905276e789a72c55db1835187b0d4ab342a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369157"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager sınıfı
Türetilen visual yöneticileri ve Windows tema API arasındaki katman.  
  
 `CMFCBaseVisualManager` varsa UxTheme.dll, yükler ve Windows tema API yöntemlerini erişimini yönetir.  
  
 Bu sınıf yalnızca dahili kullanım içindir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|Oluşturur ve başlatır bir `CMFCBaseVisualManager` nesnesi.|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|Bir onay kutusu denetimi, geçerli Windows temasını kullanarak çizer.|  
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|Geçerli Windows temasını kullanarak birleşik giriş kutusu kenarlık çizer.|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|Geçerli Windows temasını kullanarak bir birleşik giriş kutusu açılan düğmesine çizer.|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|Geçerli Windows temasını kullanarak bir gönderme düğmesi çizer.|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|Geçerli Windows temasını kullanarak bir radyo düğmesi denetimini çizer.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|Durum çubuğu denetiminde bir ilerleme çubuğu çizer ( [CMFCStatusBar sınıfı](../../mfc/reference/cmfcstatusbar-class.md)) kullanarak geçerli Windows teması.|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|Rebar denetimiyle arka planı geçerli Windows temasını kullanarak doldurur.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|Geçerli Windows temasını alır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|Çağrıları `CloseThemeData` tüm tanıtıcıları elde için `UpdateSystemColors`.|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|Çağrıları `OpenThemeData` çeşitli denetimleri çizim tanıtıcıları almak için: windows, araç çubukları, düğmeler ve benzeri.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın nesnelerini doğrudan örneği gerekmez.  
  
 Tüm visual yöneticileri için bir taban sınıf olduğundan, yalnızca çağırabilirsiniz [CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)bir işaretçi için geçerli Visual Yöneticisi edinin ve yöntemleri için erişim `CMFCBaseVisualManager` bu işaretçisi kullanılarak. Geçerli Windows temasını kullanarak bir denetimi görüntüleme varsa, ancak bunu kullanmak en iyisidir `CMFCVisualManagerWindows` arabirimi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxvisualmanager.h  
  
##  <a name="cleanupthemes"></a>  CMFCBaseVisualManager::CleanUpThemes  
 Çağrıları `CloseThemeData` tüm tanıtıcıları elde için `UpdateSystemColors`.  
  
```  
void CleanUpThemes();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca dahili kullanım için.  
  
##  <a name="cmfcbasevisualmanager"></a>  CMFCBaseVisualManager::CMFCBaseVisualManager  
 Oluşturur ve başlatır bir `CMFCBaseVisualManager` nesnesi.  
  
```  
CMFCBaseVisualManager();
```  
  
##  <a name="drawcheckbox"></a>  CMFCBaseVisualManager::DrawCheckBox  
 Bir onay kutusu denetimi, geçerli Windows temasını kullanarak çizer.  
  
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
 [in] `pDC`  
 Bir işaretçi bir cihaz bağlamı  
  
 [in] `rect`  
 Onay kutusu sınırlayıcı dikdörtgenini.  
  
 [in] `bHighlighted`  
 Onay kutusu vurgulanmış olup olmadığını belirtir.  
  
 [in] `nState`  
 0 işaretlenmemişse 1 checked normal için  
  
 karma normal için 2.  
  
 [in] `bEnabled`  
 Onay kutusu etkinleştirilip etkinleştirilmeyeceğini belirtir.  
  
 [in] `bPressed`  
 Onay kutusu basılı olup olmadığını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Tema API etkinleştirilirse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Değerlerini `nState` aşağıdaki onay kutusu stilleri karşılık gelir.  
  
|nDurum|Onay kutusu stili|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1.|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="drawcomboborder"></a>  CMFCBaseVisualManager::DrawComboBorder  
 Geçerli Windows temasını kullanarak birleşik giriş kutusu kenarlığı çizer.  
  
```  
virtual BOOL DrawComboBorder(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rect`  
 Birleşik giriş kutusu kenarlığı sınırlayıcı dikdörtgenini.  
  
 [in] `bDisabled`  
 Birleşik giriş kutusu kenarlığı etkinleştirilip etkinleştirilmeyeceğini belirtir.  
  
 [in] `bIsDropped`  
 Birleşik giriş kutusu kenarlığı açılmış olup olmadığını belirtir.  
  
 [in] `bIsHighlighted`  
 Birleşik giriş kutusu kenarlığı vurgulanmış olup olmadığını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Tema API etkinleştirilirse; Aksi takdirde `FALSE`.  
  
##  <a name="drawcombodropbutton"></a>  CMFCBaseVisualManager::DrawComboDropButton  
 Geçerli Windows temasını kullanarak bir birleşik giriş kutusu açılan düğmesine çizer.  
  
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
|[in] `pDC`|Bir cihaz bağlamı için bir işaretçi.|  
|[in] `rect`|Birleşik giriş kutusu açılan düğmesine sınırlayıcı dikdörtgenini.|  
|[in] `bDisabled`|Birleşik giriş kutusu açılan düğmesi devre dışı olup olmadığını belirtir.|  
|[in] `bIsDropped`|Birleşik giriş kutusu açılan düğmesine açılmış olup olmadığını belirtir.|  
|[in] `bIsHighlighted`|Birleşik giriş kutusu açılan düğmesi vurgulanmış olup olmadığını belirtir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Tema API etkinleştirilirse; Aksi takdirde `FALSE`.  
  
##  <a name="drawpushbutton"></a>  CMFCBaseVisualManager::DrawPushButton  
 Geçerli Windows temasını kullanarak bir gönderme düğmesi çizer.  
  
```  
virtual BOOL DrawPushButton(
    CDC* pDC,   
    CRect rect,   
    CMFCButton* pButton,   
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rect`  
 Düğme sınırlayıcı dikdörtgenini.  
  
 [in] `pButton`  
 Bir işaretçi [CMFCButton sınıfı](../../mfc/reference/cmfcbutton-class.md) çizmek için nesne.  
  
 [in] `uiState`  
 Yoksayıldı. Durum alınırlar `pButton`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Tema API etkinleştirilirse; Aksi takdirde `FALSE`.  
  
##  <a name="drawradiobutton"></a>  CMFCBaseVisualManager::DrawRadioButton  
 Geçerli Windows temasını kullanarak bir radyo düğmesi denetimini çizer.  
  
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
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rect`  
 Radyo düğmesi sınırlayıcı dikdörtgenini.  
  
 [in] `bHighlighted`  
 Radyo düğmesi vurgulanmış olup olmadığını belirtir.  
  
 [in] `bChecked`  
 Radyo düğmesi işaretli olup olmadığını belirtir.  
  
 [in] `bEnabled`  
 Radyo düğmesi etkin olup olmadığını belirtir.  
  
 [in] `bPressed`  
 Radyo düğmesini basılı olup olmadığını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Tema API etkinleştirilirse; Aksi takdirde `FALSE`.  
  
##  <a name="drawstatusbarprogress"></a>  CMFCBaseVisualManager::DrawStatusBarProgress  
 Durum çubuğu denetiminde ilerleme çubuğu çizer ( [CMFCStatusBar sınıfı](../../mfc/reference/cmfcstatusbar-class.md)) kullanarak geçerli Windows teması.  
  
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
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `pStatusBar`  
 Durum çubuğu için bir işaretçi. Bu değer yoksayılır.  
  
 [in] `rectProgress`  
 İlerleme çubuğu'nun sınırlayıcı dikdörtgenini `pDC` koordinatları.  
  
 [in] `nProgressTotal`  
 Toplam devam eden değer.  
  
 [in] `nProgressCurr`  
 Geçerli ilerleme değeri.  
  
 [in] `clrBar`  
 Başlangıç rengi. `CMFCBaseVisualManager` Bu yok sayar. Türetilen sınıflar için renk gradyan kullanabilirsiniz.  
  
 [in] `clrProgressBarDest`  
 Bitiş rengi. `CMFCBaseVisualManager` Bu yok sayar. Türetilen sınıflar için renk gradyan kullanabilirsiniz.  
  
 [in] `clrProgressText`  
 İlerleme metin rengi. `CMFCBaseVisualManager` Bu yok sayar. Metin rengi tarafından tanımlanan `afxGlobalData.clrBtnText`.  
  
 [in] `bProgressText`  
 İlerleme metni görüntülenip görüntülenmeyeceğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Tema API etkinleştirilirse; Aksi takdirde `FALSE`.  
  
##  <a name="fillrebarpane"></a>  CMFCBaseVisualManager::FillReBarPane  
 Rebar denetimiyle arka planı geçerli Windows temasını kullanarak doldurur.  
  
```  
virtual void FillReBarPane(
    CDC* pDC,   
    CBasePane* pBar,   
    CRect rectClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `pBar`  
 Bir bölme arka planının çizilmesi gerektiğini gösteren bir işaretçi.  
  
 [in] `rectClient`  
 Doldurulacak alan sınırlayıcı dikdörtgenini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Tema API etkinleştirilirse; Aksi takdirde `FALSE`.  
  
##  <a name="getstandardwindowstheme"></a>  CMFCBaseVisualManager::GetStandardWindowsTheme  
 Geçerli Windows temasını alır.  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili Windows Tema rengi. Aşağıdaki numaralandırılmış değerlerden biri olabilir:  
  
- `WinXpTheme_None` -Etkin tema yoktur.  
  
- `WinXpTheme_NonStandard` -Standart olmayan tema seçili (Tema seçildiğinde, yok aşağıdaki listeden ancak anlamına gelir).  
  
- `WinXpTheme_Blue` -mavi tema (Luna).  
  
- `WinXpTheme_Olive` -Zeytin tema.  
  
- `WinXpTheme_Silver` -Gümüş tema.  
  
##  <a name="updatesystemcolors"></a>  CMFCBaseVisualManager::UpdateSystemColors  
 Çağrıları `OpenThemeData` çeşitli denetimleri çizim tanıtıcıları almak için: windows, araç çubukları, düğmeler ve benzeri.  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca dahili kullanım için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
