---
title: CMFCColorDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
helpviewer_keywords:
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
ms.openlocfilehash: 987e4f1e5e89c3c56b58adaad76cfd23d5e26c52
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367714"
---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog Sınıfı

Sınıf `CMFCColorDialog` bir renk seçimi iletişim kutusunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMFCColorDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|Bir `CMFCColorDialog` nesne inşa eder.|
|`CMFCColorDialog::~CMFCColorDialog`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorDialog::GetColor](#getcolor)|Geçerli seçili rengi döndürür.|
|[CMFCColorDialog::GetPalette](#getpalette)|Rengin paletini döndürür.|
|`CMFCColorDialog::PreTranslateMessage`|Pencere iletilerini [Çeviri İletisi](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirir. Sözdizimi ve daha fazla bilgi için [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)' a bakın. (Geçersiz `CDialogEx::PreTranslateMessage`kılar .)|
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Sistem paletinden bir palet türeter.|
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Geçerli seçili rengi ayarlar.|
|[CMFCColorDialog::SetNewColor](#setnewcolor)|Rengi belirtilen RGB değerine en çok eşdeğer ayarlar.|
|[CMFCColorDialog::SetPageOne](#setpageone)|İlk özellik sayfası için bir RGB değeri seçer.|
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|İkinci özellik sayfası için bir RGB değeri seçer.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|`m_bIsMyPalette`|Renk seçimi iletişim kutusu kendi renk paletini kullanıyorsa DOĞRU veya iletişim kutusu `CMFCColorDialog` oluşturucuda belirtilen bir palet kullanıyorsa FALSE.|
|`m_bPickerMode`|Kullanıcı seçim iletişim kutusundan bir renk seçerken TRUE; aksi takdirde, YANLIŞ.|
|`m_btnColorSelect`|Kullanıcının seçtiği renk düğmesi.|
|`m_CurrentColor`|Şu anda seçili renk.|
|`m_hcurPicker`|Bir renk seçmek için kullanılan imleç.|
|`m_NewColor`|Kalıcı olarak seçilebilen veya orijinal renge geri döndürülebilen olası seçili renk.|
|`m_pColourSheetOne`|Renk seçimi özelliği sayfasının ilk özellik sayfasına işaretçi.|
|`m_pColourSheetTwo`|Renk seçimi özelliği sayfasının ikinci özellik sayfasına işaretçi.|
|`m_pPalette`|Geçerli mantıksal palet.|
|`m_pPropSheet`|Renk seçimi iletişim kutusu için özellik sayfasına işaretçi.|
|`m_wndColors`|Renk seçici kontrol nesnesi.|
|`m_wndStaticPlaceHolder`|Renk seçici özellik sayfası için yer tutucu olan statik denetim.|

## <a name="remarks"></a>Açıklamalar

Renk seçimi iletişim kutusu, iki sayfalık bir özellik sayfası olarak görüntülenir. İlk sayfada, sistem paletinden standart bir renk seçersiniz; ikinci sayfada, özel bir renk seçin.

Yığında bir `CMFCColorDialog` nesne oluşturabilir ve `DoModal`ardından ilk rengi `CMFCColorDialog` oluşturucuya parametre olarak geçirerek arayabilirsiniz. Renk seçimi iletişim kutusu daha sonra her renk paletini işlemek için birkaç [CMFCColorPickerCtrl Sınıf](../../mfc/reference/cmfccolorpickerctrl-class.md) nesneleri oluşturur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[Cmfccolordialog](../../mfc/reference/cmfccolordialog-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCColorDialog` sınıfta çeşitli yöntemler kullanarak bir renk iletişim kutusunun nasıl yapılandırılabildiğini gösterir. Örnek, iletişim kutusunun geçerli ve yeni renklerini nasıl ayarlayişize edilebildiğini ve renk iletişim kutusunun iki özellik sayfalarında seçili rengin kırmızı, yeşil ve mavi bileşenlerinin nasıl ayarlanılabildiğini gösterir. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolordialog.h

## <a name="cmfccolordialogcmfccolordialog"></a><a name="cmfccolordialog"></a>CMFCColorDialog::CMFCColorDialog

Bir `CMFCColorDialog` nesne inşa eder.

```
CMFCColorDialog(
    COLORREF clrInit=0,
    DWORD dwFlags=0,
    CWnd* pParentWnd=NULL,
    HPALETTE hPal=NULL);
```

### <a name="parameters"></a>Parametreler

*clrInit*<br/>
[içinde] Varsayılan renk seçimi. Değer belirtilmemişse, varsayılan değer RGB(0,0,0) (siyah) olur.

*Dwflags*<br/>
[içinde] Saklı -dır.

*pParentWnd*<br/>
[içinde] İletişim kutusunun üst veya sahip penceresiiçin bir işaretçi.

*hPal*<br/>
[içinde] Renk paletine tutamaç.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolordialoggetcolor"></a><a name="getcolor"></a>CMFCColorDialog::GetColor

Kullanıcının renk iletişim kutusundan seçtiği rengi alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Renk iletişim kutusunda seçilen renk için RGB bilgilerini içeren BIR [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

`DoModal` Yöntemi aradıktan sonra bu işlevi arayın.

## <a name="cmfccolordialoggetpalette"></a><a name="getpalette"></a>CMFCColorDialog::GetPalette

Geçerli renk iletişim kutusunda bulunan renk paletini alır.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturucuda `CPalette` belirtilen nesneye işaretçi. `CMFCColorDialog`

### <a name="remarks"></a>Açıklamalar

Renk paleti, kullanıcının seçebileceği renkleri belirtir.

## <a name="cmfccolordialogrebuildpalette"></a><a name="rebuildpalette"></a>CMFCColorDialog::RebuildPalette

Sistem paletinden bir palet türeter.

```
void RebuildPalette();
```

## <a name="cmfccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CMFCColorDialog::SetCurrentColor

İletişim kutusunun geçerli rengini ayarlar.

```
void SetCurrentColor(COLORREF rgb);
```

### <a name="parameters"></a>Parametreler

*Rgb*<br/>
[içinde] RGB renk değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolordialogsetnewcolor"></a><a name="setnewcolor"></a>CMFCColorDialog::SetNewColor

Geçerli rengi, en çok benzeyen geçerli paletteki renge ayarlar.

```
void SetNewColor(COLORREF rgb);
```

### <a name="parameters"></a>Parametreler

*Rgb*<br/>
[içinde] RGB rengini belirten bir [COLORREF.](/windows/win32/gdi/colorref)

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolordialogsetpageone"></a><a name="setpageone"></a>CMFCColorDialog::SetPageOne

Renk iletişim kutusunun ilk özellik sayfasında seçili rengin kırmızı, yeşil ve mavi bileşenlerini açıkça belirtir.

```
void SetPageOne(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parametreler

*R*<br/>
[içinde] RGB değerinin kırmızı bileşenini belirtir.

*G*<br/>
[içinde] RGB değerinin yeşil bileşenini belirtir.

*B*<br/>
[içinde] RGB değerinin mavi bileşenini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolordialogsetpagetwo"></a><a name="setpagetwo"></a>CMFCColorDialog::SetPageTwo

Bir renk iletişim kutusunun ikinci özellik sayfasında seçili rengin kırmızı, yeşil ve mavi bileşenlerini açıkça belirtir.

```
void SetPageTwo(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parametreler

*R*<br/>
[içinde] RGB değerinin kırmızı bir bileşenini belirtir

*G*<br/>
[içinde] RGB değerinin yeşil bileşenini belirtir

*B*<br/>
[içinde] RGB değerinin mavi bileşenini belirtir

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorPickerCtrl Sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md)
