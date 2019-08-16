---
title: CMFCColorButton sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: ac49957f075f8798607535286d6c4518c0eeeeae
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505368"
---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton sınıfı

Ve CMFCColorBar sınıf sınıfları bir renk seçici denetimi uygulamak için birlikte kullanılır. [](../../mfc/reference/cmfccolorbar-class.md) `CMFCColorButton`

## <a name="syntax"></a>Sözdizimi

```
class CMFCColorButton : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorButton:: CMFCColorButton](#cmfccolorbutton)|Yeni `CMFCColorButton` bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorButton:: EnableAutomaticButton](#enableautomaticbutton)|Normal renk düğmelerinin üzerine yerleştirilmiş bir "otomatik" düğmesini etkinleştirip devre dışı bırakır. (Standart sistem otomatik düğmesi **Otomatik**olarak etiketlenir.)|
|[CMFCColorButton:: EnableOtherButton](#enableotherbutton)|Normal renk düğmelerinin altına yerleştirilmiş bir "diğer" düğmesini etkinleştirip devre dışı bırakır. (Standart sistem "diğer" düğmesi **daha fazla renk**etiketlidir.)|
|[CMFCColorButton:: GetAutomaticColor](#getautomaticcolor)|Geçerli otomatik rengi alır.|
|[CMFCColorButton:: GetColor](#getcolor)|Düğme rengini alır.|
|[CMFCColorButton:: SetColor](#setcolor)|Düğme rengini ayarlar.|
|[CMFCColorButton:: SetColorName](#setcolorname)|Bir renk adı ayarlar.|
|[CMFCColorButton:: SetColumns numarası](#setcolumnsnumber)|Renk Seçici iletişim kutusundaki sütun sayısını ayarlar.|
|[CMFCColorButton:: SetDocumentColors](#setdocumentcolors)|Renk Seçici iletişim kutusunda görüntülenen belgeye özgü renklerin listesini belirtir.|
|[CMFCColorButton:: SetPalette](#setpalette)|Standart görüntü renkleri paletini belirtir.|
|[CMFCColorButton:: SizeToContent](#sizetocontent)|Metin ve resim boyutuna bağlı olarak düğme denetiminin boyutunu değiştirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorButton:: ısdrawxptheme](#isdrawxptheme)|Windows XP 'nin görsel stilinde geçerli renk düğmesinin görüntülenip görüntülenmediğini gösterir.|
|[CMFCColorButton:: OnDraw](#ondraw)|Düğmenin bir görüntüsünü göstermek için Framework tarafından çağırılır.|
|[CMFCColorButton:: OnDrawBorder](#ondrawborder)|Düğmenin kenarlığını göstermek için Framework tarafından çağırılır.|
|[CMFCColorButton:: OnDrawFocusRect](#ondrawfocusrect)|Düğme odağa sahip olduğunda bir odak dikdörtgeni göstermek için Framework tarafından çağırılır.|
|[CMFCColorButton:: OnShowColorPopup](#onshowcolorpopup)|Renk Seçici iletişim kutusu görüntülenmek üzereyken Framework tarafından çağırılır.|
|[CMFCColorButton:: RebuildPalette](#rebuildpalette)|`m_pPalette` Korunan veri üyesini belirtilen palete veya varsayılan sistem paletine başlatır.|
|[CMFCColorButton:: UpdateColor](#updatecolor)|Kullanıcı Renk Seçici iletişim kutusu paletinden bir renk seçtiğinde Framework tarafından çağırılır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|`m_bAltColorDlg`|Boole değeri. TRUE ise Framework, *diğer* düğmeye tıklandığında [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Color ILETIŞIM kutusunu görüntüler veya false ise sistem rengi iletişim kutusudur. Varsayılan değer TRUE 'dur. Daha fazla bilgi için bkz. [CMFCColorButton:: EnableOtherButton](#enableotherbutton).|
|`m_bAutoSetFocus`|Boole değeri. TRUE ise, çerçeve menü görüntülenirken odak rengini ayarlar veya FALSE ise odağı değiştirmez. Varsayılan değer TRUE 'dur.|
|[CMFCColorButton:: m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Özelleştirme modunun renk düğmesi için etkin olup olmadığını gösterir.|
|`m_Color`|[Colorref](/windows/win32/gdi/colorref) değeri. Şu anda seçili rengi içerir.|
|`m_ColorAutomatic`|[Colorref](/windows/win32/gdi/colorref) değeri. Şu anda seçili olan varsayılan rengi içerir.|
|`m_Colors`|[Colorref](/windows/win32/gdi/colorref) değerlerinin [CArray](../../mfc/reference/carray-class.md) değeri. Şu anda kullanılabilir renkleri içerir.|
|`m_lstDocColors`|[Colorref](/windows/win32/gdi/colorref) değerlerinin [CList](../../mfc/reference/clist-class.md) 'i. Geçerli belge renklerini içerir.|
|`m_nColumns`|Bir tamsayı. Renk seçimi menüsündeki renklerin kılavuzunda görüntülenecek sütun sayısını içerir.|
|`m_pPalette`|[CPalette](../../mfc/reference/cpalette-class.md)işaretçisi. Geçerli renk seçim menüsünde bulunan renkleri içerir.|
|`m_pPopup`|[CMFCColorPopupMenu sınıfı](../../mfc/reference/cmfccolorpopupmenu-class.md) nesnesine yönelik bir işaretçi. Renk düğmesine tıkladığınızda görüntülenen renk seçim menüsü.|
|`m_strAutoColorText`|Bir dize. Renk seçimi menüsündeki "otomatik" düğmesinin etiketi.|
|`m_strDocColorsText`|Bir dize. Belge renklerini görüntüleyen bir renk seçimi menüsündeki düğme etiketi.|
|`m_strOtherText`|Bir dize. Renk seçimi menüsündeki "diğer" düğmesinin etiketi.|

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CMFCColorButton` sınıfı bir renk seçici iletişim kutusu açan bir itme düğmesi olarak davranır. Renk Seçici iletişim kutusunda bir dizi küçük renk düğmesi ve özel bir renk seçici görüntüleyen bir "diğer" düğmesi bulunur. (Standart sistem "diğer" düğmesi **daha fazla renk**etiketlidir.) Bir Kullanıcı yeni bir renk seçtiğinde, `CMFCColorButton` nesne değişikliği yansıtır ve seçilen rengi görüntüler.

