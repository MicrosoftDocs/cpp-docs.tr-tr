---
description: 'Daha fazla bilgi edinin: CMFCColorPickerCtrl sınıfı'
title: CMFCColorPickerCtrl sınıfı
ms.date: 11/19/2018
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
ms.openlocfilehash: e4363c08af86dee96df1492e9a029414d9902435
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313079"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl sınıfı

`CMFCColorPickerCtrl`Sınıfı, renk seçmek için kullanılan bir denetim için işlevsellik sağlar.

## <a name="syntax"></a>Syntax

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorPickerCtrl:: CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Bir `CMFCColorPickerCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorPickerCtrl:: GetColor](#getcolor)|Kullanıcının seçtiği rengi alır.|
|[CMFCColorPickerCtrl:: GetHLS](#gethls)|Kullanıcının seçtiği rengin ton, ışıklılık ve doygunluk değerlerini alır.|
|[CMFCColorPickerCtrl:: GetHue](#gethue)|Kullanıcının seçtiği rengin ton bileşenini alır.|
|[CMFCColorPickerCtrl:: Getışıklılık](#getluminance)|Kullanıcının seçtiği rengin ışıklılık bileşenini alır.|
|[CMFCColorPickerCtrl:: Getdoyma](#getsaturation)|Kullanıcının seçtiği rengin doygunluk bileşenini alır.|
|[CMFCColorPickerCtrl:: Selectcellaltıon](#selectcellhexagon)|Geçerli rengi belirtilen RGB renk bileşenleri veya belirtilen hücre altıya tarafından tanımlanan renge ayarlar.|
|[CMFCColorPickerCtrl:: SetColor](#setcolor)|Geçerli rengi belirtilen RGB renk değerine ayarlar.|
|[CMFCColorPickerCtrl:: SetHLS](#sethls)|Geçerli rengi belirtilen HLS renk değerine ayarlar.|
|[CMFCColorPickerCtrl:: SetHue](#sethue)|Şu anda seçili olan rengin ton bileşenini değiştirir.|
|[CMFCColorPickerCtrl:: Setışıklılık](#setluminance)|Şu anda seçili olan rengin ışıklılık bileşenini değiştirir.|
|[CMFCColorPickerCtrl:: SetLuminanceBarWidth](#setluminancebarwidth)|Renk seçici denetimindeki ışıklılık çubuğunun genişliğini ayarlar.|
|[CMFCColorPickerCtrl:: SetOriginalColor](#setoriginalcolor)|Başlangıçtaki seçili rengi ayarlar.|
|[CMFCColorPickerCtrl:: SetPalette](#setpalette)|Geçerli renk paletini ayarlar.|
|[CMFCColorPickerCtrl:: Setdoyma](#setsaturation)|Şu anda seçili olan rengin doygunluk bileşenini değiştirir.|
|[CMFCColorPickerCtrl:: SetType](#settype)|Görüntülenecek renk seçici denetiminin türünü ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorPickerCtrl::D rawCursor](#drawcursor)|Seçilen renge işaret eden bir imleç görüntülenmeden önce Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Standart renkler, bir altıgen renk paletinden seçilir ve renklerin kırmızı/yeşil/mavi Gösterim ya da ton/satuaration/ışıklılık gösterimi kullanılarak belirtildiği bir ışıklılık çubuğundan seçilir.

Aşağıdaki çizimde çeşitli nesneler gösterilmektedir `CMFCColorPickerCtrl` .

![CMFCColorPickerCtrl iletişim kutusu](../../mfc/reference/media/colorpicker.png "CMFCColorPickerCtrl iletişim kutusu")

`CMFCColorPickerCtrl`İki çift stili destekler. ONALTıLıK ve HEX_GREYSCALE stilleri standart renk seçimi için uygundur. SEÇICI ve ıŞıKLıLıK stilleri özel renk seçimi için uygundur.

İletişim kutusuna denetimi birleştirmek için aşağıdaki adımları gerçekleştirin `CMFCColorPickerCtrl` :

1. **ClassWizard** kullanırsanız, iletişim kutusu şablonunuza yeni bir düğme denetimi ekleyin ( `CMFCColorPickerCtrl` sınıf sınıftan devralındığından `CButton` ).

1. İletişim kutusu sınıfınıza yeni düğme denetimiyle ilişkili bir üye değişkeni ekleyin. Sonra değişken türünü `CButton` olarak değiştirin `CMFCColorPickerCtrl` .

1. `WM_INITDIALOG`İletişim kutusu sınıfı için ileti işleyicisini ekleyin. İşleyicide, denetimin türünü, paletini ve başlangıçtaki seçili rengini ayarlayın `CMFCColorPickerCtrl` .

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCColorPickerCtrl` sınıfında çeşitli yöntemler kullanarak bir nesnenin nasıl yapılandırılacağını gösterir `CMFCColorPickerCtrl` . Örnek, seçici denetiminin türünün nasıl ayarlanacağını ve renk, ton, ışıklılık ve doygunluğu nasıl ayarlayabileceğinizi gösterir. Örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolorpickerctrl. h

