---
title: CMFCColorDialog sınıfı
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
ms.openlocfilehash: 9e018c122cded09e5366c3b349525fa7cc004897
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505336"
---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog sınıfı

`CMFCColorDialog` Sınıf bir renk seçimi iletişim kutusunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMFCColorDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorDialog:: CMFCColorDialog](#cmfccolordialog)|Bir `CMFCColorDialog` nesnesi oluşturur.|
|`CMFCColorDialog::~CMFCColorDialog`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorDialog:: GetColor](#getcolor)|Seçilen geçerli rengi döndürür.|
|[CMFCColorDialog:: GetPalette](#getpalette)|Rengin paletini döndürür.|
|`CMFCColorDialog::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini çevirir. Sözdizimi ve daha fazla bilgi için bkz. [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz `CDialogEx::PreTranslateMessage`kılmalar.)|
|[CMFCColorDialog:: RebuildPalette](#rebuildpalette)|Sistem paletinden bir palet türetir.|
|[CMFCColorDialog:: SetCurrentColor](#setcurrentcolor)|Geçerli seçili rengi ayarlar.|
|[CMFCColorDialog:: SetNewColor](#setnewcolor)|Belirtilen RGB değerine en çok denk rengi ayarlar.|
|[CMFCColorDialog:: SetPageOne](#setpageone)|İlk özellik sayfası için bir RGB değeri seçer.|
|[CMFCColorDialog:: SetPageTwo](#setpagetwo)|İkinci özellik sayfası için bir RGB değeri seçer.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|`m_bIsMyPalette`|Renk seçimi iletişim kutusu kendi renk paletini kullanıyorsa true, iletişim kutusu `CMFCColorDialog` oluşturucuda belirtilen bir paleti kullanıyorsa false.|
|`m_bPickerMode`|Kullanıcı seçim iletişim kutusundan bir renk seçerken doğru. Aksi takdirde, FALSE.|
|`m_btnColorSelect`|Kullanıcının seçtiği renk düğmesi.|
|`m_CurrentColor`|Şu anda seçili olan renk.|
|`m_hcurPicker`|Bir renk seçmek için kullanılan imleç.|
|`m_NewColor`|Kalıcı olarak seçilebilen veya orijinal renge geri döndürülebilmesi olası seçili renk.|
|`m_pColourSheetOne`|Renk seçimi Özellik sayfasının ilk özellik sayfasına yönelik bir işaretçi.|
|`m_pColourSheetTwo`|Renk seçimi Özellik sayfasının ikinci özellik sayfasına yönelik bir işaretçi.|
|`m_pPalette`|Geçerli mantıksal palet.|
|`m_pPropSheet`|Renk seçimi iletişim kutusu için özellik sayfasına yönelik bir işaretçi.|
|`m_wndColors`|Renk Seçici denetim nesnesi.|
|`m_wndStaticPlaceHolder`|Renk seçici Özellik sayfası için yer tutucu olan statik bir denetim.|

## <a name="remarks"></a>Açıklamalar

Renk seçimi iletişim kutusu, iki sayfalı bir özellik sayfası olarak görüntülenir. İlk sayfada sistem paletinden standart bir renk seçersiniz; İkinci sayfada özel bir renk seçersiniz.

Yığında bir `CMFCColorDialog` nesne oluşturabilir ve sonra ilk rengi `CMFCColorDialog` oluşturucuya bir parametre `DoModal`olarak geçirerek çağırın. Renk seçimi iletişim kutusu, her renk paletini işlemek için birkaç [CMFCColorPickerCtrl sınıf](../../mfc/reference/cmfccolorpickerctrl-class.md) nesnesi oluşturur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCColorDialog` sınıfında çeşitli yöntemler kullanarak bir renk iletişim kutusunun nasıl yapılandırılacağını gösterir. Örnekte, iletişim kutusunun geçerli ve yeni renklerinin nasıl ayarlanacağı ve renk iletişim kutusunun iki özellik sayfasında seçili bir rengin kırmızı, yeşil ve mavi bileşenlerinin nasıl ayarlanacağı gösterilmektedir. Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolordialog. h

##  <a name="cmfccolordialog"></a>CMFCColorDialog:: CMFCColorDialog

Bir `CMFCColorDialog` nesnesi oluşturur.

```
CMFCColorDialog(
    COLORREF clrInit=0,
    DWORD dwFlags=0,
    CWnd* pParentWnd=NULL,
    HPALETTE hPal=NULL);
```

### <a name="parameters"></a>Parametreler

*clrInit*<br/>
'ndaki Varsayılan renk seçimi. Değer belirtilmemişse, varsayılan RGB 'dir (0, 0, 0) (siyah).

*dwFlags*<br/>
'ndaki Ayrılamadı.

*pParentWnd*<br/>
'ndaki İletişim kutusunun üst veya sahip penceresine yönelik bir işaretçi.

*hPal*<br/>
'ndaki Renk paleti için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getcolor"></a>CMFCColorDialog:: GetColor

Kullanıcının renk iletişim kutusundan seçtiği rengi alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Renk iletişim kutusunda seçilen rengin RGB bilgilerini içeren [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

`DoModal` Yöntemi çağırdıktan sonra bu işlevi çağırın.

##  <a name="getpalette"></a>CMFCColorDialog:: GetPalette

Geçerli renk iletişim kutusunda bulunan renk paletini alır.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturucuda`CMFCColorDialog` belirtilen `CPalette` nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Renk paleti, kullanıcının seçecan renkleri belirtir.

##  <a name="rebuildpalette"></a>CMFCColorDialog:: RebuildPalette

Sistem paletinden bir palet türetir.

```
void RebuildPalette();
```

##  <a name="setcurrentcolor"></a>CMFCColorDialog:: SetCurrentColor

İletişim kutusunun geçerli rengini ayarlar.

```
void SetCurrentColor(COLORREF rgb);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
'ndaki Bir RGB renk değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="setnewcolor"></a>CMFCColorDialog:: SetNewColor

Geçerli rengi geçerli palet içindeki renge en benzer şekilde ayarlar.

```
void SetNewColor(COLORREF rgb);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
'ndaki Bir RGB rengi belirten [colorref](/windows/win32/gdi/colorref) .

### <a name="remarks"></a>Açıklamalar

##  <a name="setpageone"></a>CMFCColorDialog:: SetPageOne

Açık olarak, bir renk iletişim kutusunun ilk özellik sayfasında seçili rengin kırmızı, yeşil ve mavi bileşenlerini belirtir.

```
void SetPageOne(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parametreler

*R*<br/>
'ndaki RGB değerinin kırmızı bileşenini belirtir.

*G*<br/>
'ndaki RGB değerinin yeşil bileşenini belirtir.

*B*<br/>
'ndaki RGB değerinin mavi bileşenini belirtir.

### <a name="remarks"></a>Açıklamalar

##  <a name="setpagetwo"></a>CMFCColorDialog:: SetPageTwo

Açık olarak, bir renk iletişim kutusunun ikinci özellik sayfasında seçili rengin kırmızı, yeşil ve mavi bileşenlerini belirtir.

```
void SetPageTwo(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parametreler

*R*<br/>
'ndaki RGB değerinin kırmızı bileşenini belirtir

*G*<br/>
'ndaki RGB değerinin yeşil bir bileşenini belirtir

*B*<br/>
'ndaki Bir RGB değerinin mavi bileşenini belirtir

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorPickerCtrl Sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md)
