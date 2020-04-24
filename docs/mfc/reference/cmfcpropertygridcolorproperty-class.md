---
title: CMFCPropertyGridColorProperty Sınıfı
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
ms.openlocfilehash: 393a871a881aa4bddd786b1d4333e02d5e0dbef1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751832"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty Sınıfı

Sınıf, `CMFCPropertyGridColorProperty` renk seçimi iletişim kutusunu açan bir özellik listesi denetim öğesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Bir `CMFCPropertyGridColorProperty` nesne inşa eder.|
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Renk seçimi iletişim kutusundaki *otomatik* düğmeyi etkinleştirin. (Standart otomatik düğme **Otomatik**olarak etiketlenmiştir.)|
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Renk seçimi iletişim kutusundaki *diğer* düğmeyi etkinleştirin. (Standart diğer düğme **Daha Fazla Renk**olarak etiketlenir.)|
|`CMFCPropertyGridColorProperty::FormatProperty`|Özellik değerinin metin temsilini biçimlendiriyor. [(CMFCPropertyGridProperty geçersiz kılar::FormatÖzellik](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|Özelliğin geçerli rengini alır.|
|`CMFCPropertyGridColorProperty::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|`CMFCPropertyGridColorProperty::OnClickButton`|Kullanıcı bir özellikte bulunan bir düğmeyi tıklattığında çerçeve tarafından çağrılır. [(CMFCPropertyGridProperty geçersiz kılar::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|
|`CMFCPropertyGridColorProperty::OnDrawValue`|Özellik değerini görüntülemek için çerçeve tarafından çağrılır. [(CMFCPropertyGridProperty geçersiz kılar::OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|
|`CMFCPropertyGridColorProperty::OnEdit`|Kullanıcı bir özellik değerini değiştirmek üzereyken çerçeve tarafından çağrılır. [(CMFCPropertyGridProperty geçersiz kılar::OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Bir editable özelliğin değeri değiştiğinde çerçeve tarafından çağrılır. [(CMFCPropertyGridProperty geçersiz kılar::OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|Özellik için yeni bir renk ayarlar.|
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Geçerli renk özelliği tablosundaki sütun sayısını belirtir.|
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Editable özelliğinin özgün değerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCPropertyGridColorProperty` özellik listesi denetimine eklenebilecek bir renk özelliğini destekler. Daha fazla bilgi için [CMFCPropertyGridCtrl Sınıfına](../../mfc/reference/cmfcpropertygridctrl-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın nesnesinin `CMFCPropertyGridColorProperty` nasıl oluşturup, sınıfın çeşitli yöntemlerini kullanarak `CMFCPropertyGridColorProperty` bu nesneyi nasıl yapılandırıştırılabildiğini göstermektedir. Kod, otomatik ve diğer düğmelerin nasıl etkinleştirilen, renk ve sütun numarasının nasıl ayarlanır olduğunu açıklar. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridEmlak](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertygridctrl.h

## <a name="cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a>CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty

Bir `CMFCPropertyGridColorProperty` nesne inşa eder.

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
[içinde] Mülkün adı.

*color*<br/>
[içinde] Özelliğin renk değeri.

*pPalette*<br/>
[içinde] Renk paletine işaretçi. Varsayılan değer NULL'dur.

*lpszDescr*<br/>
[içinde] Mülk tanımı. Varsayılan değer NULL'dur.

*Dwdata*<br/>
[içinde] Tamsayı veya özellik ile ilişkili diğer verilere işaretçi gibi uygulamaya özgü veriler. Varsayılan değer 0’dır.

## <a name="cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCPropertyGridColorProperty::EnableAutomaticButton

Renk seçimi iletişim kutusundaki *otomatik* düğmeyi etkinleştirin. (Standart otomatik düğme **Otomatik**olarak etiketlenmiştir.)

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Otomatik düğmenin etiket metni.

*Colorautomatic*<br/>
[içinde] Otomatik (varsayılan) rengin RGB renk değeri.

*bEtkinleştir*<br/>
[içinde] Otomatik düğmeyi etkinleştirmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan değer TRUE'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a>CMFCPropertyGridColorProperty::EnableOtherButton

Renk seçimi iletişim kutusundaki *diğer* düğmeyi etkinleştirin. (Standart diğer düğme **Daha Fazla Renk**olarak etiketlenir.)

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Diğer düğmenin etiket metni.

*bAltColorDlg*<br/>
[içinde] `CMFCColorDialog` İletişim kutusunu görüntülemek için TRUE; Standart renk seçimi iletişim kutusunu görüntülemek için FALSE. Varsayılan değer TRUE'dur.

*bEtkinleştir*<br/>
[içinde] Diğer düğmeyi görüntülemek için TRUE; aksi takdirde, YANLIŞ.  Varsayılan değer TRUE'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a>CMFCPropertyGridColorProperty::GetColor

Özelliğin geçerli rengini alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a>CMFCPropertyGridColorProperty::SetColor

Özellik için yeni bir renk ayarlar.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCPropertyGridColorProperty::SetColumnsNumber

Geçerli renk özelliği tablosundaki sütun sayısını belirtir.

```cpp
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>Parametreler

*nColumnsNumber*<br/>
[içinde] Renk özelliği ızgarasında tercih edilen sütun sayısı.

### <a name="remarks"></a>Açıklamalar

Bu `m_nColumnsNumber` yöntem, korunan veri üyesinin değerini ayarlar.

## <a name="cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a>CMFCPropertyGridColorProperty::SetOriginalValue

Editable özelliğinin özgün değerini ayarlar.

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>Parametreler

*varValue*<br/>
[içinde] Bir değer.

### <a name="remarks"></a>Açıklamalar

Düzenlenen bir özelliğin özgün değerini sıfırlamak için [CMFCPropertyGridProperty::ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) yöntemini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl Sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty Sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