## <a name="cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a> CMFCColorPickerCtrl:: CMFCColorPickerCtrl

Bir `CMFCColorPickerCtrl` nesnesi oluşturur.

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a> CMFCColorPickerCtrl::D rawCursor

Seçilen renge işaret eden bir imleç görüntülenmeden önce Framework tarafından çağırılır.

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamı işaretçisi.

*Rect*<br/>
'ndaki Seçilen rengin çevresindeki dikdörtgen bir alanı belirtir.

### <a name="remarks"></a>Açıklamalar

Seçilen renge işaret eden imlecin şeklini değiştirmeniz gerektiğinde bu yöntemi geçersiz kılın.

## <a name="cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a> CMFCColorPickerCtrl:: GetColor

Kullanıcının seçtiği rengi alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçilen rengin RGB değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlgethls"></a><a name="gethls"></a> CMFCColorPickerCtrl:: GetHLS

Kullanıcının seçtiği rengin ton, ışıklılık ve doygunluk değerlerini alır.

```cpp
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>Parametreler

*renk*<br/>
dışı Ton bilgilerini alan Double türünde bir değişkene yönelik işaretçi.

*ışıklılık*<br/>
dışı Aydınlatma bilgilerini alan Double türünde bir değişkene yönelik işaretçi.

*doygunluğu*<br/>
dışı Doygunluk bilgilerini alan Double türünde bir değişkene yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlgethue"></a><a name="gethue"></a> CMFCColorPickerCtrl:: GetHue

Kullanıcının seçtiği rengin ton bileşenini alır.

```
double GetHue() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçilen rengin ton bileşeni.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a> CMFCColorPickerCtrl:: Getışıklılık

Kullanıcının seçtiği rengin ışıklılık bileşenini alır.

```
double GetLuminance() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçilen rengin ışıklılık bileşeni.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a> CMFCColorPickerCtrl:: Getdoyma

Kullanıcının seçtiği rengin doygunluk değerini alır.

```
double GetSaturation() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçilen rengin doygunluk bileşeni.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a> CMFCColorPickerCtrl:: Selectcellaltıon

Geçerli rengi belirtilen RGB renk bileşenleri veya belirtilen hücre altıya tarafından tanımlanan renge ayarlar.

```cpp
void SelectCellHexagon(
    BYTE R,
    BYTE G,
    BYTE B);

BOOL SelectCellHexagon(
    int x,
    int y);
```

### <a name="parameters"></a>Parametreler

*R*<br/>
'ndaki Kırmızı renk bileşeni.

*G*<br/>
'ndaki Yeşil renk bileşeni.

*B*<br/>
'ndaki Mavi renk bileşeni.

*x*<br/>
'ndaki İmlecin bir hücresini işaret eden x koordinatı.

