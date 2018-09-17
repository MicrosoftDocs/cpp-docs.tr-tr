---
title: CMFCColorPickerCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ea0bf6ed8361419af3519a41edbe6bb3c4b4a77
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725666"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl sınıfı
`CMFCColorPickerCtrl` Sınıfı renkleri seçmek için kullanılan bir denetim için işlevsellik sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Oluşturur bir `CMFCColorPickerCtrl` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Kullanıcının seçtiği rengini alır.|  
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Kullanıcının seçtiği bir renk hue, parlaklık ve doygunluğu değerlerini alır.|  
|[CMFCColorPickerCtrl::GetHue](#gethue)|Kullanıcının seçtiği bir renk tonu bileşeninin alır.|  
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Kullanıcının seçtiği bir renk parlaklığını bileşeninin alır.|  
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Kullanıcının seçtiği bir renk doygunluğu bileşeninin alır.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Belirtilen RGB renk bileşenlerine ya da belirtilen hücre Altıgene tarafından tanımlanan renk için geçerli rengini ayarlar.|  
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Geçerli renk belirtilen RGB renk değerine ayarlar.|  
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Geçerli renk belirtilen HLS renk değerine ayarlar.|  
|[CMFCColorPickerCtrl::SetHue](#sethue)|Şu anda seçili renk tonu bileşeninin değiştirir.|  
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Seçili renk aydınlatma bileşeninin değiştirir.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Renk Seçici denetimi aydınlatma çubuğunun genişliğini ayarlar.|  
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|İlk seçilen rengini ayarlar.|  
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Geçerli renk paletine ayarlar.|  
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Seçili renk doygunluğu bileşeninin değiştirir.|  
|[CMFCColorPickerCtrl::SetType](#settype)|Görüntülenecek renk seçici denetimini türünü ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Seçilen renge işaret eden bir imleç görüntülenmeden önce framework tarafından çağırılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Standart renkler Altıgen renk paletinden seçilir ve özel renkler aydınlatma çubuğundan seçili renkleri kırmızı/yeşil/mavi gösterimi veya satuaration/hue/aydınlatma gösterimi kullanılarak belirtilen burada.  
  
 Aşağıdaki çizimde birkaç gösterilmektedir `CMFCColorPickerCtrl` nesneleri.  
  
 ![CMFCColorPickerCtrl iletişim kutusu](../../mfc/reference/media/colorpicker.png "colorpicker")  
  
 `CMFCColorPickerCtrl` Stilleri iki çiftlerini destekler. ONALTILIK ve HEX_GREYSCALE stilleri standart renk seçimi için uygundur. SEÇİCİ ve AYDINLATMA stilleri özel renk seçimi için uygundur.  
  
 Birleştirmek için aşağıdaki adımları gerçekleştirin `CMFCColorPickerCtrl` , iletişim kutusu denetimine:  
  
1.  Kullanırsanız **ClassWizard**, iletişim kutusu şablonunuza yeni bir düğme denetimi ekleyin (çünkü `CMFCColorPickerCtrl` sınıfı devralınır `CButton` sınıfı).  
  
2.  Yeni bir düğme denetimi ile iletişim kutusu sınıfınızı ilişkili olan bir üye değişkeni ekleyin. Ardından değişken türünden değiştirin `CButton` için `CMFCColorPickerCtrl`.  
  
3.  INSERT `WM_INITDIALOG` iletişim kutusu sınıfı için ileti işleyicisi. İşleyicisinde türü, paleti ve başlangıç seçili rengini ayarlayın `CMFCColorPickerCtrl` denetimi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl yapılandırılacağını gösteren bir `CMFCColorPickerCtrl` çeşitli yöntemleri kullanarak nesne `CMFCColorPickerCtrl` sınıfı. Örnek Seçici denetim türünü ayarlama ve renk, hue, parlaklık ve doygunluğu nasıl ayarlanacağını gösterir. Bir örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcolorpickerctrl.h  
  
##  <a name="cmfccolorpickerctrl"></a>  CMFCColorPickerCtrl::CMFCColorPickerCtrl  
 Oluşturur bir `CMFCColorPickerCtrl` nesne.  
  
```  
CMFCColorPickerCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="drawcursor"></a>  CMFCColorPickerCtrl::DrawCursor  
 Seçilen renge işaret eden bir imleç görüntülenmeden önce framework tarafından çağırılır.  
  
```  
virtual void DrawCursor(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Bir cihaz bağlamı işaretçisi.  
  
*Rect*<br/>
[in] Seçili renk çevresinde bir dikdörtgen alan belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Seçilen renge işaret eden imleci şeklini değiştirmek istediğinizde bu yöntemi yok sayın.  
  
##  <a name="getcolor"></a>  CMFCColorPickerCtrl::GetColor  
 Kullanıcının seçtiği rengini alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçilen rengin RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethls"></a>  CMFCColorPickerCtrl::GetHLS  
 Kullanıcının seçtiği bir renk hue, parlaklık ve doygunluğu değerlerini alır.  
  
```  
void GetHLS(
    double* hue,  
    double* luminance,  
    double* saturation);
```  
  
### <a name="parameters"></a>Parametreler  
*Hue*<br/>
[out] Çift aldığı hue bilgi türünde bir değişken işaretçisi.  
  
*Parlaklık*<br/>
[out] Çift aldığı aydınlatma bilgi türünde bir değişken işaretçisi.  
  
*Doygunluğu*<br/>
[out] Çift aldığı doygunluğu bilgi türünde bir değişken işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethue"></a>  CMFCColorPickerCtrl::GetHue  
 Kullanıcının seçtiği bir renk tonu bileşeninin alır.  
  
```  
double GetHue() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili renk tonu bileşeni.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getluminance"></a>  CMFCColorPickerCtrl::GetLuminance  
 Kullanıcının seçtiği bir renk parlaklığını bileşeninin alır.  
  
```  
double GetLuminance() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili renk parlaklığını bileşeni.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getsaturation"></a>  CMFCColorPickerCtrl::GetSaturation  
 Kullanıcının seçtiği bir renk doygunluğu değerini alır.  
  
```  
double GetSaturation() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili renk doygunluğu bileşeni.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="selectcellhexagon"></a>  CMFCColorPickerCtrl::SelectCellHexagon  
 Belirtilen RGB renk bileşenlerine ya da belirtilen hücre Altıgene tarafından tanımlanan renk için geçerli rengini ayarlar.  
  
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
[in] Kırmızı renk bileşeni.  
  
*G*<br/>
[in] Yeşil renk bileşeni.  
  
*B*<br/>
[in] Mavi renk bileşeni.  
  
*x*<br/>
[in] X koordinatı bir hücre Altıgene işaret imleci.  
  
*Y*<br/>
[in] Y koordinatı bir hücre Altıgene işaret imleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yönteminin ikinci aşırı yüklemesini her zaman false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli renk renk seçimi denetime karşılık gelen rengi için bu yöntemi kümelerinin ilk aşırı yükleme kırmızı, yeşil ve mavi renk bileşenlerine belirtilen.  
  
 Bu yönteminin ikinci aşırı yüklemesini geçerli renk belirtilen İmleç konumuna tarafından işaret edilen hücre Altıgene rengine ayarlar.  
  
##  <a name="setcolor"></a>  CMFCColorPickerCtrl::SetColor  
 Geçerli renk belirtilen RGB renk değerine ayarlar.  
  
```  
void SetColor(COLORREF Color);
```  
  
### <a name="parameters"></a>Parametreler  
*Renk*<br/>
[in] Bir RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sethls"></a>  CMFCColorPickerCtrl::SetHLS  
 Geçerli renk belirtilen HLS renk değerine ayarlar.  
  
```  
void SetHLS(
    double hue,  
    double luminance,  
    double saturation,  
    BOOL bInvalidate=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
*Hue*<br/>
[in] Hue değeri.  
  
*Parlaklık*<br/>
[in] Aydınlatma değeri.  
  
*Doygunluğu*<br/>
[in] Doygunluk değeri.  
  
*bInvalidate*<br/>
[in] Pencerenin yeni renge hemen güncelleştirmeye zorlamak için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sethue"></a>  CMFCColorPickerCtrl::SetHue  
 Şu anda seçili renginin değişir.  
  
```  
void SetHue(double Hue);
```  
  
### <a name="parameters"></a>Parametreler  
*Hue*<br/>
[in] Hue değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setluminance"></a>  CMFCColorPickerCtrl::SetLuminance  
 Seçili renk renginin değişir.  
  
```  
void SetLuminance(double Luminance);
```  
  
### <a name="parameters"></a>Parametreler  
*Parlaklık*<br/>
[in] Aydınlatma değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setluminancebarwidth"></a>  CMFCColorPickerCtrl::SetLuminanceBarWidth  
 Renk Seçici denetimi aydınlatma çubuğunun genişliğini ayarlar.  
  
```  
void SetLuminanceBarWidth(int w);
```  
  
### <a name="parameters"></a>Parametreler  
*w*<br/>
[in] Aydınlatma çubuğunun genişliğini piksel cinsinden ölçülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Açık aydınlatma çubuğu, yeniden boyutlandırmak için bu yöntemi kullanmak **özel** Renk Seçici denetimini sekmesi. *w* parametresi yeni aydınlatma çubuğunun genişliğini belirtir. İstemci alan genişliği üç fourths aşarsa genişlik değeri yok sayıldı.  
  
##  <a name="setoriginalcolor"></a>  CMFCColorPickerCtrl::SetOriginalColor  
 İlk seçilen rengini ayarlar.  
  
```  
void SetOriginalColor(COLORREF ref);
```  
  
### <a name="parameters"></a>Parametreler  
*ref*<br/>
[in] Bir RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk Seçici denetimini başlatıldığında, bu yöntemi çağırın.  
  
##  <a name="setpalette"></a>  CMFCColorPickerCtrl::SetPalette  
 Geçerli renk paletine ayarlar.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parametreler  
*pPalette*<br/>
[in] Renk paleti işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk paletini sunulan dizi renklerin renk seçici denetimi tanımlar.  
  
##  <a name="setsaturation"></a>  CMFCColorPickerCtrl::SetSaturation  
 Seçili renk doygunluğu değiştirir.  
  
```  
void SetSaturation(double Saturation);
```  
  
### <a name="parameters"></a>Parametreler  
*Doygunluğu*<br/>
[in] Doygunluk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settype"></a>  CMFCColorPickerCtrl::SetType  
 Görüntülenecek renk seçici denetimini türünü ayarlar.  
  
```  
void SetType(COLORTYPE colorType);
```  
  
### <a name="parameters"></a>Parametreler  
*colorType*<br/>
[in] Renk Seçici denetim türü.  
  
 Türleri tarafından tanımlanan `CMFCColorPickerCtrl::COLORTYPE` sabit listesi. Olası AYDINLATMA, SEÇİCİ, ONALTILIK ve HEX_GREYSCALE türleridir. Varsayılan SEÇİCİ türüdür.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows Denetim oluşturulmadan önce bir renk seçici denetim türü belirtmek için bu yöntemi çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog Sınıfı](../../mfc/reference/cmfccolordialog-class.md)
