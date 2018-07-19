---
title: CMFCRibbonFontComboBox sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2eb5fa8f56f242ce40f6be9c27bc1cbd9c5d61ff
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852529"
---
# <a name="cmfcribbonfontcombobox-class"></a>CMFCRibbonFontComboBox sınıfı
Yazı tiplerinin bir listesini içeren bir birleşik giriş kutusu uygular. Bir Şerit panel üzerine birleşik giriş kutusu yerleştirin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Yıkıcı.|  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|Oluşturur ve başlatır bir `CMFCRibbonFontComboBox` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|Şerit yazı tipi birleşik giriş kutusunun yazı tipleri ile belirtilen yazı tipi, karakter kümesi aralığı ve ailesi doldurur.|  
|`CMFCRibbonFontComboBox::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|  
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|Belirtilen karakter kümesini döndürür.|  
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||  
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|Birleşik giriş kutusu içinde görüntülemek için hangi yazıtiplerini döndürür. DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE ya da bir bit düzeyinde birleşimlere geçerli seçenekler şunlardır.|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|Aralık ve birleşik giriş kutusunda görüntülenen yazı tipi ailesi döndürür.|  
|`CMFCRibbonFontComboBox::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|Şerit yazı tipi birleşik giriş kutusunun yazı tipleri ile daha önce belirtilen yazı tipi, karakter kümesi aralığı ve ailesi doldurur.|  
|[CMFCRibbonFontComboBox::SetFont](#setfont)|Belirtilen yazı tipi birleşik giriş kutusunda seçer.|  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturduktan sonra bir `CMFCRibbonFontComboBox` nesne, çağırarak bir Şerit paneline Ekle [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonComboBox.h  
  
##  <a name="buildfonts"></a>  CMFCRibbonFontComboBox::BuildFonts  
 Yazı tipleri ile Şerit birleşik giriş kutusunu doldurur.  
  
```  
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFontType*  
 Yazı tipi eklemek için yazı tipini belirtir.  
  
 [in] *nCharSet*  
 Eklenecek yazı tiplerinin karakter kümesini belirtir.  
  
 [in] *nPitchAndFamily*  
 Eklenecek yazı tipi ailesi ve sıklıktaki değişimi belirtir.  
  
##  <a name="cmfcribbonfontcombobox"></a>  CMFCRibbonFontComboBox::CMFCRibbonFontComboBox  
 Oluşturur ve başlatır bir [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md) nesne.  
  
```  
CMFCRibbonFontComboBox(
    UINT nID,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH,  
    int nWidth = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nID*  
 Kullanıcı birleşik giriş kutusundan bir öğe seçtiğinde yürüten komutu komut kimliği.  
  
 [in] *nFontType*  
 Yazı tipi birleşik giriş kutusunda görüntülenecek türlerini belirtir. DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE ya da bir bit düzeyinde birleşimlere geçerli seçenekler şunlardır.  
  
 [in] *nCharSet*  
 Yazı tipi birleşik giriş kutusunda belirtilen karakter kümesine ait olanlar filtreler...  
  
 [in] *nPitchAndFamily*  
 Aralık ve birleşik giriş kutusunda görüntülenen yazı tipi ailesini belirtir.  
  
 [in] *nWidth*  
 Birleşik giriş kutusu piksel cinsinden genişliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası hakkında daha fazla bilgi için *nFontType* parametre değerleri görmek [EnumFontFamProc](http://msdn.microsoft.com/library/windows/desktop/dd162621) Windows SDK belgelerinde.  
  
 Atanabilir geçerli karakter kümeleri hakkında daha fazla bilgi için *nCharSet*ve atanabilir geçerli değerleri *nPitchAndFamily*, bkz: [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) içinde Windows SDK Belgeleri.  
  
##  <a name="getfontdesc"></a>  CMFCRibbonFontComboBox::GetFontDesc  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *İIndex*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="rebuildfonts"></a>  CMFCRibbonFontComboBox::RebuildFonts  
 Yazı tipleri ile Şerit birleşik giriş kutusunu bir daha önce belirtilen yazı tipi, karakter kümesi aralığı ve ailesi doldurur.  
  
```  
void RebuildFonts();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yazı tipi, karakter kümesini belirtebilirsiniz ve aralık ve Şerit yazı tipi birleşik giriş eklenecek yazı tipi ailesi kutusunda [Oluşturucusu](#cmfcribbonfontcombobox) bu sınıfın veya çağırarak [CMFCRibbonFontComboBox::BuildFonts](#buildfonts).  
  
##  <a name="setfont"></a>  CMFCRibbonFontComboBox::SetFont  
 Belirtilen yazı tipi birleşik giriş kutusunda seçer.  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BOOL bExact = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 ' lpszName *  
 Seçmek için yazı tipinin adını belirtir.  
  
 *nCharSet*  
 Karakter kümesi için seçili yazı tipini belirtir.  
  
 *bExact*  
 Karakter kümesi bir yazı tipi seçerken eşleşmesi gerektiğini belirtmek için TRUE; Karakter kümesi belirtmek için yanlış bir yazı tipi seçerken yoksayılabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen yazı tipi bulundu ve seçili olursa sıfır dışı; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcharset"></a>  CMFCRibbonFontComboBox::GetCharSet  
 Belirtilen karakter kümesini döndürür.  
  
```  
BYTE GetCharSet() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 (Windows SDK belgelerinde LOGFONT bakın) karakter kümesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getfonttype"></a>  CMFCRibbonFontComboBox::GetFontType  
 Birleşik giriş kutusu içinde görüntülemek için hangi yazıtiplerini döndürür. DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE ya da bir bit düzeyinde birleşimlere geçerli seçenekler şunlardır.  
  
```  
int GetFontType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazı tipi türleri (Windows SDK belgelerinde EnumFontFamProc bakın).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpitchandfamily"></a>  CMFCRibbonFontComboBox::GetPitchAndFamily  
 Aralık ve birleşik giriş kutusunda görüntülenen yazı tipi ailesi döndürür.  
  
```  
BYTE GetPitchAndFamily() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aralık ve ailesi (Windows SDK belgelerinde LOGFONT bakın).  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonComboBox Sınıfı](../../mfc/reference/cmfcribboncombobox-class.md)
