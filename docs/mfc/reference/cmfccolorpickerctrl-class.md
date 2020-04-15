---
title: CMFCColorPickerCtrl Sınıfı
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
ms.openlocfilehash: c3c11db448ab31324367b7f314cd6bfe44c2e96d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367695"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl Sınıfı

Sınıf, `CMFCColorPickerCtrl` renkleri seçmek için kullanılan bir denetim için işlevsellik sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Bir `CMFCColorPickerCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Kullanıcının seçtiği rengi alır.|
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Kullanıcının seçtiği rengin renk tonunu, parlaklığını ve doygunluk değerlerini alır.|
|[CMFCColorPickerCtrl::GetHue](#gethue)|Kullanıcının seçtiği rengin ton bileşenini alır.|
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Kullanıcının seçtiği rengin parlaklık bileşenini alır.|
|[CMFCColorPickerCtrl::Alma Satürasyonu](#getsaturation)|Kullanıcının seçtiği rengin doygunluk bileşenini alır.|
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Geçerli rengi belirtilen RGB renk bileşenleri veya belirtilen hücre altıgeni tarafından tanımlanan renge ayarlar.|
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Geçerli rengi belirtilen RGB renk değerine ayarlar.|
|[CMFCColorPickerCtrl:SetHLS](#sethls)|Geçerli rengi belirtilen HLS renk değerine ayarlar.|
|[CMFCColorPickerCtrl::SetHue](#sethue)|Şu anda seçili rengin ton bileşenini değiştirir.|
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Şu anda seçili rengin parlaklık bileşenini değiştirir.|
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Renk seçici denetiminde parlaklık çubuğunun genişliğini ayarlar.|
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|İlk seçili rengi ayarlar.|
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Geçerli renk paletini ayarlar.|
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Şu anda seçili rengin doygunluk bileşenini değiştirir.|
|[CMFCColorPickerCtrl::SetType](#settype)|Görüntülemek için renk seçici denetiminin türünü ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Seçili renge işaret eden bir imleç görüntülenmeden önce çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

Standart renkler altıgen renk paletinden seçilir ve renklerin kırmızı/yeşil/mavi gösterim veya ton/doygunluk/parlaklık gösterimi kullanılarak belirtildiği bir parlaklık çubuğundan özel renkler seçilir.

Aşağıdaki resimde birkaç `CMFCColorPickerCtrl` nesne gösterilmiştir.

![CMFCColorPickerCtrl iletişim kutusu](../../mfc/reference/media/colorpicker.png "CMFCColorPickerCtrl iletişim kutusu")

İki `CMFCColorPickerCtrl` stil çiftini destekler. HEX ve HEX_GREYSCALE stilleri standart renk seçimi için uygundur. PICKER ve LUMINANCE stilleri özel renk seçimi için uygundur.

Denetimi iletişim kutunuza `CMFCColorPickerCtrl` dahil etmek için aşağıdaki adımları gerçekleştirin:

1. **ClassWizard**kullanıyorsanız, iletişim kutusu şablonuna yeni bir düğme denetimi `CMFCColorPickerCtrl` ekleyin (sınıf `CButton` sınıftan devralındı.

1. İletişim kutusu sınıfınıza yeni düğme denetimiyle ilişkili bir üye değişken ekleyin. Daha sonra değişken `CButton` türünü `CMFCColorPickerCtrl`' den ' e değiştirin

1. İletişim kutusu `WM_INITDIALOG` sınıfı için ileti işleyicisini ekleyin. İşleyicide, denetimin türünü, paletini `CMFCColorPickerCtrl` ve ilk seçili rengini ayarlayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCColorPickerCtrl` `CMFCColorPickerCtrl` sınıfta çeşitli yöntemler kullanarak bir nesneyi nasıl yapılandırışlagösteriyi gösterir. Örnek, seçici denetiminin türünü nasıl ayarlayacağı ve rengini, tonunu, parlaklığını ve doygunluğu nasıl ayarlanınacağı gösteriş verir. Örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cbutton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolorpickerctrl.h

## <a name="cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a>CMFCColorPickerCtrl::CMFCColorPickerCtrl

Bir `CMFCColorPickerCtrl` nesne inşa eder.

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a>CMFCColorPickerCtrl::DrawCursor

Seçili renge işaret eden bir imleç görüntülenmeden önce çerçeve tarafından çağrılır.

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Seçili rengin etrafında dikdörtgen bir alan belirtir.

### <a name="remarks"></a>Açıklamalar

Seçili renge işaret eden imlecin şeklini değiştirmeniz gerektiğinde bu yöntemi geçersiz kılın.

## <a name="cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a>CMFCColorPickerCtrl::GetColor

Kullanıcının seçtiği rengi alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili rengin RGB değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlgethls"></a><a name="gethls"></a>CMFCColorPickerCtrl::GetHLS

Kullanıcının seçtiği rengin renk tonunu, parlaklığını ve doygunluk değerlerini alır.

