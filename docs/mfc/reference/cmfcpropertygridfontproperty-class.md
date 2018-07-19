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
ms.openlocfilehash: 3ea43fefabe43bec8a5bf9b00404491a405e5416
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852987"
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty sınıfı
`CMFCPropertyGridFileProperty` Sınıfı, bir yazı tipi seçimi iletişim kutusunu açan bir özellik listesi denetim öğesini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Oluşturur bir `CMFCPropertyGridFontProperty` nesne.|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|Özellik değerinin metin temsilini biçimlendirir. (Geçersiz kılmaları [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Yazı tipi iletişim kutusundan kullanıcının seçtiği yazı tipi rengini alır.|  
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Yazı tipi iletişim kutusundan kullanıcının seçtiği yazı tipini alır.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|Kullanıcı bir özelliğinde bulunan bir düğmeye tıkladığında framework tarafından çağırılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfontproperty"></a>  CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty  
 Oluşturur bir `CMFCPropertyGridFontProperty` nesne.  
  
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
 [in] *strName*  
 Özelliğin adı.  
  
 [in] *lf*  
 Yazı tipi özniteliklerini belirtir mantıksal yazı tipi yapısı.  
  
 [in] *dwFontDialogFlags*  
 Özellik değeri açılan Düğmeye tıkladığınızda görüntülenen yazı tipi iletişim kutusu için uygulanan stiller. Bit düzeyinde birleşimi (veya) CF_EFFECTS ve CF_SCREENFONTS varsayılan değerdir. Daha fazla bilgi için *bayrakları* parametresinin [CHOOSEFONT yapısı](http://msdn.microsoft.com/library/windows/desktop/ms646832).  
  
 [in] *lpszDescr*  
 Yazı tipi özellik açıklaması. Varsayılan değer NULL olur.  
  
 [in] *dwData*  
 Uygulamaya özgü verileri, bir tamsayı ya da özellikle ilişkili diğer veri işaretçisi gibi. Varsayılan değer 0’dır.  
  
 [in] *rengi*  
 Yazı tipi rengi. Varsayılan renk varsayılan değerdir.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CMFCPropertyGridFontProperty` nesnesi bir yazı tipi özelliği bir özellik Kılavuzu yazı tipi denetimini temsil eder.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, gösterir nasıl bir nesne oluşturun `CMFCPropertyGridFontProperty` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]  
  
##  <a name="getcolor"></a>  CMFCPropertyGridFontProperty::GetColor  
 Yazı tipi iletişim kutusundan kullanıcının seçtiği yazı tipi rengini alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazı tipi rengi temsil eden bir RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getlogfont"></a>  CMFCPropertyGridFontProperty::GetLogFont  
 Yazı tipi iletişim kutusundan kullanıcının seçtiği yazı tipini alır.  
  
```  
LPLOGFONT GetLogFont();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) seçili yazı tipini açıklayan yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty Sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