Doğrudan kodunuzda veya **ClassWizard** aracını ve bir iletişim kutusu şablonunu kullanarak bir renk düğmesi denetimi oluşturun. Doğrudan bir Color Button denetimi oluşturursanız uygulamanıza bir `CMFCColorButton` değişken ekleyin ve ardından `CMFCColorButton` nesnenin oluşturucusunu ve `Create` yöntemlerini çağırın. **ClassWizard**kullanıyorsanız, uygulamanıza bir `CButton` değişken ekleyin ve sonra değişkenin `CButton` türünü olarak `CMFCColorButton`değiştirin.

Çerçeve olay işleyicisini çağırdığında, Renk Seçici iletişim kutusu ( [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md)) [CMFCColorButton:: OnShowColorPopup](#onshowcolorpopup) yöntemi tarafından görüntülenir. `OnLButtonDown` [CMFCColorButton:: OnShowColorPopup](#onshowcolorpopup) yöntemi, özel renk seçimini desteklemek için geçersiz kılınabilir.

`CMFCColorButton` Nesnesi, üst öğesine bir rengin bir WM_COMMAND göndererek değiştiğini bildirir | BN_CLICKED bildirimi. Üst öğe, geçerli rengi almak için [CMFCColorButton:: GetColor](#getcolor) metodunu kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCColorButton` sınıfında çeşitli yöntemler kullanarak bir renk düğmesinin nasıl yapılandırılacağını gösterir. Yöntemler, renk düğmesi ve sütun sayısı rengini ayarlar ve otomatik ve diğer düğmeleri etkinleştirir. Bu örnek, [durum çubuğu tanıtım örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolorbutton. h

##  <a name="cmfccolorbutton"></a>CMFCColorButton:: CMFCColorButton

Yeni `CMFCColorButton` bir nesne oluşturur.

```
CMFCColorButton();
```

##  <a name="enableautomaticbutton"></a>CMFCColorButton:: EnableAutomaticButton

Renk Seçici denetiminin "otomatik" düğmesini etkinleştirin veya devre dışı bırakın ve otomatik (varsayılan) rengi ayarlayın.

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Otomatik düğmenin metnini belirtir.

*colorAutomatic*<br/>
'ndaki Otomatik düğmenin varsayılan rengini belirten bir RGB değeri.

*bEnable*<br/>
'ndaki Otomatik düğmenin etkin mi yoksa devre dışı mı olduğunu belirtir.

### <a name="remarks"></a>Açıklamalar

##  <a name="enableotherbutton"></a>CMFCColorButton:: EnableOtherButton

Normal renk düğmelerinin altında görünen "diğer" düğmesini etkinleştirin veya devre dışı bırakın.

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Düğme metnini belirtir.

*bAltColorDlg*<br/>
'ndaki Kullanıcı düğmeye tıkladığında [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusunun veya sistem rengi iletişim kutusunun açılıp açılmadığını belirtir.

*bEnable*<br/>
'ndaki "Diğer" düğmesinin etkin veya devre dışı olduğunu belirtir.

### <a name="remarks"></a>Açıklamalar

Bir renk iletişim kutusu göstermek için "diğer" düğmesine tıklayın. *BAltColorDlg* parametresi true Ise [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md) görüntülenir; Aksi halde, sistem rengi iletişim kutusu görüntülenir.

##  <a name="getautomaticcolor"></a>CMFCColorButton:: GetAutomaticColor

Geçerli otomatik (varsayılan) rengi alır.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli otomatik rengi temsil eden bir RGB değeri.

### <a name="remarks"></a>Açıklamalar

Geçerli otomatik renk [CMFCColorButton:: EnableAutomaticButton](#enableautomaticbutton) yöntemi tarafından ayarlanır.

##  <a name="getcolor"></a>CMFCColorButton:: GetColor

Şu anda seçili rengi alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir RGB değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="isdrawxptheme"></a>CMFCColorButton:: ısdrawxptheme

Windows XP 'nin görsel stilinde geçerli renk düğmesinin görüntülenip görüntülenmediğini gösterir.

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görsel stiller destekleniyorsa ve geçerli renk düğmesi Windows XP 'nin görsel stilinde görüntüleniyorsa TRUE; Aksi takdirde, FALSE.

##  <a name="m_benabledincustomizemode"></a>CMFCColorButton:: m_bEnabledInCustomizeMode

Özelleştirme moduna bir renk düğmesi ayarlar.

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>Açıklamalar

Özelleştirme iletişim kutusunun sayfasına bir renk düğmesi eklemeniz gerekiyorsa (veya özelleştirme sırasında kullanıcının başka bir renk seçimi yapmasına izin verirseniz), `m_bEnabledInCustomizeMode` üyeyi true olarak ayarlayarak düğmeyi etkinleştirin. Varsayılan olarak, bu üye FALSE olarak ayarlanır.

##  <a name="ondraw"></a>CMFCColorButton:: OnDraw

Düğmenin bir görüntüsünü işlemek için Framework tarafından çağırılır.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Düğmenin görüntüsünü işlemek için kullanılan cihaz bağlamına işaret eder.

*Rect*<br/>
'ndaki Düğmeyi sınıralan dikdörtgen.

*uiState*<br/>
'ndaki Düğmenin görsel durumunu belirtir.

### <a name="remarks"></a>Açıklamalar

İşleme sürecini özelleştirmek için bu yöntemi geçersiz kılın.

##  <a name="ondrawborder"></a>CMFCColorButton:: OnDrawBorder

Düğmenin kenarlığını göstermek için Framework tarafından çağırılır.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Kenarlık çizmek için kullanılan cihaz bağlamına işaret eder.

*rectClient*<br/>
'ndaki Çizilecek düğmenin sınırlarını tanımlayan *PDC* parametresi tarafından belirtilen cihaz bağlamında bir dikdörtgen.

*uiState*<br/>
'ndaki Düğmenin görsel durumunu belirtir.

### <a name="remarks"></a>Açıklamalar

Renk düğmesinin kenarlık görünümünü özelleştirmek için bu işlevi geçersiz kılın.

##  <a name="ondrawfocusrect"></a>CMFCColorButton:: OnDrawFocusRect

Düğme odağa sahip olduğunda bir odak dikdörtgeni göstermek için Framework tarafından çağırılır.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Odak dikdörtgenini çizmek için kullanılan cihaz bağlamını işaret eder.

*rectClient*<br/>
'ndaki Düğmenin sınırlarını tanımlayan *PDC* parametresi tarafından belirtilen cihaz bağlamında bir dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Odak dikdörtgeninin görünümünü özelleştirmek için bu yöntemi geçersiz kılın.

##  <a name="onshowcolorpopup"></a>CMFCColorButton:: OnShowColorPopup

Açılan renk çubuğu görüntülenmeden önce çağırılır.

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="rebuildpalette"></a>CMFCColorButton:: RebuildPalette

`m_pPalette` Korunan veri üyesini belirtilen palete veya varsayılan sistem paletine başlatır.

```
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pPal*|'ndaki Mantıksal palet veya NULL işaretçisi. NULL ise, varsayılan sistem paleti kullanılır.|

##  <a name="setcolor"></a>CMFCColorButton:: SetColor

Düğmenin rengini belirtir.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Bir RGB değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="setcolorname"></a>CMFCColorButton:: SetColorName

Bir rengin adını belirtir.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Rengin RGB değeri.

*strName*<br/>
'ndaki Rengin adı.

### <a name="remarks"></a>Açıklamalar

Renk adları listesi uygulama başına geneldir. Sonuç olarak, bu yöntem parametrelerini [CMFCColorBar:: SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname)konumuna aktarır.

##  <a name="setcolumnsnumber"></a>CMFCColorButton:: SetColumns numarası

Kullanıcının renk seçimi işlemi sırasında kullanıcıya sunulan renkler tablosunda görüntülenen sütun sayısını tanımlar.

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Parametreler

*nColumns*<br/>
'ndaki Sütun sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Kullanıcı, bir açılan renk çubuğundan bir renk seçerek önceden tanımlanmış renklerin bir tablosunu görüntüler. Tablodaki sütun sayısını tanımlamak için bu yöntemi kullanın.

##  <a name="setdocumentcolors"></a>CMFCColorButton:: SetDocumentColors

Bir renk kümesi ve küme adı belirtir. Renk kümesi bir [CMFCColorBar sınıf](../../mfc/reference/cmfccolorbar-class.md) nesnesi kullanılarak görüntülenir.

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Belge renkleri kümesiyle görüntülenecek etiketi belirtir.

*lstColors*<br/>
'ndaki Bir RGB değerleri listesine başvuru.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCColorButton` nesne bir [CMFCColorBar sınıf](../../mfc/reference/cmfccolorbar-class.md) nesnesine aktarılan RGB değerlerinin listesini tutar. Renk çubuğu görüntülendiğinde, bu renkler etiketi *lpszLabel* parametresiyle belirtilen özel bir bölümde gösterilir.

##  <a name="setpalette"></a>CMFCColorButton:: SetPalette

Açılan Renk çubuğunda görüntülenecek standart renkleri belirtir.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parametreler

*pPalette*<br/>
'ndaki Renk paleti işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="sizetocontent"></a>CMFCColorButton:: SizeToContent

Düğme denetimini metin ve resmine uyacak şekilde yeniden boyutlandırır.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Parametreler

*bCalcOnly*<br/>
'ndaki Sıfır değilse, düğme denetiminin yeni boyutu hesaplanır ancak gerçek boyut değiştirilmez.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir düğme denetim boyutunu belirten nesne.`CSize`

### <a name="remarks"></a>Açıklamalar

##  <a name="updatecolor"></a>CMFCColorButton:: UpdateColor

Kullanıcı Color düğmesine tıkladığında görüntülenen renk çubuğundan bir renk seçtiğinde Framework tarafından çağırılır.

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Kullanıcı tarafından seçilen bir renk.

### <a name="remarks"></a>Açıklamalar

`UpdateColor` İşlev şu anda seçili olan düğmenin rengini değiştirir ve BN_CLICKED standart bildirimine sahip bir WM_COMMAND iletisi göndererek üst öğesine bildirir. Seçili rengi almak için [CMFCColorButton:: GetColor](#getcolor) metodunu kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)<br/>
[CMFCColorBar Sınıfı](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCColorButton:: OnShowColorPopup](#onshowcolorpopup)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[CPalette Sınıfı](../../mfc/reference/cpalette-class.md)<br/>
[CArray Sınıfı](../../mfc/reference/carray-class.md)<br/>
[CList Sınıfı](../../mfc/reference/clist-class.md)<br/>
[CString](../../atl-mfc-shared/reference/cstringt-class.md)
