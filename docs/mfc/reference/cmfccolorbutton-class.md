---
title: CMFCColorButton Sınıfı
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
ms.openlocfilehash: 21d05fd8e805467f1a7a77d20c81d5ba0401455e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367727"
---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton Sınıfı

`CMFCColorButton` [CMFCColorBar Sınıf](../../mfc/reference/cmfccolorbar-class.md) sınıfları bir renk seçici denetimi uygulamak için birlikte kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class CMFCColorButton : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Yeni `CMFCColorButton` bir nesne oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Normal renk düğmelerinin üzerine konumlandırılmış bir "otomatik" düğmeyi etkinleştirer ve devre dışı kılabilir. (Standart sistem otomatik düğmesi **Otomatik**olarak etiketlenmiştir.)|
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Normal renk düğmelerinin altına konumlandırılmış bir "diğer" düğmeyi etkinleştirer ve devre dışı kılabilir. (Standart sistem "diğer" düğmesi **Daha Fazla Renk**olarak etiketlenir.)|
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Geçerli otomatik rengi alır.|
|[CMFCColorButton::GetColor](#getcolor)|Düğmenin rengini alır.|
|[CMFCColorButton::SetColor](#setcolor)|Düğmenin rengini ayarlar.|
|[CMFCColorButton::SetColorName](#setcolorname)|Renk adı ayarlar.|
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Renk seçici iletişim kutusundaki sütun sayısını ayarlar.|
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Renk seçici iletişim kutusunda görüntülenen belgeye özgü renklerin listesini belirtir.|
|[CMFCColorButton::SetPalette](#setpalette)|Standart ekran renklerinden oluşan bir palet belirtir.|
|[CMFCColorButton::SizetoContent](#sizetocontent)|Metin ve görüntü boyutuna bağlı olarak düğme denetiminin boyutunu değiştirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Geçerli renk düğmesinin Windows XP'nin görsel stilinde görüntülenip görüntülenmediğini gösterir.|
|[CMFCColorButton::OnDraw](#ondraw)|Düğmenin bir görüntüsünü görüntülemek için çerçeve tarafından çağrılır.|
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Düğmenin kenarlığı görüntülemek için çerçeve tarafından çağrıldı.|
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Düğme nin odak noktası olduğunda odak dikdörtgenini görüntülemek için çerçeve tarafından çağrılır.|
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Renk seçici iletişim kutusu görüntülenmek üzereyken çerçeve tarafından çağrılır.|
|[CMFCColorButton::Yeniden Paletle'yi Yeniden Oluşturma](#rebuildpalette)|Korumalı veri `m_pPalette` üyesini belirtilen palete veya varsayılan sistem paletine başolarak laştırır.|
|[CMFCColorButton::UpdateColor](#updatecolor)|Kullanıcı renk seçici iletişim kutusunun paletinden bir renk seçtiğinde çerçeve tarafından çağrılır.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|`m_bAltColorDlg`|Bir Boolean. TRUE ise, diğer *düğme* tıklatıldığında veya FALSE varsa, sistem renk iletişim kutusu [CMFCColorDialog renk](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusunu görüntüler. Varsayılan değer TRUE'dur. Daha fazla bilgi için [cmfccolorbutton::EnableOtherButton](#enableotherbutton)bakın.|
|`m_bAutoSetFocus`|Bir Boolean. TRUE ise, çerçeve menü görüntülendiğinde veya FALSE ise renk menüsüne odak ayarlar, odak değişmez. Varsayılan değer TRUE'dur.|
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Renk düğmesi için özelleştirme modunun etkin olup olmadığını gösterir.|
|`m_Color`|[COLORREF](/windows/win32/gdi/colorref) değeri. Şu anda seçili rengi içerir.|
|`m_ColorAutomatic`|[COLORREF](/windows/win32/gdi/colorref) değeri. Şu anda seçili varsayılan rengi içerir.|
|`m_Colors`|[COLORREF](/windows/win32/gdi/colorref) değerlerinin [carray..](../../mfc/reference/carray-class.md) Şu anda kullanılabilir renkleri içerir.|
|`m_lstDocColors`|[COLORREF](/windows/win32/gdi/colorref) değerlerinin [clist'i.](../../mfc/reference/clist-class.md) Geçerli belge renklerini içerir.|
|`m_nColumns`|Bir tamsayı. Renk seçimi menüsünde renk ızgarasında görüntülenecek sütun sayısını içerir.|
|`m_pPalette`|[CPalette](../../mfc/reference/cpalette-class.md)için bir işaretçi . Geçerli renk seçimi menüsünde bulunan renkleri içerir.|
|`m_pPopup`|[CMFCColorPopupMenu Sınıf](../../mfc/reference/cmfccolorpopupmenu-class.md) nesnesine işaretçi. Renk düğmesini tıklattığınızda görüntülenen renk seçimi menüsü.|
|`m_strAutoColorText`|Bir ip. Renk seçimi menüsündeki "otomatik" düğmesinin etiketi.|
|`m_strDocColorsText`|Bir ip. Belge renklerini görüntüleyen renk seçimi menüsündeki düğmenin etiketi.|
|`m_strOtherText`|Bir ip. Renk seçimi menüsündeki "diğer" düğmesinin etiketi.|

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CMFCColorButton` sınıf bir renk seçici iletişim kutusunu açan bir basma düğmesi olarak görünür. Renk seçici iletişim kutusu küçük renk düğmeleri ve özel bir renk seçici görüntüler bir "diğer" düğmesi bir dizi içerir. (Standart sistem "diğer" düğmesi **Daha Fazla Renk**olarak etiketlenir.) Kullanıcı yeni bir renk seçtiğinde, `CMFCColorButton` nesne değişikliği yansıtır ve seçili rengi görüntüler.

Doğrudan kodunuzda veya **ClassWizard** aracını ve iletişim kutusu şablonunu kullanarak bir renk düğmesi denetimi oluşturun. Doğrudan bir renk düğmesi denetimi oluşturursanız, uygulamanıza bir `CMFCColorButton` değişken ekleyin `Create` ve ardından `CMFCColorButton` nesnenin oluşturucuve yöntemlerini arayın. **ClassWizard**kullanıyorsanız, uygulamanıza `CButton` bir değişken ekleyin ve sonra değişkenin `CButton` türünü `CMFCColorButton`'den ' e değiştirin

Renk seçici iletişim kutusu [(CMFCColorBar Class)](../../mfc/reference/cmfccolorbar-class.md) [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) yöntemi çerçeve `OnLButtonDown` olay işleyicisi çağırır tarafından görüntülenir. [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) yöntemi özel renk seçimini desteklemek için geçersiz kılınabilir.

Nesne, `CMFCColorButton` bir rengin WM_COMMAND göndererek üst öğesine renk değiştirdiğini belirtir | BN_CLICKED bildirimi. Üst öğe, geçerli rengi almak için [CMFCColorButton::GetColor](#getcolor) yöntemini kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemler kullanarak bir renk düğmesini `CMFCColorButton` nasıl yapılandırılabildiğini gösterir. Yöntemler renk düğmesinin rengini ve sütun sayısını ayarlar ve otomatik ve diğer düğmeleri etkinleştirin. Bu örnek Durum [Çubuğu Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolorbutton.h

## <a name="cmfccolorbuttoncmfccolorbutton"></a><a name="cmfccolorbutton"></a>CMFCColorButton::CMFCColorButton

Yeni `CMFCColorButton` bir nesne oluşturuyor.

```
CMFCColorButton();
```

## <a name="cmfccolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCColorButton::EnableAutomaticButton

Renk seçici denetiminin "otomatik" düğmesini etkinleştirin veya devre dışı düşürün ve otomatik (varsayılan) rengi ayarlayın.

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Otomatik düğmenin metnini belirtir.

*Colorautomatic*<br/>
[içinde] Otomatik düğmenin varsayılan rengini belirten bir RGB değeri.

*bEtkinleştir*<br/>
[içinde] Otomatik düğmenin etkin mi yoksa devre dışı mı olduğunu belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFCColorButton::EnableOtherButton

Normal renk düğmelerinin altında görünen "diğer" düğmesini etkinleştirin veya devre dışı edin.

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Düğmenin metnini belirtir.

*bAltColorDlg*<br/>
[içinde] [CmFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusunun mı yoksa kullanıcı düğmeyi tıklattığında sistem rengi iletişim kutusunun açılıp açılmadığını belirtir.

*bEtkinleştir*<br/>
[içinde] "Diğer" düğmesinin etkin mi yoksa devre dışı mı olduğunu belirtir.

### <a name="remarks"></a>Açıklamalar

Renk iletişim kutusunu görüntülemek için "diğer" düğmesini tıklatın. *bAltColorDlg* parametresi TRUE ise, [CMFCColorDialog Sınıfı](../../mfc/reference/cmfccolordialog-class.md) görüntülenir; aksi takdirde, sistem renk iletişim kutusu görüntülenir.

## <a name="cmfccolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFCColorButton::GetAutomaticColor

Geçerli otomatik (varsayılan) rengi alır.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli otomatik rengi temsil eden bir RGB değeri.

### <a name="remarks"></a>Açıklamalar

Geçerli otomatik renk [CMFCColorButton tarafından ayarlanır::EnableAutomaticButton](#enableautomaticbutton) yöntemi.

## <a name="cmfccolorbuttongetcolor"></a><a name="getcolor"></a>CMFCColorButton::GetColor

Şu anda seçili rengi alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

RGB değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbuttonisdrawxptheme"></a><a name="isdrawxptheme"></a>CMFCColorButton::IsDrawXPTheme

Geçerli renk düğmesinin Windows XP'nin görsel stilinde görüntülenip görüntülenmediğini gösterir.

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görsel stiller destekleniyorsa ve geçerli renk düğmesi Windows XP'nin görsel stilinde görüntüleniyorsa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfccolorbuttonm_benabledincustomizemode"></a><a name="m_benabledincustomizemode"></a>CMFCColorButton::m_bEnabledInCustomizeMode

Renk düğmesini özelleştirme moduna ayarlar.

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>Açıklamalar

Özelleştirme iletişim kutusunun sayfasına renk düğmesi eklemeniz gerekiyorsa (veya özelleştirme sırasında kullanıcının başka bir renk seçimi `m_bEnabledInCustomizeMode` yapmasına izin vermek), üyeyi TRUE olarak ayarlayarak düğmeyi etkinleştirin. Varsayılan olarak, bu üye FALSE olarak ayarlanır.

## <a name="cmfccolorbuttonondraw"></a><a name="ondraw"></a>CMFCColorButton::OnDraw

Düğmenin bir görüntüsünü işlemek için çerçeve tarafından çağrılır.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğmenin görüntüsünü işlemek için kullanılan aygıt bağlamını işaret ediyor.

*Rect*<br/>
[içinde] Düğmeyi sınırlayan bir dikdörtgen.

*uiState*<br/>
[içinde] Düğmenin görsel durumunu belirtir.

### <a name="remarks"></a>Açıklamalar

İşleme işlemini özelleştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfccolorbuttonondrawborder"></a><a name="ondrawborder"></a>CMFCColorButton::OnDrawBorder

Düğmenin kenarlığı görüntülemek için çerçeve tarafından çağrılır.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Kenarlığı çizmek için kullanılan aygıt bağlamını işaret edin.

*rectClient*<br/>
[içinde] Çizilecek düğmenin sınırlarını tanımlayan *pDC* parametretarafından belirtilen aygıt bağlamında bir dikdörtgen.

*uiState*<br/>
[içinde] Düğmenin görsel durumunu belirtir.

### <a name="remarks"></a>Açıklamalar

Renk düğmesinin kenarlık görünümünü özelleştirmek için bu işlevi geçersiz kılın.

## <a name="cmfccolorbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCColorButton::OnDrawFocusRect

Düğme odaklandığında bir odak dikdörtgeni görüntülemek için çerçeve tarafından çağrılır.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Odak dikdörtgeni çizmek için kullanılan aygıt bağlamını işaret edin.

*rectClient*<br/>
[içinde] Düğmenin sınırlarını tanımlayan *pDC* parametresi tarafından belirtilen aygıt bağlamında bir dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Odak dikdörtgeninin görünümünü özelleştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfccolorbuttononshowcolorpopup"></a><a name="onshowcolorpopup"></a>CMFCColorButton::OnShowColorPopup

Açılır renk çubuğu görüntülenmeden önce çağrılır.

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbuttonrebuildpalette"></a><a name="rebuildpalette"></a>CMFCColorButton::Yeniden Paletle'yi Yeniden Oluşturma

Korumalı veri `m_pPalette` üyesini belirtilen palete veya varsayılan sistem paletine başolarak laştırır.

```
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pPal*|[içinde] Mantıksal bir palet veya NULL için bir işaretçi. NULL ise, varsayılan sistem paleti kullanılır.|

## <a name="cmfccolorbuttonsetcolor"></a><a name="setcolor"></a>CMFCColorButton::SetColor

Düğmenin rengini belirtir.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] RGB değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbuttonsetcolorname"></a><a name="setcolorname"></a>CMFCColorButton::SetColorName

Rengin adını belirtir.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] Rengin RGB değeri.

*strName*<br/>
[içinde] Rengin adı.

### <a name="remarks"></a>Açıklamalar

Renk adları listesi uygulama başına geneldir. Sonuç olarak, bu yöntem parametrelerini [CMFCColorBar'a aktarMaktadır::SetColorName.](../../mfc/reference/cmfccolorbar-class.md#setcolorname)

## <a name="cmfccolorbuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCColorButton::SetColumnsNumber

Kullanıcının renk seçimi işlemi sırasında kullanıcıya sunulan renkler tablosunda görüntülenen sütun sayısını tanımlar.

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Parametreler

*nSütunlar*<br/>
[içinde] Sütun sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Kullanıcı, önceden tanımlanmış renklerden oluşan bir tablo görüntüleyen açılır renk çubuğundan bir renk seçebilir. Tablodaki sütun sayısını tanımlamak için bu yöntemi kullanın.

## <a name="cmfccolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFCColorButton::SetDocumentColors

Bir renk kümesini ve kümenin adını belirtir. Renk kümesi [CMFCColorBar Sınıf](../../mfc/reference/cmfccolorbar-class.md) nesnesi kullanılarak görüntülenir.

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Belge renkleri kümesiyle görüntülenecek etiketi belirtir.

*lstRenkler*<br/>
[içinde] RGB değerleri listesine başvuru.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCColorButton` [nesne, CMFCColorBar Sınıfı](../../mfc/reference/cmfccolorbar-class.md) nesnesine aktarılan RGB değerlerinin listesini tutar. Renk çubuğu görüntülendiğinde, bu renkler *lpszLabel* parametresi tarafından etiketi belirtilen özel bir bölümde gösterilir.

## <a name="cmfccolorbuttonsetpalette"></a><a name="setpalette"></a>CMFCColorButton::SetPalette

Açılır renk çubuğunda görüntülenecek standart renkleri belirtir.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parametreler

*pPalette*<br/>
[içinde] Renk paletine işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbuttonsizetocontent"></a><a name="sizetocontent"></a>CMFCColorButton::SizetoContent

Düğme denetimini metin ve resmine uyacak şekilde yeniden boyutlandırın.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Parametreler

*bCalcSadece*<br/>
[içinde] Sıfır değilse, düğme denetiminin yeni boyutu hesaplanır, ancak gerçek boyutu değiştirilmez.

### <a name="return-value"></a>Dönüş Değeri

Yeni `CSize` bir düğme denetimi boyutu belirten bir nesne.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbuttonupdatecolor"></a><a name="updatecolor"></a>CMFCColorButton::UpdateColor

Kullanıcı renk düğmesini tıklattığında görüntüleyen renk çubuğundan bir renk seçtiğinde çerçeve tarafından çağrılır.

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] Kullanıcı tarafından seçilen bir renk.

### <a name="remarks"></a>Açıklamalar

İşlev, `UpdateColor` şu anda seçili düğmenin rengini değiştirir ve BN_CLICKED standart bildirimiçeren bir WM_COMMAND ileti göndererek üst öğesini bildirir. Seçilen rengi almak için [CMFCColorButton::GetColor](#getcolor) yöntemini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)<br/>
[CMFCColorBar Sınıfı](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)<br/>
[Colorref](/windows/win32/gdi/colorref)<br/>
[CPalette Sınıfı](../../mfc/reference/cpalette-class.md)<br/>
[CArray Sınıfı](../../mfc/reference/carray-class.md)<br/>
[CList Sınıfı](../../mfc/reference/clist-class.md)<br/>
[Cstring](../../atl-mfc-shared/reference/cstringt-class.md)
