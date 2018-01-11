---
title: "CMFCFontInfo sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
dev_langs: C++
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d0ea0572667ef45264fd52934cd2d4ee750a6d4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo sınıfı
`CMFCFontInfo` Sınıfı adı ve başka bir yazı tipi özniteliklerini açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCFontInfo`|Oluşturan bir `CMFCFontInfo` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](#getfullname)|Bir yazı tipi ve onun karakter birleştirilmiş adlarını alır (komut) ayarlayın.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Yazı tipi ile ilişkilendirilmiş karakter kümesi (komut) belirten bir değer.|  
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Sıklık ve yazı tipi ailesi belirten bir değer.|  
|[CMFCFontInfo::m_nType](#m_ntype)|Yazı tipi türünü belirten bir değer.|  
|[CMFCFontInfo::m_strName](#m_strname)|Yazı tipi adı; Örneğin, **Arial**.|  
|[CMFCFontInfo::m_strScript](#m_strscript)|Yazı tipi ile ilişkilendirilmiş bir karakter kümesi (komut) adı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ekleyebilir miyim bir `CMFCFontInfo` nesne bir öğe için [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md) sınıfı. Çağrı [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) gösteren bir işaretçi alma yöntemi bir `CMFCFontInfo` nesnesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek üyelerine kullanımı gösterilmiştir `CMFCFontInfo` sınıfı. Örnek nasıl alındığını anlatan bir `CMFCFontInfo` nesnesinin bir `CMFCRibbonFontComboBox`ve yerel değişkenlerini erişim. Bu örneğin parçasıdır [MSOFFICE 2007 gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfcfontinfo"></a>CMFCFontInfo::CMFCFontInfo  
 Oluşturan bir `CMFCFontInfo` nesnesi.  
  
```  
CMFCFontInfo(
    LPCTSTR lpszName,  
    LPCTSTR lpszScript,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily,  
    int nType);  
  
CMFCFontInfo(const CMFCFontInfo& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszName`  
 Yazı tipi adı. Daha fazla bilgi için bkz: `lfFaceName` üyesi [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) yapısı.  
  
 [in]`lpszScript`  
 Yazı tipi komut dosyası (karakter kümesi) adı.  
  
 [in]`nCharSet`  
 Yazı tipi karakter kümesi (komut) belirten bir değer. Daha fazla bilgi için bkz: `lfCharSet` üyesi [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) yapısı.  
  
 [in]`nPitchAndFamily`  
 Sıklık ve yazı tipi ailesi belirten bir değer. Daha fazla bilgi için bkz: `lfPitchAndFamily` üyesi [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) yapısı.  
  
 [in]`nType`  
 Yazı tipi türünü belirten bir değer. Bu parametre DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE Bitsel bir birleşimi (veya) olabilir.  
  
 [in]`src`  
 Var olan `CMFCFontInfo` üyeleri bu oluşturmak için kullanılan nesne `CMFCFontInfo` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Bu belge koşullarını kullanır *karakter kümesi* ve *betik* birbirinin yerine. A *betik*, yazma sistemi olarak da bilinen olduğu koleksiyonudur karakter ve bir veya daha fazla dilde bu karakterleri yazmak için kurallar. Alfabesi ve bu komut dosyasında kullanılan noktalama karakterleri koleksiyonunu içerir. Örneğin, Latin betik Amerika Birleşik Devletleri'nde konuşulan ve A ile Z arasındaki karakterleri, alfabe içerir olarak İngilizce için kullanılır. `lfCharSet` Üyesi [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) yapısı bir karakter kümesini belirtir. Örneğin, değer `ANSI_CHARSET` belirtir [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] Latin betik alfabe içeren karakter kümesi.  
  
##  <a name="getfullname"></a>CMFCFontInfo::GetFullName  
 Bir yazı tipi ve onun karakter birleştirilmiş adlarını alır (komut) ayarlayın.  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazı tipi adı ve komut dosyası içeren bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazı tipinin tam adını almak için bu yöntemi kullanın. Örneğin, yazı tipi adı ise `Arial` ve yazı tipi `Cyrillic`, "Arial (Kiril)" Bu yöntemi döndürür.  
  
##  <a name="m_ncharset"></a>CMFCFontInfo::m_nCharSet  
 Yazı tipi ile ilişkilendirilmiş karakter kümesi (komut) belirten bir değer.  
  
```  
const BYTE m_nCharSet;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: `nCharSet` parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.  
  
##  <a name="m_npitchandfamily"></a>CMFCFontInfo::m_nPitchAndFamily  
 Sıklık (punto boyutunu) ve yazı tipi ailesi (örneğin, serif, sans-serif ve tek aralıklı) belirten bir değer.  
  
```  
const BYTE m_nPitchAndFamily;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: `nPitchAndFamily` parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.  
  
##  <a name="m_ntype"></a>CMFCFontInfo::m_nType  
 Yazı tipi türünü belirten bir değer.  
  
```  
const int m_nType;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: `nType` parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.  
  
##  <a name="m_strname"></a>CMFCFontInfo::m_strName  
 Yazı tipi adı: Örneğin, **Arial**.  
  
```  
const CString m_strName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: `lpszName` parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.  
  
##  <a name="m_strscript"></a>CMFCFontInfo::m_strScript  
 Yazı tipi ile ilişkilendirilmiş bir karakter kümesi (komut) adı.  
  
```  
const CString m_strScript;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: `lpszScript` parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox Sınıfı](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
