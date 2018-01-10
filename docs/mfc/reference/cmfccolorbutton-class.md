---
title: "CMFCColorButton sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
dev_langs: C++
helpviewer_keywords:
- CMFCColorButton [MFC], CMFCColorButton
- CMFCColorButton [MFC], EnableAutomaticButton
- CMFCColorButton [MFC], EnableOtherButton
- CMFCColorButton [MFC], GetAutomaticColor
- CMFCColorButton [MFC], GetColor
- CMFCColorButton [MFC], SetColor
- CMFCColorButton [MFC], SetColorName
- CMFCColorButton [MFC], SetColumnsNumber
- CMFCColorButton [MFC], SetDocumentColors
- CMFCColorButton [MFC], SetPalette
- CMFCColorButton [MFC], SizeToContent
- CMFCColorButton [MFC], IsDrawXPTheme
- CMFCColorButton [MFC], OnDraw
- CMFCColorButton [MFC], OnDrawBorder
- CMFCColorButton [MFC], OnDrawFocusRect
- CMFCColorButton [MFC], OnShowColorPopup
- CMFCColorButton [MFC], RebuildPalette
- CMFCColorButton [MFC], UpdateColor
- CMFCColorButton [MFC], m_bEnabledInCustomizeMode
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e49cec1c34af066d6f30cf70003252f28e2bb8dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton sınıfı
`CMFCColorButton` Ve [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) sınıfları birlikte bir renk seçici denetim uygulamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Yeni bir oluşturur `CMFCColorButton` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Etkinleştirir ve normal renk düğmeleri konumlandırılmış bir "Otomatik" düğmesini devre dışı bırakır. (Standart sistem otomatik düğmesi etiketli **otomatik**.)|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Sağlar ve normal renk düğmeleri yerleştirilmiş bir "diğer" düğmesini devre dışı bırakır. ("Diğer" düğmesi olarak etiketlenmiş standart sistem **daha renkleri**.)|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Geçerli otomatik rengi alır.|  
|[CMFCColorButton::GetColor](#getcolor)|Düğmenin rengi alır.|  
|[CMFCColorButton::SetColor](#setcolor)|Düğmenin rengini belirler.|  
|[CMFCColorButton::SetColorName](#setcolorname)|Renk adını belirler.|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Sütun sayısı Renk Seçici iletişim kutusunda ayarlar.|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Renk Seçici iletişim kutusunda görüntülenen belge özgü renkler listesini belirtir.|  
|[CMFCColorButton::SetPalette](#setpalette)|Standart görüntü renk paletini belirtir.|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|Düğme denetimi metin ve görüntü boyutuna bağlı olarak boyutunu değiştirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Geçerli renk düğmesi Windows XP görsel stilde görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCColorButton::OnDraw](#ondraw)|Düğme görüntüsü görüntülenecek çerçevesi tarafından çağrılır.|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Düğmenin kenarlık görüntülenecek çerçevesi tarafından çağrılır.|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Düğme bir odağa sahip olduğunda odak dikdörtgeni görüntülenecek çerçevesi tarafından çağrılır.|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Renk Seçici iletişim kutusu hakkında görüntülenecek olduğunda çerçevesi tarafından çağrılır.|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Başlatır `m_pPalette` belirtilen paleti veya varsayılan sistem paleti veri üyesini korumalı.|  
|[CMFCColorButton::UpdateColor](#updatecolor)|Kullanıcı Renk Seçici iletişim kutusu paletinden bir renk seçtiğinde çerçevesi tarafından çağrılır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`m_bAltColorDlg`|Bir Boole değeri. Varsa `TRUE`, framework görüntüler [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) renk iletişim kutusu *diğer* düğmesine tıklandığında, veya `FALSE`, sistem renk iletişim kutusu. Varsayılan değer `TRUE` şeklindedir. Daha fazla bilgi için bkz: [CMFCColorButton::EnableOtherButton](#enableotherbutton).|  
|`m_bAutoSetFocus`|Bir Boole değeri. Varsa `TRUE`, odağı Renk menüsünde menüsü görüntülendiğinde veya framework ayarlar `FALSE`, odağı değiştirmez. Varsayılan değer `TRUE` şeklindedir.|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Renk düğmesini özelleştirme modunun etkinleştirilip etkinleştirilmeyeceğini gösterir.|  
|`m_Color`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri. Seçili renk içerir.|  
|`m_ColorAutomatic`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri. Seçili varsayılan renk içerir.|  
|`m_Colors`|A [CArray](../../mfc/reference/carray-class.md) , [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değerleri. Şu anda kullanılabilir renkleri içerir.|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md) , [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değerleri. Geçerli belge renkleri içerir.|  
|`m_nColumns`|Bir tam sayı. Renklerin renk seçim menüsünü kılavuzunda görüntülenecek sütun sayısını içerir.|  
|`m_pPalette`|Bir işaretçi bir [CPalette](../../mfc/reference/cpalette-class.md). Geçerli renk seçimi menüsünden kullanılabilir renkleri içerir.|  
|`m_pPopup`|Bir işaretçi bir [CMFCColorPopupMenu sınıfı](../../mfc/reference/cmfccolorpopupmenu-class.md) nesnesi. Renk Düğmeye tıkladığınızda görüntülenen renk seçimi menüsü.|  
|`m_strAutoColorText`|Bir dize. Bir renk seçimi menüde "Otomatik" düğmesi etiketi.|  
|`m_strDocColorsText`|Bir dize. Belge renkleri görüntüler bir renk seçimi menüde düğmesi etiketi.|  
|`m_strOtherText`|Bir dize. Bir renk seçimi menüde "diğer" düğmesi etiketi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `CMFCColorButton` sınıfı bir Renk Seçici iletişim kutusu açılır bir gönderme düğmesi olarak davranır. Renk Seçici iletişim kutusu, bir dizi küçük renk düğmeleri ve özel renk seçici görüntüleyen bir "diğer" düğmesi içerir. ("Diğer" düğmesi olarak etiketlenmiş standart sistem **daha renkleri**.) Bir kullanıcı yeni bir renk seçtiğinde `CMFCColorButton` nesne değişikliği yansıtır ve seçilen rengin görüntüler.  
  
 Kodunuzda doğrudan ya da kullanarak renk düğme denetimi oluşturmak **ClassWizard** aracı ve bir iletişim kutusu şablon. Bir renk düğmesi denetimi doğrudan oluşturursanız, ekleme bir `CMFCColorButton` uygulama ve ardından arama Oluşturucusu değişken ve `Create` yöntemlerinin `CMFCColorButton` nesnesi. Kullanırsanız **ClassWizard**, ekleme bir `CButton` uygulamanıza değişken ve değişkeninden türünü değiştirme `CButton` için `CMFCColorButton`.  
  
 Renk Seçici iletişim kutusu ( [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md)) tarafından görüntülenen [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) framework çağırdığında yöntemi `OnLButtonDown` olay işleyicisi. [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) yöntem geçersiz özel renk seçimi desteklemek için.  
  
 `CMFCColorButton` Nesne bildirir göndererek değiştirme bir renk üst bir `WM_COMMAND | BN_CLICKED` bildirim. Üst kullanan [CMFCColorButton::GetColor](#getcolor) geçerli renk alma yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir renk düğmesi çeşitli yöntemlerle kullanarak yapılandırmak gösterilmiştir `CMFCColorButton` sınıfı. Yöntemleri renk düğmesi ve kendi sütun sayısı rengini ayarlama ve otomatik ve diğer düğmeleri etkinleştirin. Bu örneğin parçasıdır [durum çubuğu gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcolorbutton.h  
  
##  <a name="cmfccolorbutton"></a>CMFCColorButton::CMFCColorButton  
 Yeni bir oluşturur `CMFCColorButton` nesnesi.  
  
```  
CMFCColorButton();
```  
  
##  <a name="enableautomaticbutton"></a>CMFCColorButton::EnableAutomaticButton  
 Etkinleştirmek veya "Otomatik" düğmesine bir renk seçici denetiminin devre dışı bırakın ve otomatik (varsayılan) rengini ayarlayın.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Otomatik düğmenin metni belirtir.  
  
 [in]`colorAutomatic`  
 Otomatik düğmenin varsayılan renk belirten bir RGB değeri.  
  
 [in]`bEnable`  
 Otomatik düğmesi etkin mi yoksa devre dışı mı olduğunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enableotherbutton"></a>CMFCColorButton::EnableOtherButton  
 Etkinleştirmek veya normal renk düğmeleri görünen "diğer" düğmesini devre dışı.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Düğmenin metni belirtir.  
  
 [in]`bAltColorDlg`  
 Belirtir olup olmadığını [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu ve sistem renk iletişim kutusu kullanıcı düğmesini tıklattığında açıldığında.  
  
 [in]`bEnable`  
 "Diğer" düğmesi etkin mi yoksa devre dışı mı olduğunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk iletişim kutusu görüntülemek için "diğer" düğmesini tıklatın. Varsa *bAltColorDlg* parametresi `TRUE`, [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md) görüntülenir; Aksi takdirde, sistem renk iletişim kutusu görüntülenir.  
  
##  <a name="getautomaticcolor"></a>CMFCColorButton::GetAutomaticColor  
 Geçerli otomatik (varsayılan) rengini alır.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli otomatik rengi temsil eden bir RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli otomatik rengini ayarlama [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) yöntemi.  
  
##  <a name="getcolor"></a>CMFCColorButton::GetColor  
 Seçili renk alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isdrawxptheme"></a>CMFCColorButton::IsDrawXPTheme  
 Geçerli renk düğmesi Windows XP görsel stilde görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`görsel stiller desteklenir ve Windows XP görsel stilde geçerli renk düğmesi görüntülenir Aksi takdirde `FALSE`.  
  
##  <a name="m_benabledincustomizemode"></a>CMFCColorButton::m_bEnabledInCustomizeMode  
 Bir renk düğmesi özelleştirme moduna ayarlar.  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özelleştirme iletişim kutusu sayfasına bir renk düğmesi ekleme (veya başka bir renk seçim sırasında özelleştirme yapmak kullanıcı izin verin) gerekiyorsa, düğme ayarlayarak etkinleştir `m_bEnabledInCustomizeMode` üyesine `TRUE`. Varsayılan olarak, bu üye ayarlamak `FALSE`.  
  
##  <a name="ondraw"></a>CMFCColorButton::OnDraw  
 Düğme görüntüsü oluşturmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Düğme görüntüsü oluşturmak için kullanılan cihaz bağlamı noktalarına.  
  
 [in]`rect`  
 Düğme bounds dikdörtgen.  
  
 [in]`uiState`  
 Düğmenin görsel durumunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma işlemi özelleştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="ondrawborder"></a>CMFCColorButton::OnDrawBorder  
 Düğmenin kenarlık görüntülemek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 İşaret kenarlığı çizmek için kullanılan cihaz bağlamı eder.  
  
 [in]`rectClient`  
 Dikdörtgene tarafından belirtilen cihaz bağlamı `pDC` çizilecek düğmesinin sınırları tanımlar parametresi.  
  
 [in]`uiState`  
 Düğmenin görsel durumunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev renk düğmenin kenarlık görünümünü özelleştirmek için geçersiz kılar.  
  
##  <a name="ondrawfocusrect"></a>CMFCColorButton::OnDrawFocusRect  
 Düğme odağa sahip olmadığında odak dikdörtgeni görüntülenecek çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Odak dikdörtgeni çizmek için kullanılan cihaz bağlamı noktalarına.  
  
 [in]`rectClient`  
 Dikdörtgene tarafından belirtilen cihaz bağlamı `pDC` düğmesi sınırlarının tanımlar parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Odak dikdörtgeni görünümünü özelleştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onshowcolorpopup"></a>CMFCColorButton::OnShowColorPopup  
 Açılan renk çubuğu görüntülenmeden önce çağrılır.  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="rebuildpalette"></a>CMFCColorButton::RebuildPalette  
 Başlatır `m_pPalette` belirtilen paleti veya varsayılan sistem paleti veri üyesini korumalı.  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`pPal`|Bir mantıksal paleti gösteren bir işaretçi veya `NULL`. Varsa `NULL`, varsayılan sistem paleti kullanılır.|  
  
##  <a name="setcolor"></a>CMFCColorButton::SetColor  
 Düğmenin rengini belirtir.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`color`  
 Bir RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setcolorname"></a>CMFCColorButton::SetColorName  
 Bir renk adını belirtir.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`color`  
 Renk RGB değeri.  
  
 [in]`strName`  
 Renk adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk adları listesi, uygulama başına geneldir. Sonuç olarak, bu yöntem parametreleri için aktarır [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).  
  
##  <a name="setcolumnsnumber"></a>CMFCColorButton::SetColumnsNumber  
 Kullanıcının renk seçimi işlemi sırasında kullanıcıya sunulan renk tablosundaki görüntülenen sütun sayısını tanımlar.  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nColumns`  
 Sütun sayısını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir renk bir açılan renk önceden tanımlanmış renkleri tablosu görüntüleyen çubuğundan seçebilirsiniz. Tablodaki sütun sayısını tanımlamak için bu yöntemi kullanın.  
  
##  <a name="setdocumentcolors"></a>CMFCColorButton::SetDocumentColors  
 Birtakım renk ve kümenin adını belirtir. Renk kümesi kullanılarak görüntülenen bir [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) nesnesi.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Belge renkleri kümesiyle görüntülenecek etiket belirtir.  
  
 [in]`lstColors`  
 RGB değerleri listesi başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CMFCColorButton` nesne aktarılır RGB değerleri listesini tutar bir [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) nesnesi. Renk Çubuğu görüntülendiğinde bu renkleri, etiket tarafından belirtilen özel bir bölümünde gösterilen `lpszLabel` parametresi.  
  
##  <a name="setpalette"></a>CMFCColorButton::SetPalette  
 Açılan Renk Çubuğu'nda görüntülemek için standart renklerini belirtir.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pPalette`  
 Renk paleti gösteren bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sizetocontent"></a>CMFCColorButton::SizeToContent  
 Düğme denetimi, metin ve resim uyacak şekilde yeniden boyutlandırır.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bCalcOnly`  
 Sıfır olmayan düğme denetimi yeni boyutunu hesaplanan ancak gerçek boyutu değiştirilmedi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` nesne yeni bir düğme denetim boyutu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="updatecolor"></a>CMFCColorButton::UpdateColor  
 Kullanıcının kullanıcı renk düğmesini tıklattığında görüntüleyen renk çubuğundan bir renk seçtiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`color`  
 Kullanıcının seçtiği bir renk.  
  
### <a name="remarks"></a>Açıklamalar  
 `UpdateColor` İşlevi şu anda seçili düğmenin rengi değişir ve kendi üst göndererek bildirir bir `WM_COMMAND` ile ileti bir `BN_CLICKED` standart bir bildirim. Kullanım [CMFCColorButton::GetColor](#getcolor) seçili renk alma yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCButton sınıfı](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette sınıfı](../../mfc/reference/cpalette-class.md)   
 [CArray sınıfı](../../mfc/reference/carray-class.md)   
 [CList sınıfı](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)
