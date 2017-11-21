---
title: "CMFCColorDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0f607d6145d08617151a64845bc23a58f2849dbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog sınıfı
`CMFCColorDialog` Sınıfı, bir renk seçimi iletişim kutusunu gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|Oluşturan bir `CMFCColorDialog` nesnesi.|  
|`CMFCColorDialog::~CMFCColorDialog`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](#getcolor)|Geçerli seçili renk döndürür.|  
|[CMFCColorDialog::GetPalette](#getpalette)|Renk paleti döndürür.|  
|`CMFCColorDialog::PreTranslateMessage`|Pencere iletileri için gönderilen önce çevirir [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. Sözdizimi ve daha fazla bilgi için bkz: [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz kılmaları `CDialogEx::PreTranslateMessage`.)|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Palet sistem paletinden türer.|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Geçerli seçili rengini belirler.|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|Belirtilen bir RGB değeri en eşdeğer rengini belirler.|  
|[CMFCColorDialog::SetPageOne](#setpageone)|İlk özellik sayfası için bir RGB değeri seçer.|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|İkinci özellik sayfası için bir RGB değeri seçer.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`m_bIsMyPalette`|`TRUE`Renk seçimi iletişim kutusu, kendi renk paletini kullanıyorsa veya `FALSE` iletişim kutusu içinde belirtilen bir palet kullanıp kullanmadığını `CMFCColorDialog` Oluşturucusu.|  
|`m_bPickerMode`|`TRUE`Kullanıcı seçimi iletişim kutusundan bir renk seçerek sırada; Aksi takdirde `FALSE`.|  
|`m_btnColorSelect`|Kullanıcının seçtiği renk düğmesi.|  
|`m_CurrentColor`|Şu anda seçili rengi.|  
|`m_hcurPicker`|Bir renk seçmek için kullanılan imleç.|  
|`m_NewColor`|Kalıcı olarak seçilen veya özgün rengini geri olası seçili rengi.|  
|`m_pColourSheetOne`|Renk seçimi özellik sayfasının ilk özellik sayfası için bir işaretçi.|  
|`m_pColourSheetTwo`|Renk seçimi özellik sayfasının ikinci özellik sayfası için bir işaretçi.|  
|`m_pPalette`|Geçerli mantıksal palet.|  
|`m_pPropSheet`|Renk seçimi iletişim kutusunu özellik sayfasını gösteren bir işaretçi.|  
|`m_wndColors`|Bir renk seçici denetim nesnesi.|  
|`m_wndStaticPlaceHolder`|Renk Seçici özellik sayfası için bir yer tutucu statik denetim.|  
  
## <a name="remarks"></a>Açıklamalar  
 Renk seçimi iletişim kutusu iki sayfa bulunan bir özellik sayfası görüntülenir. İlk sayfasında, standart bir renk sistem paletinden seçin; ikinci sayfasında, özel bir renk seçin.  
  
 Oluşturabileceğiniz bir `CMFCColorDialog` nesne yığında ve ardından arama `DoModal`, ilk renk bir parametre olarak geçirme `CMFCColorDialog` Oluşturucusu. Renk seçimi iletişim kutusunu daha sonra birkaç oluşturur [CMFCColorPickerCtrl sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md) her renk paletini işlemek için nesneleri.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir renk iletişim kutusu çeşitli yöntemlerle kullanarak yapılandırmak gösterilmiştir `CMFCColorDialog` sınıfı. Örnek, geçerli ve yeni renkleri iletişim kutusunun nasıl ayarlanacağını ve seçili rengi kırmızı, yeşil ve mavi bileşenlerinin renk iletişim kutusu iki özellik sayfalarında ayarlama gösterir. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcolordialog.h  
  
##  <a name="cmfccolordialog"></a>CMFCColorDialog::CMFCColorDialog  
 Oluşturan bir `CMFCColorDialog` nesnesi.  
  
```  
CMFCColorDialog(
    COLORREF clrInit=0,  
    DWORD dwFlags=0,  
    CWnd* pParentWnd=NULL,  
    HPALETTE hPal=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`clrInit`  
 Varsayılan renk seçimi. Herhangi bir değer belirtilirse, RGB(0,0,0) (siyah) varsayılandır.  
  
 [in]`dwFlags`  
 (Ayrılmıştır.)  
  
 [in]`pParentWnd`  
 İletişim kutusunun üst veya sahibi penceresi için bir işaretçi.  
  
 [in]`hPal`  
 Renk paleti için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcolor"></a>CMFCColorDialog::GetColor  
 Renk iletişim kutusundan kullanıcının seçtiği rengi alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri renk iletişim kutusunda seçili renk RGB bilgilerini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra bu işlevi çağırmak `DoModal` yöntemi.  
  
##  <a name="getpalette"></a>CMFCColorDialog::GetPalette  
 Geçerli renk iletişim kutusunda kullanılabilir renk paletini alır.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CPalette` belirtildi nesne `CMFCColorDialog` Oluşturucusu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı seçebilir renklerin renk paletini belirtir.  
  
##  <a name="rebuildpalette"></a>CMFCColorDialog::RebuildPalette  
 Palet sistem paletinden türer.  
  
```  
void RebuildPalette();
```  
  
##  <a name="setcurrentcolor"></a>CMFCColorDialog::SetCurrentColor  
 İletişim kutusunun geçerli rengini belirler.  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rgb`  
 RGB renk değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setnewcolor"></a>CMFCColorDialog::SetNewColor  
 En benzer geçerli paletindeki renge geçerli rengini belirler.  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rgb`  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) bir RGB rengi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpageone"></a>CMFCColorDialog::SetPageOne  
 Açıkça bir renk iletişim kutusu ilk özellik sayfasında seçili rengi kırmızı, yeşil ve mavi bileşenlerini belirtir.  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`R`  
 RGB değeri kırmızı bileşeni belirtir.  
  
 [in]`G`  
 RGB değeri yeşil bileşeni belirtir.  
  
 [in]`B`  
 RGB değeri mavi bileşeni belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpagetwo"></a>CMFCColorDialog::SetPageTwo  
 Açıkça bir renk iletişim kutusu ikinci özellik sayfasında seçili rengi kırmızı, yeşil ve mavi bileşenlerini belirtir.  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`R`  
 RGB değeri kırmızı bir bileşeni belirtir  
  
 [in]`G`  
 Bir RGB değeri yeşil bir bileşeni belirtir  
  
 [in]`B`  
 Bir RGB değeri mavi bir bileşeni belirtir  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md)
