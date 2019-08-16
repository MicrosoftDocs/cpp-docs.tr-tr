---
title: CMFCPropertyGridFontProperty sınıfı
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
ms.openlocfilehash: a3c5b806482a97d64a9ffab92877781cb8778b6b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505118"
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty sınıfı

Sınıfı `CMFCPropertyGridFileProperty` , bir yazı tipi seçimi iletişim kutusunu açan bir özellik listesi denetim öğesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridFontProperty:: CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Bir `CMFCPropertyGridFontProperty` nesnesi oluşturur.|
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCPropertyGridFontProperty::FormatProperty`|Bir özellik değerinin metin temsilini biçimlendirir. ( [CMFCPropertyGridProperty:: FormatProperty özelliğini](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty)geçersiz kılar.)|
|[CMFCPropertyGridFontProperty:: GetColor](#getcolor)|Kullanıcının yazı tipi iletişim kutusundan seçtiği yazı tipi rengini alır.|
|[CMFCPropertyGridFontProperty:: GetLogFont](#getlogfont)|Kullanıcının yazı tipi iletişim kutusundan seçtiği yazı tipini alır.|
|`CMFCPropertyGridFontProperty::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|`CMFCPropertyGridFontProperty::OnClickButton`|Kullanıcı bir özellikte bulunan bir düğmeye tıkladığında Framework tarafından çağırılır. ( [CMFCPropertyGridProperty:: OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertygridctrl. h

##  <a name="cmfcpropertygridfontproperty"></a>CMFCPropertyGridFontProperty:: CMFCPropertyGridFontProperty

Bir `CMFCPropertyGridFontProperty` nesnesi oluşturur.

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
'ndaki Özelliğin adı.

*LF*<br/>
'ndaki Yazı tipinin özniteliklerini belirten bir mantıksal yazı tipi yapısı.

*dwFontDialogFlags*<br/>
'ndaki Özellik değeri açılan düğmesine tıkladığınızda görüntülenen yazı tipi iletişim kutusuna uygulanan stiller. Varsayılan değer, CF_EFFECTS ve CF_SCREENFONTS bit düzeyinde birleşimidir (veya). Daha fazla bilgi için bkz. [CHOOSEFONT yapısının](/windows/win32/api/commdlg/ns-commdlg-choosefontw) *Flags* parametresi.

*lpszDescr*<br/>
'ndaki Yazı tipi özelliğinin açıklaması. Varsayılan değer NULL.

*dwData*<br/>
'ndaki Özelliği ile ilişkili diğer verilere yönelik bir tamsayı veya bir işaretçi gibi uygulamaya özgü veriler. Varsayılan değer 0’dır.

*Renk*<br/>
'ndaki Yazı tipinin rengi. Varsayılan değer varsayılan renktir.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCPropertyGridFontProperty` nesne, özellik Kılavuzu yazı tipi denetimindeki bir yazı tipi özelliğini temsil eder.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCPropertyGridFontProperty` sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir. Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

##  <a name="getcolor"></a>CMFCPropertyGridFontProperty:: GetColor

Kullanıcının yazı tipi iletişim kutusundan seçtiği yazı tipi rengini alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçilen yazı tipi rengini temsil eden bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="getlogfont"></a>CMFCPropertyGridFontProperty:: GetLogFont

Kullanıcının yazı tipi iletişim kutusundan seçtiği yazı tipini alır.

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>Dönüş Değeri

Seçilen yazı tipini açıklayan [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl Sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty Sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
