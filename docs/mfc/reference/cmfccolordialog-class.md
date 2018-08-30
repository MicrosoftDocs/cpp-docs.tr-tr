---
title: CMFCColorDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4d6bf9d62ae1cb80041145903267d4af4d88eaa
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214158"
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
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|Oluşturur bir `CMFCColorDialog` nesne.|  
|`CMFCColorDialog::~CMFCColorDialog`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](#getcolor)|Geçerli seçili rengi döndürür.|  
|[CMFCColorDialog::GetPalette](#getpalette)|Renk paleti döndürür.|  
|`CMFCColorDialog::PreTranslateMessage`|Pencere iletileri için dağıtılmadan önce çevirir [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](https://msdn.microsoft.com/library/windows/desktop/ms644934) Windows işlevleri. Söz dizimi ve daha fazla bilgi için bkz: [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz kılmaları `CDialogEx::PreTranslateMessage`.)|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Sistem paletinden bir palet türetilir.|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Geçerli seçili rengini ayarlar.|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|Belirtilen bir RGB değeri en eşdeğer rengini ayarlar.|  
|[CMFCColorDialog::SetPageOne](#setpageone)|İlk özellik sayfası için bir RGB değeri seçer.|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|İkinci özellik sayfası için bir RGB değeri seçer.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`m_bIsMyPalette`|Renk seçimi iletişim kutusunu renk paletini kullanıyorsa TRUE veya FALSE iletişim kutusu içinde belirtilen bir palet kullanıyorsa `CMFCColorDialog` Oluşturucusu.|  
|`m_bPickerMode`|Kullanıcı bir renk seçimi iletişim kutusundan seçim sırasında TRUE; Aksi takdirde FALSE.|  
|`m_btnColorSelect`|Kullanıcının seçtiği bir renk düğmesi.|  
|`m_CurrentColor`|Şu anda seçili rengi.|  
|`m_hcurPicker`|İmleç bir renk seçmek için kullanılır.|  
|`m_NewColor`|Olası kalıcı olarak seçili veya özgün renge geri renk seçili.|  
|`m_pColourSheetOne`|Renk seçimi özellik sayfasının ilk özellik sayfası için bir işaretçi.|  
|`m_pColourSheetTwo`|Renk seçimi özellik sayfasının ikinci özellik sayfası için bir işaretçi.|  
|`m_pPalette`|Geçerli mantıksal paletini.|  
|`m_pPropSheet`|Renk seçimi iletişim kutusu için özellik sayfası için bir işaretçi.|  
|`m_wndColors`|Bir renk seçici denetim nesnesi.|  
|`m_wndStaticPlaceHolder`|Renk Seçici özellik sayfası için bir yer tutucudur statik denetimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Renk seçimi iletişim kutusunu bir özellik sayfasını iki sayfa olarak görüntülenir. İlk sayfasında, sistem paletten standart bir renk seçin; ikinci sayfasında, özel bir renk seçin.  
  
 Oluşturulabilir bir `CMFCColorDialog` yığında nesne ve sonra çağrı `DoModal`, ilk renk bir parametre olarak geçirerek `CMFCColorDialog` Oluşturucusu. Renk seçimi iletişim kutusunu daha sonra birkaç oluşturur [CMFCColorPickerCtrl sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md) her renk paletini işlemek için nesneler.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerle kullanarak renkli bir iletişimde yapılandırma işlemi gösterilmektedir `CMFCColorDialog` sınıfı. Örnek, geçerli ve yeni renklerinin iletişim nasıl ayarlanacağını ve seçili rengin kırmızı, yeşil ve mavi bileşenlerinin renk iletişim kutusu iki özellik sayfalarında ayarlama işlemini gösterir. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcolordialog.h  
  
##  <a name="cmfccolordialog"></a>  CMFCColorDialog::CMFCColorDialog  
 Oluşturur bir `CMFCColorDialog` nesne.  
  
```  
CMFCColorDialog(
    COLORREF clrInit=0,  
    DWORD dwFlags=0,  
    CWnd* pParentWnd=NULL,  
    HPALETTE hPal=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *clrInit*  
 Varsayılan renk seçimi. Değer belirtilmezse, varsayılan RGB(0,0,0) (siyah) olur.  
  
 [in] *CertOpenStore*  
 (Ayrılmış)  
  
 [in] *pParentWnd*  
 İletişim kutusunun üst veya sahip penceresine bir işaretçi.  
  
 [in] *hPal*  
 Renk paleti işleyici.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcolor"></a>  CMFCColorDialog::GetColor  
 Renk iletişim kutusundan kullanıcının seçtiği rengini alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](/windows/desktop/gdi/colorref) renk iletişim kutusunda seçilen renk RGB bilgilerini içeren bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra bu işlevi çağırın `DoModal` yöntemi.  
  
##  <a name="getpalette"></a>  CMFCColorDialog::GetPalette  
 Geçerli renk iletişim kutusunda kullanılabilir olan renk paletini alır.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CPalette` belirtilen nesne `CMFCColorDialog` Oluşturucusu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı seçebilir renklerin renk paletini belirtir.  
  
##  <a name="rebuildpalette"></a>  CMFCColorDialog::RebuildPalette  
 Sistem paletinden bir palet türetilir.  
  
```  
void RebuildPalette();
```  
  
##  <a name="setcurrentcolor"></a>  CMFCColorDialog::SetCurrentColor  
 İletişim kutusu geçerli rengini ayarlar.  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rgb*  
 Bir RGB renk değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setnewcolor"></a>  CMFCColorDialog::SetNewColor  
 Geçerli renk en benzer geçerli paletindeki rengini ayarlar.  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rgb*  
 A [COLORREF](/windows/desktop/gdi/colorref) bir RGB rengi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpageone"></a>  CMFCColorDialog::SetPageOne  
 Açıkça Seçili rengin kırmızı, yeşil ve mavi bileşenlerinin renkli bir iletişimde ilk özellik sayfasında belirtir.  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *R*  
 Kırmızı bileşeni RGB değeri belirtir.  
  
 [in] *G*  
 Yeşil bileşeni RGB değeri belirtir.  
  
 [in] *B*  
 Mavi bileşeni RGB değeri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpagetwo"></a>  CMFCColorDialog::SetPageTwo  
 Açıkça Seçili rengin kırmızı, yeşil ve mavi bileşenlerinin renkli bir iletişimde ikinci özellik sayfasında belirtir.  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *R*  
 RGB değeri kırmızı bir bileşeni belirtir.  
  
 [in] *G*  
 Bir RGB değeri yeşil bir bileşeni belirtir.  
  
 [in] *B*  
 Bir RGB değeri mavi bir bileşeni belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl Sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md)
