---
title: CMFCRibbonColorButton Sınıfı
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
ms.openlocfilehash: 528b883d75889589c7021f462324dd9dcb71be25
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754849"
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton Sınıfı

Sınıf, `CMFCRibbonColorButton` şerit çubuğuna ekleyebileceğiniz bir renk düğmesi uygular. Şerit renk düğmesi, bir veya daha fazla renk paleti içeren açılır menüyü görüntüler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Normal renk alanına bir renk grubu ekler.|
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|**Otomatik** düğmenin etkin olup olmadığını belirtir.|
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|**Diğer** düğmeyi etkinleştiri.|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[CMFCRibbonColorButton::GetColor](#getcolor)|Şu anda seçili rengi döndürür.|
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Renk çubuğunda görünen renk öğelerinin boyutunu döndürür.|
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Pop-up renk paletinde şu anda seçili öğenin rengini verir.|
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Tüm renk gruplarını normal renk alanından kaldırır.|
|[CMFCRibbonColorButton::SetColor](#setcolor)|Normal renk alanından bir renk seçer.|
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Renk çubuğunda görünen tüm renk öğelerinin boyutunu ayarlar.|
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Belge renk alanında görüntülenecek RGB değerlerinin listesini belirtir.|
|[CMFCRibbonColorButton::SetPalette](#setpalette)||
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||

## <a name="remarks"></a>Açıklamalar

Şerit renk düğmesi, kullanıcı bastığında bir renk çubuğu görüntüler. Varsayılan olarak, bu renk çubuğu normal renk alanı olarak adlandırılan bir renk seçim paleti içerir. İsteğe bağlı olarak, renk çubuğu, kullanıcının varsayılan bir renk seçmesine olanak tanıyan **Otomatik** düğmeyi ve ek renkler içeren bir açılır renk paleti görüntüleyen **diğer** düğmeyi görüntüleyebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCRibbonColorButton` nasıl kullanılacağını göstermektedir. Örnek, bir `CMFCRibbonColorButton` nesnenin nasıl oluşturulabildiğini, büyük görüntüyü nasıl ayarladığını, **Otomatik** düğmesini etkinleştirme, **Diğer** düğmesini etkinleştirme, sütun sayısını ayarlama, renk çubuğunda görünen tüm renk öğelerinin boyutunu ayarlama, normal renk alanına bir renk grubu ekleme ve belge renk alanında görüntülenecek RGB değerlerinin listesini belirtmeyi gösterir. Bu kod snippet [Çekme İstemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGaleri](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncolorbutton.h

## <a name="cmfcribboncolorbuttonaddcolorsgroup"></a><a name="addcolorsgroup"></a>CMFCRibbonColorButton::AddColorsGroup

Normal renk alanına bir renk grubu ekler.

```cpp
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
[içinde] Grup adı.

*lstRenkler*<br/>
[içinde] Renk listesi.

*bContiguousColumns*<br/>
[içinde] Renk öğelerinin grupta nasıl görüntüleneceğini denetler. TRUE ise, renk öğeleri dikey bir boşluk olmadan çizilir. FALSE ise, renk öğeleri dikey bir boşlukla çizilir.

### <a name="remarks"></a>Açıklamalar

Renk açılır penceresini çeşitli renk grupları görüntülemek için bu işlevi kullanın. Renklerin grupta nasıl görüntüleneceğini denetleyebilirsiniz.

## <a name="cmfcribboncolorbuttoncmfcribboncolorbutton"></a><a name="cmfcribboncolorbutton"></a>CMFCRibbonColorButton::CMFCRibbonColorButton

Bir `CMFCRibbonColorButton` nesne inşa eder.

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

*Nıd*<br/>
[içinde] Bir kullanıcı düğmeyi tıklattığında yürütülecek komutun komut kimliğini belirtir.

*lpszMetin*<br/>
[içinde] Düğmede görünecek metni belirtir.

*nSmallImageIndex*<br/>
[içinde] Düğmede görünecek küçük görüntünün sıfır tabanlı dizini.

*color*<br/>
[içinde] Düğmenin rengi (varsayılan olarak siyah).

*bSimpleButtonLook*<br/>
[içinde] TRUE ise, düğme basit bir dikdörtgen olarak çizilir.

*nLargeImageIndex*<br/>
[içinde] Düğmede görünecek büyük görüntünün sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCRibbonColorButton::EnableAutomaticButton

**Otomatik** düğmenin etkin olup olmadığını belirtir.

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

*lpszEtiket*<br/>
[içinde] **Otomatik** düğmesinin etiketi.

*Colorautomatic*<br/>
[içinde] **Otomatik** düğmenin varsayılan rengini belirten bir RGB değeri.

*bEtkinleştir*<br/>
[içinde] **Otomatik** düğmesi etkinse TRUE; Devre dışı bırakılırsa YANLIŞ.

*lpszToolTip*<br/>
[içinde] **Otomatik** düğmesinin araç ucu.

*bOnTop*<br/>
[içinde] **Otomatik** düğmenin renk paletinden önce en üstte olup olmadığını belirtir.

*bDrawBorder*<br/>
[içinde] Uygulama şerit renk düğmesindeki renk çubuğunun etrafına kenarlık çiziyorsa DOĞRU. Renk çubuğu, şu anda seçili rengi görüntüler. Uygulama kenarlık çizmiyorsa YANLIŞ

## <a name="cmfcribboncolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFCRibbonColorButton::EnableOtherButton

**Diğer** düğmeyi etkinleştiri.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
Düğmenin etiketi.

*lpszToolTip*<br/>
**Diğer** düğmeiçin araç ipucu metni.

### <a name="remarks"></a>Açıklamalar

**Diğer** düğme, renk grubunun altında görüntülenen düğmedir. Kullanıcı **Diğer** düğmesini tıklattığında, bir renk iletişim kutusu görüntüler.

## <a name="cmfcribboncolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFCRibbonColorButton::GetAutomaticColor

Geçerli otomatik düğme rengini alır.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli otomatik düğme rengini temsil eden bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Otomatik düğme rengi `colorAutomatic` `CMFCRibbonColorButton::EnableAutomaticButton` yönteme geçirilen parametre ile ayarlanır.

## <a name="cmfcribboncolorbuttongetcolor"></a><a name="getcolor"></a>CMFCRibbonColorButton::GetColor

Şu anda seçili rengi döndürür.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeyi tıklatarak seçilen renk.

## <a name="cmfcribboncolorbuttongetcolorboxsize"></a><a name="getcolorboxsize"></a>CMFCRibbonColorButton::GetColorBoxSize

Renk çubuğunda görünen renk öğelerinin boyutunu döndürür.

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır renk paletindeki renk düğmelerinin boyutu.

## <a name="cmfcribboncolorbuttongetcolumns"></a><a name="getcolumns"></a>CMFCRibbonColorButton::GetColumns

Şerit renk düğmesinin galeri ekranının bir satırdaki öğe sayısını alır.

```
int GetColumns() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her satırdaki simge sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncolorbuttongethighlightedcolor"></a><a name="gethighlightedcolor"></a>CMFCRibbonColorButton::GetHighlightedColor

Açılır renk paletinde şu anda seçili öğenin rengini verir.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır renk paletinde şu anda seçili öğenin rengi.

## <a name="cmfcribboncolorbuttonremoveallcolorgroups"></a><a name="removeallcolorgroups"></a>CMFCRibbonColorButton::RemoveAllColorGroups

Tüm renk gruplarını normal renk alanından kaldırır.

```cpp
void RemoveAllColorGroups();
```

## <a name="cmfcribboncolorbuttonsetcolor"></a><a name="setcolor"></a>CMFCRibbonColorButton::SetColor

Normal renk alanından bir renk seçer.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] Ayarlanan bir renk.

## <a name="cmfcribboncolorbuttonsetcolorboxsize"></a><a name="setcolorboxsize"></a>CMFCRibbonColorButton::SetColorBoxSize

Renk çubuğunda görünen tüm renk öğelerinin boyutunu ayarlar.

```cpp
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>Parametreler

*sizeBox*<br/>
[içinde] Renk paletindeki renk düğmelerinin yeni boyutu.

## <a name="cmfcribboncolorbuttonsetcolorname"></a><a name="setcolorname"></a>CMFCRibbonColorButton::SetColorName

Belirli bir renk için yeni bir ad ayarlar.

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] Bir rengin RGB değeri.

*strName*<br/>
[içinde] Belirtilen renk için yeni ad.

### <a name="remarks"></a>Açıklamalar

Aradığı `CMFCColorBar::SetColorName`için, bu yöntem uygulamanızdaki tüm `CMFCColorBar` nesnelerde belirtilen rengin adını değiştirir.

## <a name="cmfcribboncolorbuttonsetcolumns"></a><a name="setcolumns"></a>CMFCRibbonColorButton::SetColumns

Kullanıcının renk seçimi işlemi sırasında kullanıcıya sunulan renkler tablosunda görüntülenen sütun sayısını ayarlar.

```cpp
void SetColumns(int nColumns);
```

### <a name="parameters"></a>Parametreler

*nSütunlar*<br/>
[içinde] Her satırda görüntülenecek renk simgelerinin sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFCRibbonColorButton::SetDocumentColors

Belge renk alanında görüntülenecek RGB değerlerinin listesini belirtir.

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Belge renkleriyle birlikte görüntülenecek metin.

*lstRenkler*<br/>
[içinde] RGB değerleri listesine başvuru.

## <a name="cmfcribboncolorbuttonsetpalette"></a><a name="setpalette"></a>CMFCRibbonColorButton::SetPalette

Renk düğmesinin görüntülenebilen renk tablosunda görüntülenecek standart renkleri belirtir.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parametreler

*pPalette*<br/>
[içinde] Renk paletine işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncolorbuttonupdatecolor"></a><a name="updatecolor"></a>CMFCRibbonColorButton::UpdateColor

Kullanıcı renk düğmesini tıklattığında görüntülenen renk tablosundan bir renk seçtiğinde çerçeve tarafından çağrılır.

```cpp
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] Kullanıcı tarafından seçilen bir renk.

### <a name="remarks"></a>Açıklamalar

Yöntem, `CMFCRibbonColorButton::UpdateColor` seçili düğmenin rengini değiştirir ve BN_CLICKED standart bildirim içeren bir WM_COMMAND iletigöndererek üst öğesini bildirir. Seçili rengi almak için [CMFCRibbonColorButton::GetColor](#getcolor) yöntemini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery Sınıfı](../../mfc/reference/cmfcribbongallery-class.md)
