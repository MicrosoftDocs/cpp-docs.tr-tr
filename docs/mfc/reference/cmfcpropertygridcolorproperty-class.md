---
title: CMFCPropertyGridColorProperty Class
ms.date: 11/04/2016
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
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
ms.openlocfilehash: 95dcbbc2b445e2ff67979b90816daed0fb0c0fba
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767723"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty Class

`CMFCPropertyGridColorProperty` Sınıfı, bir renk seçimi iletişim kutusunu açan bir özellik listesi denetim öğesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Oluşturur bir `CMFCPropertyGridColorProperty` nesne.|
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Sağlar *otomatik* renk seçimi iletişim kutusunu düğmesi. (Standart otomatik düğme **otomatik**.)|
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Sağlar *diğer* renk seçimi iletişim kutusunu düğmesi. (Standart diğer düğme **daha fazla renk**.)|
|`CMFCPropertyGridColorProperty::FormatProperty`|Özellik değerinin metin temsilini biçimlendirir. (Geçersiz kılmaları [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|Geçerli özelliğin rengini alır.|
|`CMFCPropertyGridColorProperty::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|`CMFCPropertyGridColorProperty::OnClickButton`|Kullanıcı bir özelliğinde bulunan bir düğmeye tıkladığında framework tarafından çağırılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|
|`CMFCPropertyGridColorProperty::OnDrawValue`|Özellik değeri görüntülemek için framework tarafından çağırılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|
|`CMFCPropertyGridColorProperty::OnEdit`|Kullanıcı yaklaşık bir özellik değerini değiştirmek için çerçeve tarafından çağrılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Düzenlenebilir bir özellik değeri değiştiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCPropertyGridProperty::OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|Yeni bir özelliğin rengini ayarlar.|
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Geçerli renk özellik kılavuzunda sütun sayısını belirtir.|
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Özgün düzenlenebilir bir özelliğin değerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CMFCPropertyGridColorProperty` Sınıfı için bir özellik liste denetiminin eklenebilir bir renk özelliğini destekler. Daha fazla bilgi için [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCPropertyGridColorProperty` sınıfı ve çeşitli yöntemleri kullanarak bu nesneyi yapılandırma `CMFCPropertyGridColorProperty` sınıfı. Kod, otomatik ve diğer düğmeleri etkinleştirme ve renk ve sütun sayısını nasıl ayarlanacağı açıklanmaktadır. Bu örneğin parçasıdır [yeni denetimler örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxpropertygridctrl.h

##  <a name="cmfcpropertygridcolorproperty"></a>  CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty

Oluşturur bir `CMFCPropertyGridColorProperty` nesne.

```
CMFCPropertyGridColorProperty(
    const CString& strName,
    const COLORREF& color,
    CPalette* pPalette = NULL,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0);
```

### <a name="parameters"></a>Parametreler

*strName*<br/>
[in] Özelliğin adı.

*Renk*<br/>
[in] Özelliğin renk değeri.

*pPalette*<br/>
[in] Renk paleti işaretçisi. Varsayılan değer NULL olur.

*lpszDescr*<br/>
[in] Özellik açıklaması. Varsayılan değer NULL olur.

*dwData*<br/>
[in] Uygulamaya özgü verileri, bir tamsayı ya da özellikle ilişkili diğer veri işaretçisi gibi. Varsayılan değer 0’dır.

##  <a name="enableautomaticbutton"></a>  CMFCPropertyGridColorProperty::EnableAutomaticButton

Sağlar *otomatik* renk seçimi iletişim kutusunu düğmesi. (Standart otomatik düğme **otomatik**.)

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
[in] Otomatik düğmenin etiket metni.

*colorAutomatic*<br/>
[in] Otomatik (varsayılan) renk RGB renk değeri.

*bSistemlerde*<br/>
[in] Otomatik düğmenin etkinleştirmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.

### <a name="remarks"></a>Açıklamalar

##  <a name="enableotherbutton"></a>  CMFCPropertyGridColorProperty::EnableOtherButton

Sağlar *diğer* renk seçimi iletişim kutusunu düğmesi. (Standart diğer düğme **daha fazla renk**.)

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
[in] Diğer düğmenin etiket metni.

*bAltColorDlg*<br/>
[in] Görüntülemek true `CMFCColorDialog` ; iletişim kutusu Standart renk seçimi iletişim kutusunu görüntülemek için FALSE. Varsayılan değer True'dur.

*bSistemlerde*<br/>
[in] Bir düğme görüntülemek için TRUE; Aksi takdirde FALSE.  Varsayılan değer True'dur.

### <a name="remarks"></a>Açıklamalar

##  <a name="getcolor"></a>  CMFCPropertyGridColorProperty::GetColor

Geçerli özelliğin rengini alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="setcolor"></a>  CMFCPropertyGridColorProperty::SetColor

Yeni bir özelliğin rengini ayarlar.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[in] Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="setcolumnsnumber"></a>  CMFCPropertyGridColorProperty::SetColumnsNumber

Geçerli renk özellik kılavuzunda sütun sayısını belirtir.

```
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>Parametreler

*nColumnsNumber*<br/>
[in] Tercih edilen renk özellik kılavuzunda sütun sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem değerini ayarlar `m_nColumnsNumber` veri üyesi korumalı.

##  <a name="setoriginalvalue"></a>  CMFCPropertyGridColorProperty::SetOriginalValue

Özgün düzenlenebilir bir özelliğin değerini ayarlar.

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>Parametreler

*varValue*<br/>
[in] Bir değer.

### <a name="remarks"></a>Açıklamalar

Kullanım [CMFCPropertyGridProperty::ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) düzenlenmiş bir özelliğin özgün değeri sıfırlamak için yöntemi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl Sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty Sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
