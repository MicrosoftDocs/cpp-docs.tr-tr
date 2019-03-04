---
title: CMFCRibbonColorButton sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
ms.openlocfilehash: a7901619110652423a2ab00d8088d6b9213fe202
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266283"
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton sınıfı

`CMFCRibbonColorButton` Sınıfı bir Şerit çubuğuna ekleyebileceğiniz bir renk düğmesi uygular. Şerit rengi düğmesi, bir veya daha fazla renk paleti içeren bir açılan menü görüntüler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Renkler bir grup için normal renk alanı ekler.|
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Belirtir olup olmadığını **otomatik** düğmesi etkinleşir.|
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Sağlar **diğer** düğmesi.|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[CMFCRibbonColorButton::GetColor](#getcolor)|Seçili renk döndürür.|
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Renk çubuğunda görünen rengi öğelerin boyutunu döndürür.|
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Seçili öğenin rengini, açılan renk paletinde döndürür.|
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Tüm renk grupları normal renk alanından kaldırır.|
|[CMFCRibbonColorButton::SetColor](#setcolor)|Bir renk normal renk alanından seçer.|
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Renk çubuğunda görünen rengi öğelerin boyutunu ayarlar.|
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|RGB değerleri belge renk alanında görüntülemek için bir listesini belirtir.|
|[CMFCRibbonColorButton::SetPalette](#setpalette)||
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||

## <a name="remarks"></a>Açıklamalar

Şerit rengi düğmesi, bir kullanıcının bastığında bir renk çubuğu görüntülenir. Varsayılan olarak, bu renk çubuğu normal renk alanını adlı bir renk seçimi paletini içerir. İsteğe bağlı olarak, renk çubuğu görüntüleyebilirsiniz bir **otomatik** varsayılan rengi seçmesini sağlayan bir düğme ve bir **diğer** ek içeren bir açılan renk paletini görüntüleyen düğme.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCRibbonColorButton` sınıfı. Örnek nasıl oluşturulacağını gösterir. bir `CMFCRibbonColorButton` nesne, büyük resmi ayarlama, etkinleştirme **otomatik** düğmesi, etkinleştirme **diğer** düğmesi, sütun sayısını ayarlayın, renk öğelerin boyutunu ayarlayın renk çubuğunda, renkler grubu normal renk alan eklemek ve RGB değerleri belge renk alanında görüntülemek için bir listesini belirtin. Bu kod parçacığı parçasıdır [çizmek istemci örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxribboncolorbutton.h

##  <a name="addcolorsgroup"></a>  CMFCRibbonColorButton::AddColorsGroup

Renkler bir grup için normal renk alanı ekler.

```
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
[in] Grup adı.

*lstColors*<br/>
[in] Renkleri listesi.

*bContiguousColumns*<br/>
[in] Gruptaki öğelerin nasıl görüntüleneceğini denetler. TRUE ise, renk öğeler olmadan dikey bir aralık çizilir. FALSE ise, dikey bir aralıklı renk öğeleri çizilir.

### <a name="remarks"></a>Açıklamalar

Renk açılan yapmak için bu işlevi kullanın renkleri birkaç gruplarını görüntüler. Renkleri grubunda nasıl görüntüleneceğini denetleyebilirsiniz.

##  <a name="cmfcribboncolorbutton"></a>  CMFCRibbonColorButton::CMFCRibbonColorButton

Oluşturur bir `CMFCRibbonColorButton` nesne.

```
CMFCRibbonColorButton();

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex,
    COLORREF color = RGB(0, 0, 0));

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    BOOL bSimpleButtonLook,
    int nSmallImageIndex,
    int nLargeImageIndex,
    COLORREF color = RGB(0, 0, 0));
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
[in] Bir kullanıcı düğmeye tıkladığında çalıştırılacak komutu komut Kimliğini belirtir.

*lpszText*<br/>
[in] Çubuğunda görüntülenecek metni belirtir.

*nSmallImageIndex*<br/>
[in] Düğme üzerinde görünen küçük resmi sıfır tabanlı dizini.

*Renk*<br/>
[in] ' % S'düğmesini (varsayılan olarak siyahtır) rengi.

*bSimpleButtonLook*<br/>
[in] TRUE ise, düğme basit bir dikdörtgen çizilir.

*nLargeImageIndex*<br/>
[in] Düğme üzerinde görünen büyük resim sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="enableautomaticbutton"></a>  CMFCRibbonColorButton::EnableAutomaticButton

Belirtir olup olmadığını **otomatik** düğmesi etkinleşir.

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE,
    LPCTSTR lpszToolTip=NULL,
    BOOL bOnTop=TRUE,
    BOOL bDrawBorder=FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
[in] Etiketi **otomatik** düğmesi.

*colorAutomatic*<br/>
[in] Belirten bir RGB değeri **otomatik** düğmenin varsayılan rengi.

*bSistemlerde*<br/>
[in] TRUE ise **otomatik** düğmesi etkin; Değilse FALSE.

*lpszToolTip*<br/>
[in] Araç İpucu **otomatik** düğmesi.

*bOnTop*<br/>
[in] Belirtir olup olmadığını **otomatik** renk paletini önce üst düğmesidir.

*bDrawBorder*<br/>
[in] Uygulama, Şerit rengi düğmesi üzerinde renk çubuğu çevresine bir kenarlık çizer TRUE. Seçili renk renk çubuğu görüntüler. YANLIŞ uygulama bir kenarlık çizmek değil

##  <a name="enableotherbutton"></a>  CMFCRibbonColorButton::EnableOtherButton

Sağlar **diğer** düğmesi.

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
Düğmenin etiket.

*lpszToolTip*<br/>
Araç ipucu metnini **diğer** düğmesi.

### <a name="remarks"></a>Açıklamalar

**Diğer** düğmesidir renkleri grubunu görüntülenen düğme. Kullanıcı tıkladığında **diğer** düğmesi, bir renk iletişim kutusu görüntüler.

##  <a name="getautomaticcolor"></a>  CMFCRibbonColorButton::GetAutomaticColor

Geçerli otomatik düğme rengi alır.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli otomatik düğme rengi temsil eden bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Otomatik düğme rengi belirlediği `colorAutomatic` geçirilen `CMFCRibbonColorButton::EnableAutomaticButton` yöntemi.

##  <a name="getcolor"></a>  CMFCRibbonColorButton::GetColor

Seçili renk döndürür.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmesine tıklayarak seçili rengi.

##  <a name="getcolorboxsize"></a>  CMFCRibbonColorButton::GetColorBoxSize

Renk çubuğunda görünen rengi öğelerin boyutunu döndürür.

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan renk paletindeki renk düğmelerinin boyutu.

##  <a name="getcolumns"></a>  CMFCRibbonColorButton::GetColumns

Şerit rengi düğmenin galeri görünen bir satırda öğe sayısını alır.

```
int GetColumns() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her satırda simgelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="gethighlightedcolor"></a>  CMFCRibbonColorButton::GetHighlightedColor

Seçili öğenin rengini, açılan renk paletinde döndürür.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili olan öğenin açılan renk paletindeki rengi.

##  <a name="removeallcolorgroups"></a>  CMFCRibbonColorButton::RemoveAllColorGroups

Tüm renk grupları normal renk alanından kaldırır.

```
void RemoveAllColorGroups();
```

##  <a name="setcolor"></a>  CMFCRibbonColorButton::SetColor

Bir renk normal renk alanından seçer.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[in] Ayarlamak için bir renk.

##  <a name="setcolorboxsize"></a>  CMFCRibbonColorButton::SetColorBoxSize

Renk çubuğunda görünen rengi öğelerin boyutunu ayarlar.

```
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>Parametreler

*sizeBox*<br/>
[in] Renk düğmeleri renk paletindeki yeni boyutu.

##  <a name="setcolorname"></a>  CMFCRibbonColorButton::SetColorName

Belirtilen bir renk için yeni bir ad belirler.

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[in] Renk RGB değeri.

*strName*<br/>
[in] Belirtilen "rengin" yeni adı.

### <a name="remarks"></a>Açıklamalar

Bunun çağırdığı `CMFCColorBar::SetColorName`, bu yöntem tüm belirtilen "rengin" adını değiştirir `CMFCColorBar` uygulamanızdaki nesneleri.

##  <a name="setcolumns"></a>  CMFCRibbonColorButton::SetColumns

Kullanıcının renk seçimi işlemi sırasında kullanıcıya renk tablosundaki görüntülenen sütunların sayısını ayarlar.

```
void SetColumns(int nColumns);
```

### <a name="parameters"></a>Parametreler

*nColumns*<br/>
[in] Her satırda görüntülenecek renk simgelerinin genişliğini sayısı.

### <a name="remarks"></a>Açıklamalar

##  <a name="setdocumentcolors"></a>  CMFCRibbonColorButton::SetDocumentColors

RGB değerleri belge renk alanında görüntülemek için bir listesini belirtir.

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
[in] Belge renkleri görüntülenecek metin.

*lstColors*<br/>
[in] RGB değerleri listesi başvuru.

##  <a name="setpalette"></a>  CMFCRibbonColorButton::SetPalette

Standart renkler görüntüler renk düğmesinin renk tablosundaki görüntülemek için belirtir.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parametreler

*pPalette*<br/>
[in] Renk paleti işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="updatecolor"></a>  CMFCRibbonColorButton::UpdateColor

Kullanıcı kullanıcı renk düğmesine tıkladığında görüntülenir renk tablosundan bir renk seçtiğinde framework tarafından çağırılır.

```
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[in] Kullanıcının seçtiği bir renk.

### <a name="remarks"></a>Açıklamalar

`CMFCRibbonColorButton::UpdateColor` Yöntemi şu anda seçili düğmenin rengini değiştirir ve kendi üst WM_COMMAND ileti ile BN_CLICKED standart bildirim göndererek size bildirir. Kullanım [CMFCRibbonColorButton::GetColor](#getcolor) seçilen rengin almak için yöntemi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery Sınıfı](../../mfc/reference/cmfcribbongallery-class.md)