*Iz*<br/>
'ndaki İmlecin, altıon hücresini işaret eden y koordinatı.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntemin ikinci aşırı yüklemesi her zaman FALSE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin ilk aşırı yüklemesi, geçerli rengi renk seçim denetiminin belirtilen kırmızı, yeşil ve mavi renk bileşenlerine karşılık gelen renge ayarlar.

Bu yöntemin ikinci aşırı yüklemesi, geçerli rengi, belirtilen imleç konumu tarafından işaret edilen altıon hücresinin rengine ayarlar.

## <a name="cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a> CMFCColorPickerCtrl:: SetColor

Geçerli rengi belirtilen RGB renk değerine ayarlar.

```cpp
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsethls"></a><a name="sethls"></a> CMFCColorPickerCtrl:: SetHLS

Geçerli rengi belirtilen HLS renk değerine ayarlar.

```cpp
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>Parametreler

*renk*<br/>
'ndaki Bir ton değeri.

*ışıklılık*<br/>
'ndaki Işıklılık değeri.

*doygunluğu*<br/>
'ndaki Bir doygunluk değeri.

*bInvalidate*<br/>
'ndaki Pencereyi yeni renge hemen güncelleştirmeye zorlamak için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsethue"></a><a name="sethue"></a> CMFCColorPickerCtrl:: SetHue

Şu anda seçili olan rengin tonunu değiştirir.

```cpp
void SetHue(double Hue);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Bir ton değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a> CMFCColorPickerCtrl:: Setışıklılık

Şu anda seçili olan rengin parlaklığını değiştirir.

```cpp
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>Parametreler

*Işıklılık*<br/>
'ndaki Işıklılık değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a> CMFCColorPickerCtrl:: SetLuminanceBarWidth

Renk seçici denetimindeki ışıklılık çubuğunun genişliğini ayarlar.

```cpp
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>Parametreler

*w*<br/>
'ndaki Işıklılık çubuğunun piksel cinsinden ölçülen genişliği.

### <a name="remarks"></a>Açıklamalar

Renk Seçici denetiminin **özel** sekmesinde bulunan ışıklılık çubuğunu yeniden boyutlandırmak için bu yöntemi kullanın. *W* parametresi, ışıklılık çubuğunun yeni genişliğini belirtir. Genişlik değeri, istemci alanı genişliğinin üç adet onda birini aşarsa yok sayılır.

## <a name="cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a> CMFCColorPickerCtrl:: SetOriginalColor

Başlangıçtaki seçili rengi ayarlar.

```cpp
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>Parametreler

*ref*<br/>
'ndaki Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Renk seçici denetimi başlatıldığında bu yöntemi çağırın.

## <a name="cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a> CMFCColorPickerCtrl:: SetPalette

Geçerli renk paletini ayarlar.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parametreler

*pPalette*<br/>
'ndaki Renk paleti işaretçisi.

### <a name="remarks"></a>Açıklamalar

Renk paleti, renk seçici denetiminde sunulan renklerin dizisini tanımlar.

## <a name="cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a> CMFCColorPickerCtrl:: Setdoyma

Şu anda seçili olan rengin doygunluğunu değiştirir.

```cpp
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>Parametreler

*Doygunluğu*<br/>
'ndaki Bir doygunluk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsettype"></a><a name="settype"></a> CMFCColorPickerCtrl:: SetType

Görüntülenecek renk seçici denetiminin türünü ayarlar.

```cpp
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>Parametreler

*colorType*<br/>
'ndaki Renk Seçici denetim türü.

Türler numaralandırma tarafından tanımlanır `CMFCColorPickerCtrl::COLORTYPE` . Olası türler ıŞıKLıLıK, SEÇICI, ONALTıLı ve HEX_GREYSCALE. Varsayılan tür SEÇICSAHIPTIR.

### <a name="remarks"></a>Açıklamalar

Bir renk seçici denetim türü belirtmek için, Windows denetimi oluşturulmadan önce bu yöntemi çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md)
