---
title: CMFCPropertyGridFileProperty sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c1ba2bb78260ade8dc95685789ec6af7e0ff58a
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038919"
---
# <a name="cmfcpropertygridfileproperty-class"></a>CMFCPropertyGridFileProperty sınıfı
`CMFCPropertyGridFileProperty` Sınıfı, bir dosya seçimi iletişim kutusunu açar bir özelliği liste denetim öğesi destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|Oluşturan bir `CMFCPropertyGridFileProperty` nesnesi.|  
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCPropertyGridFileProperty::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|`CMFCPropertyGridFileProperty::OnClickButton`|(Geçersiz kılmaları [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfileproperty"></a>  CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty  
 Oluşturan bir `CMFCPropertyGridFileProperty` nesnesi.  
  
```  
CMFCPropertyGridFileProperty(
    const CString& strName,  
    BOOL bOpenFileDialog,  
    const CString& strFileName,  
    LPCTSTR lpszDefExt=NULL,  
    DWORD dwFlags=OFN_HIDEREADONLY|OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter=NULL,  
    LPCTSTR lpszDescr=NULL,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *strName*  
 Özellik adı.  
  
 [in] *bOpenFileDialog*  
 `TRUE` açmak için bir **Dosya Aç** iletişim kutusu; `FALSE` açmak için bir **dosyayı Kaydet** iletişim kutusu.  
  
 [in] *strFileName*  
 İlk dosya adı.  
  
 [in] *lpszDefExt*  
 Bir veya daha fazla dosya adı uzantılarını dizesi. Varsayılan değer `NULL` şeklindedir.  
  
 [in] *dwFlags*  
 İletişim kutusu bayraklar. Bit düzeyinde bileşimini (veya) varsayılan değerdir `OFN_HIDEREADONLY` ve `OFN_OVERWRITEPROMPT`.  
  
 [in] *lpszFilter*  
 Bir veya daha fazla dosya filtreleri dizesi. Varsayılan değer `NULL` şeklindedir.  
  
 [in] *lpszDescr*  
 Özellik öğesi açıklaması. Varsayılan değer `NULL` şeklindedir.  
  
 [in] *dwData*  
 Özellik öğesi ile ilişkilendirilen uygulamaya özgü verileri. Örneğin, bir 32 bit tamsayı veya diğer veri için bir işaretçi. Varsayılan değer 0’dır.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılabilir bayrakları tam bir listesi için bkz: [AÇIKDOSYAADI yapısı](https://msdn.microsoft.com/library/ms646839.aspx).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, oluşturucusunun kullanan bir nesne oluşturmak gösterilmiştir `CMFCPropertyGridFileProperty` sınıfı. Bu örneğin parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
