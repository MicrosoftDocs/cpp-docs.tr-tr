---
description: 'Daha fazla bilgi edinin: CMFCPropertyGridFileProperty sınıfı'
title: CMFCPropertyGridFileProperty sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: c18345876eb49ee2e71d3eb02776212918e5c2c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289952"
---
# <a name="cmfcpropertygridfileproperty-class"></a>CMFCPropertyGridFileProperty sınıfı

`CMFCPropertyGridFileProperty`Sınıfı, bir dosya seçimi iletişim kutusunu açan bir özellik listesi denetim öğesini destekler.

## <a name="syntax"></a>Syntax

```
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridFileProperty:: CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|Bir `CMFCPropertyGridFileProperty` nesnesi oluşturur.|
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCPropertyGridFileProperty::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|`CMFCPropertyGridFileProperty::OnClickButton`|( [CMFCPropertyGridProperty:: OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)geçersiz kılar.)|

### <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertygridctrl. h

## <a name="cmfcpropertygridfilepropertycmfcpropertygridfileproperty"></a><a name="cmfcpropertygridfileproperty"></a> CMFCPropertyGridFileProperty:: CMFCPropertyGridFileProperty

Bir `CMFCPropertyGridFileProperty` nesnesi oluşturur.

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

*strName*<br/>
'ndaki Özellik adı.

*bOpenFileDialog*<br/>
'ndaki **Dosya Aç** iletişim kutusunu açmak için true. **Dosya Kaydet** iletişim kutusunu açmak için false.

*strFileName*<br/>
'ndaki İlk dosya adı.

*lpszDefExt*<br/>
'ndaki Bir veya daha fazla dosya adı uzantısının dizesi. Varsayılan değer NULL.

*dwFlags*<br/>
'ndaki İletişim kutusu bayrakları. Varsayılan değer, OFN_HIDEREADONLY ve OFN_OVERWRITEPROMPT bit düzeyinde birleşimidir (veya).

*lpszFilter*<br/>
'ndaki Bir veya daha fazla dosya filtresi dizesi. Varsayılan değer NULL.

*lpszDescr*<br/>
'ndaki Özellik öğesi açıklaması. Varsayılan değer NULL.

*dwData*<br/>
'ndaki Özellik öğesiyle ilişkili uygulamaya özel veriler. Örneğin, 32 bitlik bir tamsayı veya diğer verilere yönelik bir işaretçi. Varsayılan değer 0’dır.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Kullanılabilir bayrakların tam listesi için bkz. [OpenFileName yapısı](/windows/win32/api/commdlg/ns-commdlg-openfilenamew).

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının yapıcısını kullanarak bir nesnesinin nasıl oluşturulacağını gösterir `CMFCPropertyGridFileProperty` . Bu örnek, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
