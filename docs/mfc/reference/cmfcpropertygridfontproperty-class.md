---
title: CMFCPropertyGridFontProperty sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e7acda3bf3734a325c7d603489c1305cb63bc3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty sınıfı
`CMFCPropertyGridFileProperty` Sınıfı, yazı tipi seçimi iletişim kutusunu açan özelliği liste denetim öğesi destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Oluşturan bir `CMFCPropertyGridFontProperty` nesnesi.|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|Bir özellik değeri metin gösterimini biçimlendirir. (Geçersiz kılmaları [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Yazı tipi iletişim kutusu kullanıcının seçtiği yazı tipi rengi alır.|  
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Yazı tipi iletişim kutusu kullanıcının seçtiği yazı tipini alır.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|Kullanıcı bir özelliğinde yer alan bir düğmesini tıklattığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfontproperty"></a>  CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty  
 Oluşturan bir `CMFCPropertyGridFontProperty` nesnesi.  
  
```  
CMFCPropertyGridFontProperty(
    const CString& strName,  
    LOGFONT& lf,  
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0,  
    COLORREF color = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `strName`  
 Özelliğin adı.  
  
 [in] `lf`  
 Yazı tipi özniteliklerini belirtir mantıksal yazı tipi yapısı.  
  
 [in] `dwFontDialogFlags`  
 Özellik değeri açılan düğmesine tıkladığınızda görüntülenen yazı tipi iletişim kutusu uygulanan stil. Varsayılan değer Bitsel (veya) CF_EFFECTS ve CF_SCREENFONTS birleşimidir. Daha fazla bilgi için bkz: `Flags` parametresinin [CHOOSEFONT yapısı](http://msdn.microsoft.com/library/windows/desktop/ms646832).  
  
 [in] `lpszDescr`  
 Font özelliği açıklaması. Varsayılan değer `NULL` şeklindedir.  
  
 [in] `dwData`  
 Bir tamsayı ya da özelliği ile ilişkili diğer veri için bir işaretçi gibi uygulamaya özgü verileri. Varsayılan değer 0’dır.  
  
 [in] `color`  
 Yazı tipi rengi. Varsayılan rengini varsayılan değerdir.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CMFCPropertyGridFontProperty` nesnesi özelliği kılavuz yazı tipi denetiminde font özelliği temsil eder.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterilmiştir nasıl bir nesne oluşturun `CMFCPropertyGridFontProperty` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]  
  
##  <a name="getcolor"></a>  CMFCPropertyGridFontProperty::GetColor  
 Yazı tipi iletişim kutusu kullanıcının seçtiği yazı tipi rengi alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazı tipi rengi temsil eden bir RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getlogfont"></a>  CMFCPropertyGridFontProperty::GetLogFont  
 Yazı tipi iletişim kutusu kullanıcının seçtiği yazı tipini alır.  
  
```  
LPLOGFONT GetLogFont();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) seçili yazı tipi tanımlar yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
