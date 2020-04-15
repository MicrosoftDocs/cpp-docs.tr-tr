---
title: CMFCPropertyGridFontProperty Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
ms.openlocfilehash: a1c9905d8d7f32a049496c4e164c9eaac13455d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361846"
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty Sınıfı

Sınıf, `CMFCPropertyGridFileProperty` yazı tipi seçimi iletişim kutusunu açan bir özellik listesi denetim öğesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Bir `CMFCPropertyGridFontProperty` nesne inşa eder.|
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCPropertyGridFontProperty::FormatProperty`|Özellik değerinin metin temsilini biçimlendiriyor. [(CMFCPropertyGridProperty geçersiz kılar::FormatÖzellik](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Kullanıcının yazı tipi iletişim kutusundan seçtiği yazı tipi rengini alır.|
|[CMFCPropertyGridFontProperty::GetlogFont](#getlogfont)|Kullanıcının yazı tipi iletişim kutusundan seçtiği yazı tipini alır.|
|`CMFCPropertyGridFontProperty::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|`CMFCPropertyGridFontProperty::OnClickButton`|Kullanıcı bir özellikte bulunan bir düğmeyi tıklattığında çerçeve tarafından çağrılır. [(CMFCPropertyGridProperty geçersiz kılar::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridEmlak](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertygridctrl.h

## <a name="cmfcpropertygridfontpropertycmfcpropertygridfontproperty"></a><a name="cmfcpropertygridfontproperty"></a>CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty

Bir `CMFCPropertyGridFontProperty` nesne inşa eder.

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

*strName*<br/>
[içinde] Mülkün adı.

*Eğer*<br/>
[içinde] Yazı tipinin özniteliklerini belirten mantıksal bir yazı tipi yapısı.

*dwFontDialogBayraklar*<br/>
[içinde] Özellik değeri açılır düğmesini tıklattığınızda görüntülenen yazı tipi iletişim kutusuna uygulanan stiller. Varsayılan değer, CF_EFFECTS ve CF_SCREENFONTS bitwise birleşimidir. Daha fazla bilgi için [SELECTFONT Yapısının](/windows/win32/api/commdlg/ns-commdlg-choosefontw) *Bayraklar* parametresini görün.

*lpszDescr*<br/>
[içinde] Yazı tipi özelliğinin açıklaması. Varsayılan değer NULL'dur.

*Dwdata*<br/>
[içinde] Tamsayı veya özellik ile ilişkili diğer verilere işaretçi gibi uygulamaya özgü veriler. Varsayılan değer 0’dır.

*color*<br/>
[içinde] Yazı tipinin rengi. Varsayılan değer varsayılan renktir.

### <a name="remarks"></a>Açıklamalar

Nesne, `CMFCPropertyGridFontProperty` özellik ızgara yazı tipi denetiminde bir yazı tipi özelliğini temsil eder.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCPropertyGridFontProperty` nasıl inşa edilebildiğini göstermektedir. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

## <a name="cmfcpropertygridfontpropertygetcolor"></a><a name="getcolor"></a>CMFCPropertyGridFontProperty::GetColor

Kullanıcının yazı tipi iletişim kutusundan seçtiği yazı tipi rengini alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipi rengini temsil eden bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpropertygridfontpropertygetlogfont"></a><a name="getlogfont"></a>CMFCPropertyGridFontProperty::GetlogFont

Kullanıcının yazı tipi iletişim kutusundan seçtiği yazı tipini alır.

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazı tipini açıklayan [logfont](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısına işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl Sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty Sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
