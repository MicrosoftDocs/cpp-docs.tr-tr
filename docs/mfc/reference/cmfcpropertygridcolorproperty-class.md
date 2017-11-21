---
title: "CMFCPropertyGridColorProperty sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
dev_langs: C++
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d00258a8171dc5b9786961879eccee1743b84da1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty sınıfı
`CMFCPropertyGridColorProperty` Sınıfı, bir renk seçimi iletişim kutusunu açar bir özelliği liste denetim öğesi destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Oluşturan bir `CMFCPropertyGridColorProperty` nesnesi.|  
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Etkinleştirir *otomatik* renk seçimi iletişim kutusunu düğmesinde. (Standart otomatik düğme etiketli **otomatik**.)|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Etkinleştirir *diğer* renk seçimi iletişim kutusunu düğmesinde. (Standart diğer düğme etiketini **daha renkleri**.)|  
|`CMFCPropertyGridColorProperty::FormatProperty`|Bir özellik değeri metin gösterimini biçimlendirir. (Geçersiz kılmaları [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|Özelliği geçerli rengi alır.|  
|`CMFCPropertyGridColorProperty::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|`CMFCPropertyGridColorProperty::OnClickButton`|Kullanıcı bir özelliğinde yer alan bir düğmesini tıklattığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|Özellik değerini görüntülemek için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|  
|`CMFCPropertyGridColorProperty::OnEdit`|Kullanıcı hakkında bir özellik değerini değiştirmek için olduğunda çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Düzenlenebilir bir özellik değeri değiştiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|  
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|Özelliği için yeni bir renk ayarlar.|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Sütun sayısı geçerli renk özellik kılavuzunda belirtir.|  
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Düzenlenebilir bir özelliğinin özgün değeri ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCPropertyGridColorProperty` Sınıfı, bir özellik listesi denetimine eklenebilir bir renk özelliğini destekler. Daha fazla bilgi için bkz: [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCPropertyGridColorProperty` sınıfı ve çeşitli yöntemleri kullanarak bu nesneyi yapılandırma `CMFCPropertyGridColorProperty` sınıfı. Kodu otomatik ve diğer düğmeleri etkinleştirme ve rengi ve sütun numarası nasıl ayarlanacağı açıklanmaktadır. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridcolorproperty"></a>CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty  
 Oluşturan bir `CMFCPropertyGridColorProperty` nesnesi.  
  
```  
CMFCPropertyGridColorProperty(
    const CString& strName,  
    const COLORREF& color,  
    CPalette* pPalette = NULL,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`strName`  
 Özelliğin adı.  
  
 [in]`color`  
 Özelliğin renk değeri.  
  
 [in]`pPalette`  
 Renk paletini işaretçi. Varsayılan değer `NULL` şeklindedir.  
  
 [in]`lpszDescr`  
 Özellik açıklaması. Varsayılan değer `NULL` şeklindedir.  
  
 [in]`dwData`  
 Bir tamsayı ya da özelliği ile ilişkili diğer veri için bir işaretçi gibi uygulamaya özgü verileri. Varsayılan değer 0’dır.  
  
##  <a name="enableautomaticbutton"></a>CMFCPropertyGridColorProperty::EnableAutomaticButton  
 Etkinleştirir *otomatik* renk seçimi iletişim kutusunu düğmesinde. (Standart otomatik düğme etiketli **otomatik**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Otomatik düğmesinin etiket metni.  
  
 [in]`colorAutomatic`  
 Otomatik (varsayılan) renk RGB renk değeri.  
  
 [in]`bEnable`  
 `TRUE`Otomatik düğmesini etkinleştirmek için; Aksi takdirde `FALSE`. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enableotherbutton"></a>CMFCPropertyGridColorProperty::EnableOtherButton  
 Etkinleştirir *diğer* renk seçimi iletişim kutusunu düğmesinde. (Standart diğer düğme etiketini **daha renkleri**.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg = TRUE,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Diğer düğmesinin etiket metni.  
  
 [in]`bAltColorDlg`  
 `TRUE`Görüntülenecek `CMFCColorDialog` iletişim kutusu; `FALSE` standart renk seçimi iletişim kutusunu görüntüleyin. Varsayılan değer `TRUE` şeklindedir.  
  
 [in]`bEnable`  
 `TRUE`diğer düğmesini görüntülemek için; Aksi takdirde `FALSE`.  Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcolor"></a>CMFCPropertyGridColorProperty::GetColor  
 Özelliği geçerli rengi alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setcolor"></a>CMFCPropertyGridColorProperty::SetColor  
 Özelliği için yeni bir renk ayarlar.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`color`  
 RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setcolumnsnumber"></a>CMFCPropertyGridColorProperty::SetColumnsNumber  
 Sütun sayısı geçerli renk özellik kılavuzunda belirtir.  
  
```  
void SetColumnsNumber(int nColumnsNumber);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nColumnsNumber`  
 Renk özellik kılavuzunda sütun tercih edilen sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem değerini ayarlar `m_nColumnsNumber` veri üyesi korumalı.  
  
##  <a name="setoriginalvalue"></a>CMFCPropertyGridColorProperty::SetOriginalValue  
 Düzenlenebilir bir özelliğinin özgün değeri ayarlar.  
  
```  
virtual void SetOriginalValue(const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`varValue`  
 Bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCPropertyGridProperty::ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) düzenlenen özelliğinin özgün değeri sıfırlama yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