```
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>Parametreler

*Ton*<br/>
[çıkış] Renk tonu bilgilerini alan bir tür çift değişkenini işaretçi.

*Parlak -lık*<br/>
[çıkış] Parlaklık bilgilerini alan bir tür çift değişkenini işaretçi.

*Doygun -luk*<br/>
[çıkış] Doygunluk bilgilerini alan bir tür çift değişkenini işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlgethue"></a><a name="gethue"></a>CMFCColorPickerCtrl::GetHue

Kullanıcının seçtiği rengin ton bileşenini alır.

```
double GetHue() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili rengin ton bileşeni.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a>CMFCColorPickerCtrl::GetLuminance

Kullanıcının seçtiği rengin parlaklık bileşenini alır.

```
double GetLuminance() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili rengin parlaklık bileşeni.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a>CMFCColorPickerCtrl::Alma Satürasyonu

Kullanıcının seçtiği rengin doygunluk değerini alır.

```
double GetSaturation() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili rengin doygunluk bileşeni.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a>CMFCColorPickerCtrl::SelectCellHexagon

Geçerli rengi belirtilen RGB renk bileşenleri veya belirtilen hücre altıgeni tarafından tanımlanan renge ayarlar.

```
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
[içinde] Kırmızı renk bileşeni.

*G*<br/>
[içinde] Yeşil renk bileşeni.

*B*<br/>
[içinde] Mavi renk bileşeni.

*X*<br/>
[içinde] İmleçin x-koordinatı, bir hücre altıgenini işaret eder.

*Y*<br/>
[içinde] İmleçin y-koordinatı, bir hücre altıgenini işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntemin ikinci aşırı yükleme her zaman FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin ilk aşırı yükü, renk seçimi denetiminin belirtilen kırmızı, yeşil ve mavi renk bileşenlerine karşılık gelen renge geçerli rengi ayarlar.

Bu yöntemin ikinci aşırı yükleme belirtilen imleç konumu tarafından işaret hücre altıgen rengi için geçerli renk ayarlar.

## <a name="cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a>CMFCColorPickerCtrl::SetColor

Geçerli rengi belirtilen RGB renk değerine ayarlar.

```
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[içinde] RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsethls"></a><a name="sethls"></a>CMFCColorPickerCtrl:SetHLS

Geçerli rengi belirtilen HLS renk değerine ayarlar.

```
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>Parametreler

*Ton*<br/>
[içinde] Bir renk değeri.

*Parlak -lık*<br/>
[içinde] Parlaklık değeri.

*Doygun -luk*<br/>
[içinde] Doygunluk değeri.

*bGeçersiz*<br/>
[içinde] Pencereyi yeni renge hemen güncellemeye zorlamak için TRUE; aksi takdirde, YANLIŞ. Varsayılan TRUE'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsethue"></a><a name="sethue"></a>CMFCColorPickerCtrl::SetHue

Seçili rengin tonunu değiştirir.

```
void SetHue(double Hue);
```

### <a name="parameters"></a>Parametreler

*Ton*<br/>
[içinde] Bir renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a>CMFCColorPickerCtrl::SetLuminance

Şu anda seçili rengin parlaklığını değiştirir.

```
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>Parametreler

*Parlak -lık*<br/>
[içinde] Parlaklık değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a>CMFCColorPickerCtrl::SetLuminanceBarWidth

Renk seçici denetiminde parlaklık çubuğunun genişliğini ayarlar.

```
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>Parametreler

*W*<br/>
[içinde] Parlaklık çubuğunun genişliği piksel cinsinden ölçülür.

### <a name="remarks"></a>Açıklamalar

Renk seçici denetiminin **Özel** sekmesinde bulunan parlaklık çubuğunu yeniden boyutlandırmak için bu yöntemi kullanın. *w* parametresi parlaklık çubuğunun yeni genişliğini belirtir. İstemci alan genişliğinin dörtte üçünü aşarsa genişlik değeri yoksayılır.

## <a name="cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a>CMFCColorPickerCtrl::SetOriginalColor

İlk seçili rengi ayarlar.

```
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>Parametreler

*ref*<br/>
[içinde] RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Renk seçici denetimi başharfe geçtiğinde bu yöntemi çağırın.

## <a name="cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a>CMFCColorPickerCtrl::SetPalette

Geçerli renk paletini ayarlar.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parametreler

*pPalette*<br/>
[içinde] Renk paletine işaretçi.

### <a name="remarks"></a>Açıklamalar

Renk paleti, renk seçici denetiminde sunulan renk dizisini tanımlar.

## <a name="cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a>CMFCColorPickerCtrl::SetSaturation

Seçili rengin doygunluğu değişir.

```
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>Parametreler

*Doygun -luk*<br/>
[içinde] Doygunluk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorpickerctrlsettype"></a><a name="settype"></a>CMFCColorPickerCtrl::SetType

Görüntülemek için renk seçici denetiminin türünü ayarlar.

```
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>Parametreler

*colorType*<br/>
[içinde] Renk seçici kontrol türü.

Türleri numaralandırma ile `CMFCColorPickerCtrl::COLORTYPE` tanımlanır. Olası türleri LUMINANCE, PICKER, HEX ve HEX_GREYSCALE. Varsayılan tür PICKER'dır.

### <a name="remarks"></a>Açıklamalar

Renk seçici denetim türünü belirtmek için, Windows denetimi oluşturulmadan önce bu yöntemi arayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog Sınıfı](../../mfc/reference/cmfccolordialog-class.md)
