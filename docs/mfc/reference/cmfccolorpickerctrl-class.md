---
title: "CMFCColorPickerCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 11c015df63d3032a8616f7f19614376aa966d89b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl sınıfı
`CMFCColorPickerCtrl` Sınıfı renkleri seçmek için kullanılan bir denetimi için işlevsellik sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Oluşturan bir `CMFCColorPickerCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Kullanıcının seçtiği rengi alır.|  
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Kullanıcının seçtiği rengi ton, aydınlatma ve Doygunluk değerlerini alır.|  
|[CMFCColorPickerCtrl::GetHue](#gethue)|Kullanıcının seçtiği rengi ton bileşeninin alır.|  
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Kullanıcının seçtiği rengi aydınlatma bileşeninin alır.|  
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Kullanıcının seçtiği rengi Doygunluk bileşeninin alır.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Belirtilen RGB renk bileşenlerini ya da belirtilen hücre Altıgene tarafından tanımlanan renge geçerli rengini belirler.|  
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Geçerli renk belirtilen RGB renk değerine ayarlar.|  
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Geçerli renk belirtilen HLS renk değerine ayarlar.|  
|[CMFCColorPickerCtrl::SetHue](#sethue)|Seçili renk ton bileşeninin değiştirir.|  
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Seçili renk aydınlatma bileşeninin değiştirir.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Renk Seçici denetiminde aydınlatma çubuğunun genişliğini ayarlar.|  
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|İlk seçili rengini belirler.|  
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Geçerli renk paletini belirler.|  
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Seçili renk doygunluk bileşeninin değiştirir.|  
|[CMFCColorPickerCtrl::SetType](#settype)|Görüntülenecek renk seçici denetim türünü ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Seçili renk işaret eden bir imleç görüntülenmeden önce çerçevesi tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Standart renkler Altıgen renk paletinden seçilir ve özel renkler aydınlatma çubuğundan seçili renkleri yeşil/kırmızı/mavi gösterimi veya satuaration/ton/aydınlatma gösterim kullanılarak belirtilir burada.  
  
 Aşağıda birkaç gösterilmektedir `CMFCColorPickerCtrl` nesneleri.  
  
 ![CMFCColorPickerCtrl iletişim kutusu](../../mfc/reference/media/colorpicker.png "colorpicker")  
  
 `CMFCColorPickerCtrl` İki çiftlerini stillerini destekler. ONALTILIK ve HEX_GREYSCALE stilleri standart renk seçimi için uygundur. SEÇİCİ ve AYDINLATMA stilleri özel renk seçimi için uygundur.  
  
 Aşağıdaki adımları izleyerek dahil `CMFCColorPickerCtrl` iletişim kutusuna denetim:  
  
1.  Kullanırsanız **ClassWizard**, iletişim kutusu şablonunuza yeni düğmesi denetim ekleme (çünkü `CMFCColorPickerCtrl` sınıfı devralınır `CButton` sınıfı).  
  
2.  Yeni düğmesi denetimi ile iletişim kutusu sınıfına ilişkili bir üye değişkeni ekleyin. Değişken türü değiştirme `CButton` için `CMFCColorPickerCtrl`.  
  
3.  INSERT `WM_INITDIALOG` iletişim kutusu sınıfı için ileti işleyicisi. İşleyicisinde türü, paleti ve başlangıç seçili rengini ayarlama `CMFCColorPickerCtrl` denetim.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl yapılandırılacağını göstermektedir bir `CMFCColorPickerCtrl` çeşitli yöntemlerle kullanarak nesne `CMFCColorPickerCtrl` sınıfı. Örnek Seçici denetim türünü nasıl kurulur ve rengi, ton, aydınlatma ve Doygunluk nasıl ayarlanacağını gösterir. Örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
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
  
##  <a name="cmfccolorpickerctrl"></a>CMFCColorPickerCtrl::CMFCColorPickerCtrl  
 Oluşturan bir `CMFCColorPickerCtrl` nesnesi.  
  
```  
CMFCColorPickerCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="drawcursor"></a>CMFCColorPickerCtrl::DrawCursor  
 Seçili renk işaret eden bir imleç görüntülenmeden önce çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawCursor(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı işaretçi.  
  
 [in]`rect`  
 Seçilen rengin etrafında dikdörtgen bir belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Seçili renk işaret imleci şeklini değiştirmek istediğinizde bu yöntemi geçersiz kılın.  
  
##  <a name="getcolor"></a>CMFCColorPickerCtrl::GetColor  
 Kullanıcının seçtiği rengi alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçilen rengin RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethls"></a>CMFCColorPickerCtrl::GetHLS  
 Kullanıcının seçtiği rengi ton, aydınlatma ve Doygunluk değerlerini alır.  
  
```  
void GetHLS(
    double* hue,  
    double* luminance,  
    double* saturation);
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`hue`  
 İşaretçi bir değişkene türünün çift ton bilgilerini alır.  
  
 [out]`luminance`  
 İşaretçi bir değişkene türünün çift aydınlatma bilgilerini alır.  
  
 [out]`saturation`  
 İşaretçi bir değişkene türünün çift Doygunluk bilgilerini alır.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethue"></a>CMFCColorPickerCtrl::GetHue  
 Kullanıcının seçtiği rengi ton bileşeninin alır.  
  
```  
double GetHue() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçilen rengin ton bileşenidir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getluminance"></a>CMFCColorPickerCtrl::GetLuminance  
 Kullanıcının seçtiği rengi aydınlatma bileşeninin alır.  
  
```  
double GetLuminance() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçilen rengin aydınlatma bileşenidir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getsaturation"></a>CMFCColorPickerCtrl::GetSaturation  
 Kullanıcının seçtiği rengi doygunluk değerini alır.  
  
```  
double GetSaturation() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçilen rengin Doygunluk bileşenidir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="selectcellhexagon"></a>CMFCColorPickerCtrl::SelectCellHexagon  
 Belirtilen RGB renk bileşenlerini ya da belirtilen hücre Altıgene tarafından tanımlanan renge geçerli rengini belirler.  
  
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
 [in]`R`  
 Kırmızı renk bileşeni.  
  
 [in]`G`  
 Yeşil renk bileşeni.  
  
 [in]`B`  
 Mavi renkle bileşeni.  
  
 [in]`x`  
 X koordinatını bir hücre Altıgene işaret imleci.  
  
 [in]`y`  
 Y koordinatını bir hücre Altıgene işaret imleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem ikinci yüklemesini her zaman döndürür `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli rengi renk seçimi denetimine karşılık gelen renk için bu yöntemi kümelerinin ilk aşırı kırmızı, yeşil ve mavi renk bileşenleri belirtilen.  
  
 Bu yöntem ikinci yüklemesini geçerli rengini tarafından belirtilen imleç konumu olarak verilir hücreye Altıgene rengi için ayarlar.  
  
##  <a name="setcolor"></a>CMFCColorPickerCtrl::SetColor  
 Geçerli renk belirtilen RGB renk değerine ayarlar.  
  
```  
void SetColor(COLORREF Color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`Color`  
 RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sethls"></a>CMFCColorPickerCtrl::SetHLS  
 Geçerli renk belirtilen HLS renk değerine ayarlar.  
  
```  
void SetHLS(
    double hue,  
    double luminance,  
    double saturation,  
    BOOL bInvalidate=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hue`  
 Bir ton değeri.  
  
 [in]`luminance`  
 Aydınlatma değeri.  
  
 [in]`saturation`  
 Bir Doygunluk değer.  
  
 [in]`bInvalidate`  
 `TRUE`yeni renge hemen güncelleştirmek için penceresini zorlamak için; Aksi takdirde `FALSE`. Varsayılan, `TRUE` değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sethue"></a>CMFCColorPickerCtrl::SetHue  
 Şu anda seçili renginin değiştirir.  
  
```  
void SetHue(double Hue);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`Hue`  
 Bir ton değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setluminance"></a>CMFCColorPickerCtrl::SetLuminance  
 Seçili renk renginin değiştirir.  
  
```  
void SetLuminance(double Luminance);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`Luminance`  
 Aydınlatma değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setluminancebarwidth"></a>CMFCColorPickerCtrl::SetLuminanceBarWidth  
 Renk Seçici denetiminde aydınlatma çubuğunun genişliğini ayarlar.  
  
```  
void SetLuminanceBarWidth(int w);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`w`  
 Aydınlatma çubuğunun genişliğini piksel cinsinden ölçülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Açık aydınlatma çubuğunu yeniden boyutlandırmak için bu yöntemi kullanın **özel** Renk Seçici denetimini sekmesinde. `w` Parametresi, yeni aydınlatma çubuğunun genişliğini belirtir. İstemci alanı genişliğinin üç fourths aşarsa, genişlik değeri göz ardı edilir.  
  
##  <a name="setoriginalcolor"></a>CMFCColorPickerCtrl::SetOriginalColor  
 İlk seçili rengini belirler.  
  
```  
void SetOriginalColor(COLORREF ref);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`ref`  
 RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk Seçici denetimini başlatıldığında bu yöntemi çağırın.  
  
##  <a name="setpalette"></a>CMFCColorPickerCtrl::SetPalette  
 Geçerli renk paletini belirler.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pPalette`  
 Renk paleti işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk paleti sunulan dizi renklerin renk seçici denetiminde tanımlar.  
  
##  <a name="setsaturation"></a>CMFCColorPickerCtrl::SetSaturation  
 Seçili renk doygunluğunu değiştirir.  
  
```  
void SetSaturation(double Saturation);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`Saturation`  
 Bir Doygunluk değer.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settype"></a>CMFCColorPickerCtrl::SetType  
 Görüntülenecek renk seçici denetim türünü ayarlar.  
  
```  
void SetType(COLORTYPE colorType);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`colorType`  
 Renk Seçici denetim türü.  
  
 Türleri tarafından tanımlanan `CMFCColorPickerCtrl::COLORTYPE` numaralandırması. Olası türleri `LUMINANCE`, `PICKER`, `HEX` ve `HEX_GREYSCALE`. Varsayılan türdür `PICKER`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk seçici denetim türünü belirtmek için Windows Denetim oluşturulmadan önce bu yöntemi çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog Sınıfı](../../mfc/reference/cmfccolordialog-class.md)
