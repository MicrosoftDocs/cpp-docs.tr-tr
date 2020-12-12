---
description: 'Daha fazla bilgi edinin: CMFCRibbonColorButton sınıfı'
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
ms.openlocfilehash: a350339559febdc9346dcf8b342d274d00bab391
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293722"
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton sınıfı

`CMFCRibbonColorButton`Sınıfı, şerit çubuğuna ekleyebileceğiniz bir renk düğmesi uygular. Şerit rengi düğmesi bir veya daha fazla renk paletleri içeren bir açılan menü görüntüler.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonColorButton:: CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonColorButton:: AddColorsGroup](#addcolorsgroup)|Normal renk alanına bir renk grubu ekler.|
|[CMFCRibbonColorButton:: EnableAutomaticButton](#enableautomaticbutton)|**Otomatik** düğmenin etkinleştirilip etkinleştirilmeyeceğini belirtir.|
|[CMFCRibbonColorButton:: EnableOtherButton](#enableotherbutton)|**Diğer** düğmeye izin vermez.|
|[CMFCRibbonColorButton:: GetAutomaticColor](#getautomaticcolor)||
|[CMFCRibbonColorButton:: GetColor](#getcolor)|Şu anda seçili rengi döndürür.|
|[CMFCRibbonColorButton:: GetColorBoxSize](#getcolorboxsize)|Renk çubuğunda görünen renk öğelerinin boyutunu döndürür.|
|[CMFCRibbonColorButton:: GetColumns](#getcolumns)||
|[CMFCRibbonColorButton:: Gethighaçıklatedcolor](#gethighlightedcolor)|Açılan renk paletindeki seçili olan öğenin rengini döndürür.|
|[CMFCRibbonColorButton:: RemoveAllColorGroups](#removeallcolorgroups)|Normal renk alanından tüm renk gruplarını kaldırır.|
|[CMFCRibbonColorButton:: SetColor](#setcolor)|Normal renk alanından bir renk seçer.|
|[CMFCRibbonColorButton:: SetColorBoxSize](#setcolorboxsize)|Renk çubuğunda görünen tüm renk öğelerinin boyutunu ayarlar.|
|[CMFCRibbonColorButton:: SetColorName](#setcolorname)||
|[CMFCRibbonColorButton:: SetColumns](#setcolumns)||
|[CMFCRibbonColorButton:: SetDocumentColors](#setdocumentcolors)|Belge renk alanında görüntülenecek RGB değerlerinin listesini belirtir.|
|[CMFCRibbonColorButton:: SetPalette](#setpalette)||
|[CMFCRibbonColorButton:: UpdateColor](#updatecolor)||

## <a name="remarks"></a>Açıklamalar

Şerit rengi düğmesi bir Kullanıcı ona bastığında bir renk çubuğu görüntüler. Varsayılan olarak, bu renk çubuğu normal renk alanı adlı bir renk seçim paleti içerir. İsteğe bağlı olarak, renk çubuğu, kullanıcının varsayılan bir renk seçmesine izin veren bir **Otomatik** düğme ve ek renkler içeren bir açılan renk paleti görüntüleyen **diğer** bir düğme görüntüleyebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCRibbonColorButton` . Örnek, bir nesnenin nasıl oluşturulduğunu `CMFCRibbonColorButton` , büyük görüntünün nasıl ayarlanacağını, **Otomatik** düğmeyi nasıl etkinleştireceğinizi, **diğer** düğmeyi etkinleştirir, sütun sayısını ayarlamayı, Renk çubuğunda görünen tüm renk öğelerinin boyutunu ayarlamayı, normal renk alanına bir renk grubu eklemenizi ve belge renk alanında görüntülenecek RGB değerlerinin bir listesini belirtmenizi gösterir. Bu kod parçacığı, [Çizim istemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)

[Cmfcribbongalerisi](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncolorbutton. h

## <a name="cmfcribboncolorbuttonaddcolorsgroup"></a><a name="addcolorsgroup"></a> CMFCRibbonColorButton:: AddColorsGroup

Normal renk alanına bir renk grubu ekler.

```cpp
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
'ndaki Grup adı.

*lstColors*<br/>
'ndaki Renklerin listesi.

*bContiguousColumns*<br/>
'ndaki Renk öğelerinin grupta nasıl görüntülendiğini denetler. TRUE ise, renk öğeleri dikey bir boşluk olmadan çizilir. FALSE ise, renk öğeleri dikey bir boşluk ile çizilir.

### <a name="remarks"></a>Açıklamalar

Renk açılır listesini birkaç renk grubunu görüntüleyecek şekilde bu işlevi kullanın. Renklerin grup içinde nasıl görüntülendiğini denetleyebilirsiniz.

## <a name="cmfcribboncolorbuttoncmfcribboncolorbutton"></a><a name="cmfcribboncolorbutton"></a> CMFCRibbonColorButton:: CMFCRibbonColorButton

Bir `CMFCRibbonColorButton` nesnesi oluşturur.

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

*NID*<br/>
'ndaki Kullanıcı düğmeye tıkladığında yürütülecek komutun komut KIMLIĞINI belirtir.

*lpszText*<br/>
'ndaki Düğmede görüntülenecek metni belirtir.

*Nsmallımageındex*<br/>
'ndaki Düğme üzerinde görünecek küçük görüntünün sıfır tabanlı dizini.

*Renk*<br/>
'ndaki Düğmenin rengi (varsayılan olarak siyah olur).

*bSimpleButtonLook*<br/>
'ndaki TRUE ise düğme basit bir dikdörtgen olarak çizilir.

*Nlargeımageındex*<br/>
'ndaki Düğme üzerinde görünecek büyük görüntünün sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCRibbonColorButton:: EnableAutomaticButton

**Otomatik** düğmenin etkinleştirilip etkinleştirilmeyeceğini belirtir.

```cpp
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
'ndaki **Otomatik** düğmenin etiketi.

*colorAutomatic*<br/>
'ndaki **Otomatik** düğmenin varsayılan rengini BELIRTEN bir RGB değeri.

*bEnable*<br/>
'ndaki **Otomatik** düğme etkinse doğru; Devre dışıysa yanlış.

*lpszToolTip*<br/>
'ndaki **Otomatik** düğmenin araç ipucu.

*bOnTop*<br/>
'ndaki **Otomatik** düğmenin en üstte, renk paletinden önce olup olmadığını belirtir.

*bDrawBorder*<br/>
'ndaki Uygulama, şerit rengi düğmesindeki renk çubuğunun etrafında bir kenarlık çizdiğinde TRUE. Renk çubuğu şu anda seçili rengi görüntüler. Uygulama bir kenarlık çizmezse yanlış

## <a name="cmfcribboncolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a> CMFCRibbonColorButton:: EnableOtherButton

**Diğer** düğmeye izin vermez.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
Düğmenin etiketi.

*lpszToolTip*<br/>
**Diğer** düğmenin araç ipucu metni.

### <a name="remarks"></a>Açıklamalar

**Diğer** düğme, renklerin grubunun altında görüntülenen düğmedir. Kullanıcı **diğer** düğmeye tıkladığında bir renk iletişim kutusu görüntüler.

## <a name="cmfcribboncolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a> CMFCRibbonColorButton:: GetAutomaticColor

Geçerli otomatik düğme rengini alır.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli otomatik düğme rengini temsil eden bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Otomatik düğme rengi `colorAutomatic` yöntemine geçirilen parametre tarafından ayarlanır `CMFCRibbonColorButton::EnableAutomaticButton` .

## <a name="cmfcribboncolorbuttongetcolor"></a><a name="getcolor"></a> CMFCRibbonColorButton:: GetColor

Şu anda seçili rengi döndürür.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeye tıklayarak seçilen renk.

## <a name="cmfcribboncolorbuttongetcolorboxsize"></a><a name="getcolorboxsize"></a> CMFCRibbonColorButton:: GetColorBoxSize

Renk çubuğunda görünen renk öğelerinin boyutunu döndürür.

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan renk paletindeki renk düğmelerinin boyutu.

## <a name="cmfcribboncolorbuttongetcolumns"></a><a name="getcolumns"></a> CMFCRibbonColorButton:: GetColumns

Şerit rengi düğmesinin Galeri görüntüsüne ait bir satırdaki öğelerin sayısını alır.

```
int GetColumns() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her satırdaki simgelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncolorbuttongethighlightedcolor"></a><a name="gethighlightedcolor"></a> CMFCRibbonColorButton:: Gethighaçıklatedcolor

Açılır renk paletindeki seçili olan öğenin rengini döndürür.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır renk paletindeki seçili olan öğenin rengi.

## <a name="cmfcribboncolorbuttonremoveallcolorgroups"></a><a name="removeallcolorgroups"></a> CMFCRibbonColorButton:: RemoveAllColorGroups

Normal renk alanından tüm renk gruplarını kaldırır.

```cpp
void RemoveAllColorGroups();
```

## <a name="cmfcribboncolorbuttonsetcolor"></a><a name="setcolor"></a> CMFCRibbonColorButton:: SetColor

Normal renk alanından bir renk seçer.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Ayarlanacak bir renk.

## <a name="cmfcribboncolorbuttonsetcolorboxsize"></a><a name="setcolorboxsize"></a> CMFCRibbonColorButton:: SetColorBoxSize

Renk çubuğunda görünen tüm renk öğelerinin boyutunu ayarlar.

```cpp
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>Parametreler

*Boyut kutusu*<br/>
'ndaki Renk paletindeki renk düğmelerinin yeni boyutu.

## <a name="cmfcribboncolorbuttonsetcolorname"></a><a name="setcolorname"></a> CMFCRibbonColorButton:: SetColorName

Belirtilen renk için yeni bir ad ayarlar.

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Rengin RGB değeri.

*strName*<br/>
'ndaki Belirtilen rengin yeni adı.

### <a name="remarks"></a>Açıklamalar

Çağırdığı için `CMFCColorBar::SetColorName` , bu yöntem uygulamanızdaki tüm nesnelerde belirtilen rengin adını değiştirir `CMFCColorBar` .

## <a name="cmfcribboncolorbuttonsetcolumns"></a><a name="setcolumns"></a> CMFCRibbonColorButton:: SetColumns

Kullanıcının renk seçimi sürecinde kullanıcıya sunulan renkler tablosunda görüntülenen sütun sayısını ayarlar.

```cpp
void SetColumns(int nColumns);
```

### <a name="parameters"></a>Parametreler

*nColumns*<br/>
'ndaki Her satırda görüntülenecek renk simgeleri sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a> CMFCRibbonColorButton:: SetDocumentColors

Belge renk alanında görüntülenecek RGB değerlerinin listesini belirtir.

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Belge renkleriyle görüntülenecek metin.

*lstColors*<br/>
'ndaki Bir RGB değerleri listesine başvuru.

## <a name="cmfcribboncolorbuttonsetpalette"></a><a name="setpalette"></a> CMFCRibbonColorButton:: SetPalette

Renk düğmesinin görüntülediği renk tablosunda görüntülenecek standart renkleri belirtir.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parametreler

*pPalette*<br/>
'ndaki Renk paleti işaretçisi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncolorbuttonupdatecolor"></a><a name="updatecolor"></a> CMFCRibbonColorButton:: UpdateColor

Kullanıcı Color düğmesine tıkladığında görünen renk tablosundan bir renk seçtiğinde Framework tarafından çağırılır.

```cpp
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Kullanıcı tarafından seçilen bir renk.

### <a name="remarks"></a>Açıklamalar

`CMFCRibbonColorButton::UpdateColor`Yöntemi şu anda seçili olan düğmenin rengini değiştirir ve BN_CLICKED standart bildirimiyle WM_COMMAND bir ileti göndererek üst öğesine bildirir. Seçili rengi almak için [CMFCRibbonColorButton:: GetColor](#getcolor) metodunu kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery sınıfı](../../mfc/reference/cmfcribbongallery-class.md)
