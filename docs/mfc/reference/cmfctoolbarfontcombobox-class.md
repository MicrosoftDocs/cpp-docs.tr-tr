---
title: CMFCToolBarFontComboBox sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea8f05c20c3a3276f51b4267b6763831dc23eacf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373533"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox sınıfı
Yazı tipleri listesinden bir yazı tipi seçmek kullanıcının sağlayan bir birleşik giriş kutusu denetimi içeren bir araç çubuğu düğmesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|Oluşturan bir `CMFCToolBarFontComboBox` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|Bir işaretçi döndürür `CMFCFontInfo` nesne için belirtilen bir birleşik giriş kutusu dizini.|  
|[CMFCToolBarFontComboBox::SetFont](#setfont)|Yazı tipi adı ya da yazı tipini öneki ve karakter kümesini yazı tipi açılan kutuya göre ya da bir yazıtipi seçer.|  
  
### <a name="data-members"></a>Veri üyeleri  
 [CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)  
 Yazı tipi birleşik giriş kutusu karakterleri yüksekliği.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir araç için bir yazı tipi birleşik giriş kutusu düğmesi eklemek için aşağıdaki adımları izleyin:  
  
1.  Bir kukla kaynağı kimliği üst araç çubuğu kaynak düğmesi için ayrılmış.  
  
2.  Oluşturmak bir `CMFCToolBarFontComboBox` nesnesi.  
  
3.  İşler ileti işleyicisi'ndeki `AFX_WM_RESETTOOLBAR` iletisi, özgün düğmesini kullanarak yeni birleşik giriş kutusu düğmesi ile değiştirin [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
4.  Açılan kutuda belgedeki yazı tipi ile kullanarak seçili yazı tipi eşitleme [CMFCToolBarFontComboBox::SetFont](#setfont) yöntemi.  
  
 Belgenin yazı tipi açılan kutuda seçilen yazı tipi ile eşitlemek için kullanmak [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc) seçili yazı tipi özniteliklerini almak ve oluşturmak için öznitelikleri kullanma yöntemi bir [ CFont sınıfı](../../mfc/reference/cfont-class.md) nesnesi.  
  
 Yazı tipi birleşik giriş kutusu düğmesi Win32 işlevi çağırır [EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620) sistemi için kullanılabilir ekran ve yazıcı yazı belirlemek için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontcombobox"></a>  CMFCToolBarFontComboBox::CMFCToolBarFontComboBox  
 Oluşturan bir [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) nesnesi.  
  
```  
public:  
CMFCToolBarFontComboBox(
    UINT uiID,  
    int iImage,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    DWORD dwStyle = CBS_DROPDOWN,  
    int iWidth = 0,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);

 
protected:  
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,  
    int nFontType,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily);  
  
CMFCToolBarFontComboBox();
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiID`  
 Birleşik giriş kutusu komut kimliği.  
  
 [in] `iImage`  
 Araç çubuğu görüntüsünü sıfır tabanlı dizini. Görüntü bulunan [CMFCToolBarImages sınıfı](../../mfc/reference/cmfctoolbarimages-class.md) nesnesinin [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfı korur.  
  
 [in] `nFontType`  
 Birleşik giriş kutusu içeren yazı tipleri türleri. Bu parametre birleşimi (Boole veya) aşağıdaki değerlerden biri olabilir:  
  
 DEVICE_FONTTYPE  
  
 RASTER_FONTTYPE  
  
 TRUETYPE_FONTTYPE  
  
 [in] `nCharSet`  
 DEFAULT_CHARSET, birleşik giriş kutusu kümesine tüm karakter kümelerini yazı tiplerini tüm benzersiz olarak adlandırılmış içeriyorsa. (Aynı ada sahip iki yazı tipi varsa, birleşik giriş kutusu bunlardan birini içerir.) Geçerli karakter kümesi değeri, birleşik giriş kutusu kümesine yalnızca belirtilen karakter kümesinde yazı tiplerini içeriyorsa. Bkz: [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) olası karakteri bir listesi için ayarlar.  
  
 [in] `dwStyle`  
 Birleşik giriş kutusu stili. (bkz [birleşik giriş kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))  
  
 [in] `iWidth`  
 Düzen denetimin piksel cinsinden genişliği.  
  
 [in] `nPitchAndFamily`  
 DEFAULT_PITCH, birleşik giriş kutusu kümesine aralık bağımsız olarak yazı tipleri içeriyorsa. FIXED_PITCH veya VARIABLE_PITCH olarak ayarlayın, birleşik giriş kutusu yalnızca bu aralık türüyle yazı tiplerini içeriyorsa. Yazı tipi ailesi göre filtreleme şu anda desteklenmiyor.  
  
 [out] `pLstFontsExternal`  
 İşaretçi bir [CObList sınıfı](../../mfc/reference/coblist-class.md) yazı tiplerini depolar nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, `CMFCToolBarFontComboBox` nesneleri depolamak kullanılabilir yazı tipi listesi tek bir paylaşılan `CObList` nesnesi. İkinci oluşturucu kullanın ve geçerli bir işaretçi sağlamak `pLstFontsExternal`, o `CMFCToolBarFontComboBox` nesne yerine doldurur `CObList` , `pLstFontsExternal` kullanılabilir yazı tipleriyle işaret eder.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCToolBarFontComboBox` nesnesi. Bu kod parçacığını parçası olan [Word paneli örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]  
  
##  <a name="getfontdesc"></a>  CMFCToolBarFontComboBox::GetFontDesc  
 Bir işaretçi döndürür `CMFCFontInfo` nesne için belirtilen bir birleşik giriş kutusu dizini.  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iIndex`  
 Birleşik giriş kutusu öğesi sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CMFCFontInfo` nesnesi. Varsa `iIndex` geçerli öğe dizini belirtmiyor dönüş değeri `NULL`.  
  
##  <a name="m_nfontheight"></a>  CMFCToolBarFontComboBox::m_nFontHeight  
 Birleşik giriş kutusu stili çizin sahibi varsa yazı tipi birleşik giriş kutusu karakter piksel cinsinden yüksekliği belirtir.  
  
```  
static int m_nFontHeight  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `m_nFontHeight` değişkeni 0, yükseklik birleşik giriş kutusu varsayılan yazı tipi göre otomatik olarak hesaplanır. Yükseklik hem karakter taban çizgisinin Yokuş ve taban altında karakter düşüşü içerir.  
  
##  <a name="setfont"></a>  CMFCToolBarFontComboBox::SetFont  
 Parametrelerinde belirtilen yazı tipi birleşik giriş kutusu yazı tipi adı ve karakter göre yazı tipini kümesi seçer.  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BOOL bExact=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszName`  
 Yazı tipi adı ya da öneki belirtir.  
  
 [in] `nCharSet`  
 Karakter kümesini belirtir.  
  
 [in] `bExact`  
 Belirtir olup olmadığını `lpszName` yazı tipi adı veya yazı tipi önek içeriyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazı tipi başarıyla seçildiyse, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bExact` olan `TRUE`, bu yöntem tam olarak belirtilen adla eşleşen bir yazıtipi seçer `lpszName`. Varsa `bExact` olan `FALSE`, bu yöntem olarak belirtilen metin ile başlayan bir yazıtipi seçer `lpszName` olarak belirtilen karakter kümesi kullanan ve `nCharSet`. Varsa `nCharSet` ayarlanır DEFAULT_CHARSET için yoksayıldı ve yalnızca karakter kümesi olacak `lpszName` bir yazı tipi seçmek için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo sınıfı](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



