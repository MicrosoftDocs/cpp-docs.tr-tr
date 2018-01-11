---
title: "CMFCRibbonFontComboBox sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fab339300de907169ab7f4471d9892feadffad81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonfontcombobox-class"></a>CMFCRibbonFontComboBox sınıfı
Yazı tipleri listesini içeren bir birleşik giriş kutusu uygular. Birleşik giriş kutusu Şerit panelde yerleştirin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Yok Edicisi.|  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|Oluşturur ve başlatır bir `CMFCRibbonFontComboBox` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|Şerit yazı tipi birleşik giriş kutusu yazı tipleriyle belirtilen yazı tipi, karakter kümesi aralığı ve ailesi doldurur.|  
|`CMFCRibbonFontComboBox::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|Belirtilen karakter kümesini döndürür.|  
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||  
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|Birleşik giriş kutusu içinde görüntülemek için hangi yazıtiplerini döndürür. Geçerli seçenekler şunlardır: DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE ya da bunların bir Bitsel birleşimine göre.|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|Sıklık ve açılan kutuda görüntülenen yazı tipi ailesi döndürür.|  
|`CMFCRibbonFontComboBox::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|Şerit yazı tipi birleşik giriş kutusu yazı tipleriyle daha önce belirtilen yazı tipi, karakter kümesi aralığı ve ailesi doldurur.|  
|[CMFCRibbonFontComboBox::SetFont](#setfont)|Belirtilen yazı tipi açılan kutuda seçer.|  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturduktan sonra bir `CMFCRibbonFontComboBox` nesne, çağırarak bir Şerit paneline eklemek [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonComboBox.h  
  
##  <a name="buildfonts"></a>CMFCRibbonFontComboBox::BuildFonts  
 Yazı tipleri Şerit üzerindeki birleşik giriş kutusunu doldurur.  
  
```  
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nFontType`  
 Eklemek için yazı tipi yazı tipini belirtir.  
  
 [in]`nCharSet`  
 Yazı tipleri eklemek için karakter kümesini belirtir.  
  
 [in]`nPitchAndFamily`  
 Sıklık ve eklemek için yazı tipi ailesi belirtir.  
  
##  <a name="cmfcribbonfontcombobox"></a>CMFCRibbonFontComboBox::CMFCRibbonFontComboBox  
 Oluşturur ve başlatır bir [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md) nesnesi.  
  
```  
CMFCRibbonFontComboBox(
    UINT nID,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH,  
    int nWidth = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Kullanıcı açılan kutusundan bir öğe seçtiğinde yürütür komutu komut kimliği.  
  
 [in]`nFontType`  
 Birleşik giriş kutusu içinde görüntülemek için hangi yazı tipi türlerini belirtir. Geçerli seçenekler şunlardır: **DEVICE_FONTTYPE**, **RASTER_FONTTYPE**, ve **TRUETYPE_FONTTYPE**, veya bunların bir Bitsel birleşimine göre.  
  
 [in]`nCharSet`  
 Belirtilen karakter kümesine ait olanlar için birleşik giriş kutusu yazı tipleri filtreler...  
  
 [in]`nPitchAndFamily`  
 Sıklık ve açılan kutuda görüntülenen yazı tipi ailesi belirtir.  
  
 [in]`nWidth`  
 Birleşik giriş kutusu piksel cinsinden genişliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası hakkında daha fazla bilgi için `nFontType` parametre değerlerini görmek [EnumFontFamProc](http://msdn.microsoft.com/library/windows/desktop/dd162621) Windows SDK belgelerinde.  
  
 Atanabilir geçerli karakter kümeleri hakkında daha fazla bilgi için `nCharSet`ve atanabilir geçerli değerler `nPitchAndFamily`, bkz: [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Windows SDK belgelerinde.  
  
##  <a name="getfontdesc"></a>CMFCRibbonFontComboBox::GetFontDesc  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="rebuildfonts"></a>CMFCRibbonFontComboBox::RebuildFonts  
 Daha önce belirtilen yazı tipi, karakter kümesi ve sıklık ve ailesi tipleriyle Şerit üzerindeki birleşik giriş kutusunu doldurur.  
  
```  
void RebuildFonts();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Karakter kümesi, yazı tipi belirtebilirsiniz ve sıklık ve Şerit yazı tipi Kombo dahil etmek için yazı tipi ailesi kutusunda [Oluşturucusu](#cmfcribbonfontcombobox) Bu sınıf için ya da çağırarak [CMFCRibbonFontComboBox::BuildFonts](#buildfonts).  
  
##  <a name="setfont"></a>CMFCRibbonFontComboBox::SetFont  
 Belirtilen yazı tipi açılan kutuda seçer.  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BOOL bExact = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Seçmek için yazı tipinin adını belirtir.  
  
 `nCharSet`  
 Karakter kümesi seçili yazı tipini belirtir.  
  
 `bExact`  
 `TRUE`karakter kümesi bir yazıtipi seçerken eşleşmesi gerektiğini belirtmek için; `FALSE` karakter kümesi bir yazıtipi seçerken yoksayılabilir belirtmek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen yazı tipi bulundu ve seçili sıfır olmayan; Aksi durumda, sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcharset"></a>CMFCRibbonFontComboBox::GetCharSet  
 Belirtilen karakter kümesini döndürür.  
  
```  
BYTE GetCharSet() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 (Windows SDK belgelerinde LOGFONT bakın) karakter kümesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getfonttype"></a>CMFCRibbonFontComboBox::GetFontType  
 Birleşik giriş kutusu içinde görüntülemek için hangi yazıtiplerini döndürür. Geçerli seçenekler şunlardır: DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE ya da bunların bir Bitsel birleşimine göre.  
  
```  
int GetFontType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazı tipi türleri (EnumFontFamProc Windows SDK belgelerine bakın).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpitchandfamily"></a>CMFCRibbonFontComboBox::GetPitchAndFamily  
 Sıklık ve açılan kutuda görüntülenen yazı tipi ailesi döndürür.  
  
```  
BYTE GetPitchAndFamily() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıklık ve ailesi (LOGFONT Windows SDK belgelerine bakın).  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonComboBox Sınıfı](../../mfc/reference/cmfcribboncombobox-class.md)
