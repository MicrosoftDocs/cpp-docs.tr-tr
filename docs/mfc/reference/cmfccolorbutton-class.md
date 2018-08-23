---
title: CMFCColorButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43ee49dede1a71e8bd2a01e98a3bdd2dd53ef63d
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42465817"
---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton sınıfı
`CMFCColorButton` Ve [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) sınıfları birlikte bir renk seçici denetimini uygulamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Yeni bir oluşturur `CMFCColorButton` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Sağlar ve normal renk düğmeleri konumlandırılmış bir "Otomatik" düğmesini devre dışı bırakır. (Standart sistem otomatik düğme **otomatik**.)|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Sağlar ve normal renk düğmelerin altında konumlandırılmış bir "diğer" düğmesini devre dışı bırakır. ("Diğer" düğmesi olarak etiketlenmiş standart sistem **daha fazla renk**.)|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Geçerli otomatik rengini alır.|  
|[CMFCColorButton::GetColor](#getcolor)|Bir düğmenin rengini alır.|  
|[CMFCColorButton::SetColor](#setcolor)|Bir düğmenin rengini ayarlar.|  
|[CMFCColorButton::SetColorName](#setcolorname)|Bir renk adını ayarlar.|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Renk Seçici iletişim kutusunda sütun sayısını ayarlar.|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Renk Seçici iletişim kutusu üzerinde görüntülenen belgeye özgü renkleri listesini belirtir.|  
|[CMFCColorButton::SetPalette](#setpalette)|Bir standart görüntü renk paletini belirtir.|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|Metin ve görüntü boyutuna bağlı olarak bir düğme denetiminin boyutunu değiştirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Geçerli renk düğmesi Windows XP görsel stilde görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCColorButton::OnDraw](#ondraw)|Düğmenin resim görüntülemek için framework tarafından çağırılır.|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Düğmenin kenarlık göstermek için framework tarafından çağırılır.|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Düğmeyi bir odağa sahip olduğunda odak dikdörtgeni göstermek için framework tarafından çağırılır.|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Renk Seçici iletişim kutusu gösterilmek üzereyken framework tarafından çağırılır.|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Başlatır `m_pPalette` veri üyesi için belirtilen paleti veya varsayılan sistem paleti korumalı.|  
|[CMFCColorButton::UpdateColor](#updatecolor)|Kullanıcı Renk Seçici iletişim kutusu paletinden bir renk seçtiğinde framework tarafından çağırılır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`m_bAltColorDlg`|Bir Boole değeri. TRUE ise framework görüntüler [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) renk iletişim kutusu *diğer* düğmesine tıklandığında ya da FALSE ise, sistem renk iletişim kutusu. Varsayılan değer True'dur. Daha fazla bilgi için [CMFCColorButton::EnableOtherButton](#enableotherbutton).|  
|`m_bAutoSetFocus`|Bir Boole değeri. Menü görüntülenir ya da FALSE ise, odağı değiştirmez framework TRUE ise odak rengi menüsünde ayarlar. Varsayılan değer True'dur.|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Özelleştirme modu için renk düğmesi etkin olup olmadığını gösterir.|  
|`m_Color`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri. Seçili renk içerir.|  
|`m_ColorAutomatic`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri. Şu anda seçili varsayılan rengi içerir.|  
|`m_Colors`|A [CArray](../../mfc/reference/carray-class.md) , [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değerleri. Şu anda kullanılabilir renklerin içerir.|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md) , [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değerleri. Geçerli belge renkleri içerir.|  
|`m_nColumns`|Bir tamsayı. Renk seçim menüsünde renkleri kılavuzunda görüntülenecek sütun sayısını içerir.|  
|`m_pPalette`|Bir işaretçi bir [CPalette](../../mfc/reference/cpalette-class.md). Geçerli renk seçim menüsünde kullanılabilir olan renkleri içerir.|  
|`m_pPopup`|Bir işaretçi bir [CMFCColorPopupMenu sınıfı](../../mfc/reference/cmfccolorpopupmenu-class.md) nesne. Renk Düğmeye tıkladığınızda görüntülenen renk seçim menüsünde.|  
|`m_strAutoColorText`|Bir dize. Renk seçim menüsünde "Otomatik" düğmesinin etiketi.|  
|`m_strDocColorsText`|Bir dize. Belge renkleri görüntüleyen bir renk seçim menüsünde düğmesinin etiketi.|  
|`m_strOtherText`|Bir dize. Renk seçim menüsünde "diğer" düğmesinin etiketi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `CMFCColorButton` sınıfı bir Renk Seçici iletişim kutusunu açan bir itme düğmesi davranır. Renk Seçici iletişim kutusu, bir dizi küçük renk düğmeleri ve özel renk seçici görüntüleyen bir "diğer" düğmesi içerir. ("Diğer" düğmesi olarak etiketlenmiş standart sistem **daha fazla renk**.) Bir kullanıcı yeni bir renk seçtiğinde `CMFCColorButton` nesne değişikliği yansıtır ve seçilen rengin görüntüler.  
  
 Kodunuzda doğrudan veya kullanarak, renk düğme denetimi oluşturmak **ClassWizard** aracı ve bir iletişim kutusu şablonu. Bir renk düğmesi denetimi doğrudan oluşturursanız, ekleme bir `CMFCColorButton` uygulama ve sonra çağrı Oluşturucu değişken ve `Create` yöntemlerinin `CMFCColorButton` nesne. Kullanırsanız **ClassWizard**, ekleme bir `CButton` değişken, uygulamanıza ve ardından değişkenin türünü değiştirme `CButton` için `CMFCColorButton`.  
  
 Renk Seçici iletişim kutusu ( [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md)) tarafından görüntülenen [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) framework çağırdığında yöntemi `OnLButtonDown` olay işleyicisi. [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) yöntemi, özel bir renk seçimi desteklemek için kılınabilir.  
  
 `CMFCColorButton` Nesne bildirir, bir renk bir WM_COMMAND göndererek ile değişiyor üst | BN_CLICKED bildirimi. Üst kullanan [CMFCColorButton::GetColor](#getcolor) geçerli rengini almak için yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir renk düğmesi çeşitli yöntemlerle kullanarak yapılandırma işlemi gösterilmektedir `CMFCColorButton` sınıfı. Yöntemler rengi düğmesi ve sütunların sayısı rengini ayarlama ve otomatik ve diğer düğmeyi etkinleştir. Bu örneğin parçasıdır [durum çubuğu gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcolorbutton.h  
  
##  <a name="cmfccolorbutton"></a>  CMFCColorButton::CMFCColorButton  
 Yeni bir oluşturur `CMFCColorButton` nesne.  
  
```  
CMFCColorButton();
```  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorButton::EnableAutomaticButton  
 Etkinleştirmek veya bir renk seçici denetimi değerini "Otomatik" düğmesini devre dışı bırakın ve otomatik (varsayılan) rengini ayarlayın.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszLabel*  
 Otomatik düğmenin metni belirtir.  
  
 [in] *colorAutomatic*  
 Otomatik düğmenin varsayılan rengini belirten bir RGB değeri.  
  
 [in] *bSistemlerde*  
 Otomatik düğmenin etkin mi yoksa devre dışı mı olduğunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enableotherbutton"></a>  CMFCColorButton::EnableOtherButton  
 Etkinleştirin veya normal renk düğmeleri görüntülenen "diğer" düğmesini devre dışı.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszLabel*  
 Düğmenin metni belirtir.  
  
 [in] *bAltColorDlg*  
 Belirtir olup olmadığını [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu veya sistem renk iletişim kutusu açılır kullanıcı düğmeyi tıkladığında.  
  
 [in] *bSistemlerde*  
 "Diğer" düğmesi etkin mi yoksa devre dışı mı olduğunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk iletişim kutusu görüntülemek için "diğer" düğmesine tıklayın. Varsa *bAltColorDlg* parametredir TRUE, [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md) görüntülenir; Aksi takdirde, sistem renk iletişim kutusu görüntülenir.  
  
##  <a name="getautomaticcolor"></a>  CMFCColorButton::GetAutomaticColor  
 Geçerli otomatik (varsayılan) rengini alır.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli otomatik rengi temsil eden bir RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli otomatik renge belirlediği [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) yöntemi.  
  
##  <a name="getcolor"></a>  CMFCColorButton::GetColor  
 Şu anda seçili rengini alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isdrawxptheme"></a>  CMFCColorButton::IsDrawXPTheme  
 Geçerli renk düğmesi Windows XP görsel stilde görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görsel stiller desteklenir ve Windows XP görsel stilde geçerli renk düğmesi görüntüleniyorsa TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_benabledincustomizemode"></a>  CMFCColorButton::m_bEnabledInCustomizeMode  
 Bir renk düğmesi özelleştirme modunu ayarlar.  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özelleştirme iletişim kutusunun sayfasına bir renk düğmesi ekleyin (veya başka bir renk seçimi özelleştirme sırasında kullanıcıya izin vermek) gerekiyorsa, düğmeyi etkinleştirmeniz `m_bEnabledInCustomizeMode` üye true. Varsayılan olarak, bu üye FALSE olarak ayarlanır.  
  
##  <a name="ondraw"></a>  CMFCColorButton::OnDraw  
 Düğmenin bir görüntüsünü işlemek için framework tarafından çağırılır.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Düğme görüntüsü oluşturmak için kullanılan cihaz bağlamı işaret eder.  
  
 [in] *dikdörtgen*  
 Düğme sınırların bir dikdörtgen.  
  
 [in] *uiState*  
 Düğmenin görsel durum belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleme sürecini özelleştirmek için bu yöntemi yok sayın.  
  
##  <a name="ondrawborder"></a>  CMFCColorButton::OnDrawBorder  
 Düğmenin kenarlık göstermek için framework tarafından çağırılır.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 İşaret kenarlık çizmek için kullanılan bir cihaz bağlamı.  
  
 [in] *rectClient*  
 Tarafından belirtilen cihaz bağlamında bir dikdörtgen *pDC* düğmesinin çizilmesi sınırlarını tanımlar parametresi.  
  
 [in] *uiState*  
 Düğmenin görsel durum belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, renk düğmenin kenarlık görünümünü özelleştirmek için geçersiz kılın.  
  
##  <a name="ondrawfocusrect"></a>  CMFCColorButton::OnDrawFocusRect  
 Düğme odağa sahip olduğunda odak dikdörtgeni göstermek için framework tarafından çağırılır.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Odak dikdörtgen çizmek için kullanılan bir cihaz bağlamı işaret eder.  
  
 [in] *rectClient*  
 Tarafından belirtilen cihaz bağlamında bir dikdörtgen *pDC* düğmenin sınırlarını tanımlar parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Odak dikdörtgenini görünümünü özelleştirmek için bu yöntemi yok sayın.  
  
##  <a name="onshowcolorpopup"></a>  CMFCColorButton::OnShowColorPopup  
 Açılan renk çubuğu görüntülemeden önce çağrılır.  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="rebuildpalette"></a>  CMFCColorButton::RebuildPalette  
 Başlatır `m_pPalette` veri üyesi için belirtilen paleti veya varsayılan sistem paleti korumalı.  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *pPal*|Bir mantıksal paletini veya NULL bir işaretçi. NULL ise, varsayılan sistem paleti kullanılır.|  
  
##  <a name="setcolor"></a>  CMFCColorButton::SetColor  
 Düğmenin rengini belirtir.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rengi*  
 Bir RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setcolorname"></a>  CMFCColorButton::SetColorName  
 Bir renk adını belirtir.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rengi*  
 Renk RGB değeri.  
  
 [in] *strName*  
 Renk adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk adlarının listesi, uygulama başına geneldir. Sonuç olarak, bu yöntem parametrelerini aktarır [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).  
  
##  <a name="setcolumnsnumber"></a>  CMFCColorButton::SetColumnsNumber  
 Tablonun renkler kullanıcının renk seçimi işlemi sırasında kullanıcıya görüntülenecek sütun sayısını tanımlar.  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nColumns*  
 Sütun sayısını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcının, önceden tanımlanmış renkleri tablosu görüntüler bir açılan renk çubuğu bir renk seçebilirsiniz. Tablodaki sütun sayısını tanımlamak için bu yöntemi kullanın.  
  
##  <a name="setdocumentcolors"></a>  CMFCColorButton::SetDocumentColors  
 Birtakım renk ve kümenin adını belirtir. Renkler kümesi kullanılarak görüntülenen bir [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) nesne.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszLabel*  
 Belge renkleri kümesiyle görüntülenecek etiketi belirtir.  
  
 [in] *lstColors*  
 RGB değerleri listesi başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CMFCColorButton` nesne tutar aktarılır RGB değerleri listesi bir [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) nesne. Renk Çubuğu görüntülendiğinde, bu renklerin olan etiketi tarafından belirtilen özel bir bölümü gösterilir *lpszLabel* parametresi.  
  
##  <a name="setpalette"></a>  CMFCColorButton::SetPalette  
 Açılır renk çubuğunda görüntülemek için standart renkler belirtir.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pPalette*  
 Renk paleti işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sizetocontent"></a>  CMFCColorButton::SizeToContent  
 Görüntü ve metin sığdırmak için düğme denetimi yeniden boyutlandırır.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bCalcOnly*  
 Sıfır olmayan, yeni düğme denetiminin boyutunu hesaplanır ancak gerçek boyutu değiştirilmez.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` yeni bir düğme denetiminin boyutunu belirten bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="updatecolor"></a>  CMFCColorButton::UpdateColor  
 Kullanıcı renk çubuğu kullanıcı renk düğmeye tıkladığında görüntüleyen bir renk seçtiğinde framework tarafından çağırılır.  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rengi*  
 Kullanıcının seçtiği bir renk.  
  
### <a name="remarks"></a>Açıklamalar  
 `UpdateColor` İşlevi şu anda seçili düğmenin rengini değiştirir ve kendi üst WM_COMMAND ileti ile BN_CLICKED standart bildirim göndererek size bildirir. Kullanım [CMFCColorButton::GetColor](#getcolor) seçilen rengin almak için yöntemi.  
  
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
