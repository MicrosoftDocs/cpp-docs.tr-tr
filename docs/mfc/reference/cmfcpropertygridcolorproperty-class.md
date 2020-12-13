---
description: 'Daha fazla bilgi edinin: CMFCPropertyGridColorProperty sınıfı'
title: CMFCPropertyGridColorProperty sınıfı
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
ms.openlocfilehash: 7673044a149dc1b5171167ed0854918434651dc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334705"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty sınıfı

`CMFCPropertyGridColorProperty`Sınıfı, renk seçimi iletişim kutusunu açan bir özellik listesi denetim öğesini destekler.

## <a name="syntax"></a>Syntax

```
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridColorProperty:: CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Bir `CMFCPropertyGridColorProperty` nesnesi oluşturur.|
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridColorProperty:: EnableAutomaticButton](#enableautomaticbutton)|Renk seçimi iletişim kutusunda *Otomatik* düğmesine izin vermez. (Standart otomatik düğme **Otomatik** olarak etiketlenir.)|
|[CMFCPropertyGridColorProperty:: EnableOtherButton](#enableotherbutton)|Renk seçimi iletişim kutusunda *diğer* düğmeyi da sunar. (Standart diğer düğme **daha fazla renk** etiketlidir.)|
|`CMFCPropertyGridColorProperty::FormatProperty`|Bir özellik değerinin metin temsilini biçimlendirir. ( [CMFCPropertyGridProperty:: FormatProperty özelliğini](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty)geçersiz kılar.)|
|[CMFCPropertyGridColorProperty:: GetColor](#getcolor)|Özelliğin geçerli rengini alır.|
|`CMFCPropertyGridColorProperty::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|`CMFCPropertyGridColorProperty::OnClickButton`|Kullanıcı bir özellikte bulunan bir düğmeye tıkladığında Framework tarafından çağırılır. ( [CMFCPropertyGridProperty:: OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)geçersiz kılar.)|
|`CMFCPropertyGridColorProperty::OnDrawValue`|Özellik değerini göstermek için Framework tarafından çağırılır. ( [CMFCPropertyGridProperty:: OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue)öğesini geçersiz kılar.)|
|`CMFCPropertyGridColorProperty::OnEdit`|Kullanıcı bir özellik değerini değiştirmek üzereyken Framework tarafından çağırılır. ( [CMFCPropertyGridProperty:: OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).) öğesini geçersiz kılar|
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Düzenlenebilir bir özelliğin değeri değiştiğinde Framework tarafından çağırılır. ( [CMFCPropertyGridProperty:: OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue)öğesini geçersiz kılar.)|
|[CMFCPropertyGridColorProperty:: SetColor](#setcolor)|Özelliği için yeni bir renk ayarlar.|
|[CMFCPropertyGridColorProperty:: SetColumns numarası](#setcolumnsnumber)|Geçerli renk özelliği kılavuzundaki sütun sayısını belirtir.|
|[CMFCPropertyGridColorProperty:: SetOriginalValue](#setoriginalvalue)|Düzenlenebilir bir özelliğin orijinal değerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CMFCPropertyGridColorProperty`Sınıfı, bir özellik listesi denetimine eklenebilen bir Color özelliğini destekler. Daha fazla bilgi için bkz. [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu `CMFCPropertyGridColorProperty` ve sınıfının çeşitli yöntemlerini kullanarak bu nesneyi yapılandırmayı gösterir `CMFCPropertyGridColorProperty` . Kod, otomatik ve diğer düğmelerin nasıl etkinleştirileceğini ve rengin ve sütun numarasının nasıl ayarlanacağını açıklar. Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertygridctrl. h

## <a name="cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a> CMFCPropertyGridColorProperty:: CMFCPropertyGridColorProperty

Bir `CMFCPropertyGridColorProperty` nesnesi oluşturur.

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
'ndaki Özelliğin adı.

*Renk*<br/>
'ndaki Özelliğin renk değeri.

*pPalette*<br/>
'ndaki Renk paleti işaretçisi. Varsayılan değer NULL.

*lpszDescr*<br/>
'ndaki Özellik açıklaması. Varsayılan değer NULL.

*dwData*<br/>
'ndaki Özelliği ile ilişkili diğer verilere yönelik bir tamsayı veya bir işaretçi gibi uygulamaya özgü veriler. Varsayılan değer 0’dır.

## <a name="cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCPropertyGridColorProperty:: EnableAutomaticButton

Renk seçimi iletişim kutusunda *Otomatik* düğmesine izin vermez. (Standart otomatik düğme **Otomatik** olarak etiketlenir.)

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Otomatik düğmenin etiket metni.

*colorAutomatic*<br/>
'ndaki Otomatik (varsayılan) rengin RGB renk değeri.

*bEnable*<br/>
'ndaki Otomatik düğmeyi etkinleştirmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a> CMFCPropertyGridColorProperty:: EnableOtherButton

Renk seçimi iletişim kutusunda *diğer* düğmeyi da sunar. (Standart diğer düğme **daha fazla renk** etiketlidir.)

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Diğer düğmenin etiket metni.

*bAltColorDlg*<br/>
'ndaki İletişim kutusunu göstermek için TRUE `CMFCColorDialog` ; Standart renk seçimi iletişim kutusunu göstermek için FALSE. Varsayılan değer TRUE 'dur.

*bEnable*<br/>
'ndaki Diğer düğmeyi göstermek için TRUE; Aksi takdirde, FALSE.  Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a> CMFCPropertyGridColorProperty:: GetColor

Özelliğin geçerli rengini alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a> CMFCPropertyGridColorProperty:: SetColor

Özelliği için yeni bir renk ayarlar.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a> CMFCPropertyGridColorProperty:: SetColumns numarası

Geçerli renk özelliği kılavuzundaki sütun sayısını belirtir.

```cpp
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>Parametreler

*nColumns numarası*<br/>
'ndaki Color özelliği kılavuzundaki tercih edilen sütun sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `m_nColumnsNumber` korumalı veri üyesinin değerini ayarlar.

## <a name="cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a> CMFCPropertyGridColorProperty:: SetOriginalValue

Düzenlenebilir bir özelliğin orijinal değerini ayarlar.

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>Parametreler

*varValue*<br/>
'ndaki Bir değer.

### <a name="remarks"></a>Açıklamalar

Düzenlenen bir özelliğin orijinal değerini sıfırlamak için [CMFCPropertyGridProperty:: ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) metodunu kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
