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
ms.openlocfilehash: b7b21651bdab6bf2e4603a8fa012480a6201e34b
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336233"
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
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi  
  
 [in] *dikdörtgen*  
 Onay kutusu sınırlayıcı dikdörtgenini.  
  
 [in] *bHighlighted*  
 Onay kutusunu vurgulanır olup olmadığını belirtir.  
  
 [in] *nDurum*  
 0 işaretli normal işaretli 1  
  
 karma normal için 2.  
  
 [in] *bEtkin*  
 Onay kutusunu etkin olup olmadığını belirtir.  
  
 [in] *bPressed*  
 Onay kutusunu basılı olup olmadığını belirtir.  
  
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
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *dikdörtgen*  
 Sınırlayıcı dikdörtgeni birleşik giriş kutusu kenarlığın kalınlığı.  
  
 [in] *bDevre Dışı*  
 Birleşik giriş kutusu kenarlığı devre dışı bırakılıp bırakılmadığını belirtir.  
  
 [in] *bIsDropped*  
 Birleşik giriş kutusu kenarlığı açılmış olup olmadığını belirtir.  
  
 [in] *bIsHighlighted*  
 Birleşik giriş kutusu kenarlığı vurgulanır olup olmadığını belirtir.  
  
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
|[in] *pDC*|Bir cihaz bağlamı için bir işaretçi.|  
|[in] *dikdörtgen*|Birleşik giriş kutusu açılan düğmeyi sınırlayıcı dikdörtgenini.|  
|[in] *bDevre Dışı*|Birleşik giriş kutusu açılan düğmeyi devre dışı bırakılıp bırakılmadığını belirtir.|  
|[in] *bIsDropped*|Birleşik giriş kutusu açılan düğmeyi açılmış olup olmadığını belirtir.|  
|[in] *bIsHighlighted*|Birleşik giriş kutusu açılan düğmesi vurgulanmış olup olmadığını belirtir.|  
  
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
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *dikdörtgen*  
 Düğme sınırlayıcı dikdörtgenini.  
  
 [in] *pButton*  
 Bir işaretçi [CMFCButton sınıfı](../../mfc/reference/cmfcbutton-class.md) çizmek için kullanılan nesne.  
  
 [in] *uiState*  
 Yoksayıldı. Durumu alınır *pButton*.  
  
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
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *dikdörtgen*  
 Dikdörtgen radyo düğmesinin.  
  
 [in] *bHighlighted*  
 Radyo düğmesi vurgulanmış olup olmadığını belirtir.  
  
 [in] *bChecked*  
 Radyo düğmesinin işaretli olup olmadığını belirtir.  
  
 [in] *bEtkin*  
 Radyo düğmesi etkin olup olmadığını belirtir.  
  
 [in] *bPressed*  
 Radyo düğmesini basılı olup olmadığını belirtir.  
  
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
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *pStatusBar*  
 Durum çubuğu için bir işaretçi. Bu değer yoksayılır.  
  
 [in] *rectProgress*  
 İlerleme çubuğunda sınırlayıcı dikdörtgenini *pDC* koordinatları.  
  
 [in] *nProgressTotal*  
 Toplam devam eden değer.  
  
 [in] *nProgressCurr*  
 Geçerli ilerleme değeri.  
  
 [in] *clrBar*  
 Başlangıç rengi. `CMFCBaseVisualManager` Bu yok sayar. Türetilen sınıflar, renk gradyanlar için kullanabilirsiniz.  
  
 [in] *clrProgressBarDest*  
 Bitiş rengi. `CMFCBaseVisualManager` Bu yok sayar. Türetilen sınıflar, renk gradyanlar için kullanabilirsiniz.  
  
 [in] *clrProgressText*  
 İlerleme metin rengi. `CMFCBaseVisualManager` Bu yok sayar. Metin rengi tarafından tanımlanan `afxGlobalData.clrBtnText`.  
  
 [in] *bProgressText*  
 İlerleme metni görüntülenip görüntülenmeyeceğini belirtir.  
  
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
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *pBar*  
 Arka planının çizilmesi gerektiğini bölme için bir işaretçi.  
  
 [in] *rectClient*  
 Doldurulması için alan sınırlayıcı dikdörtgenini.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
