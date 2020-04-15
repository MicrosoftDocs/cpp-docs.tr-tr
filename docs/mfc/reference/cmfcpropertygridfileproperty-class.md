---
title: CMFCPropertyGridFileProperty Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 0ce3321968f0c29ce3b946f6127e4435b531c422
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360575"
---
# <a name="cmfcpropertygridfileproperty-class"></a>CMFCPropertyGridFileProperty Sınıfı

Sınıf, `CMFCPropertyGridFileProperty` dosya seçimi iletişim kutusunu açan bir özellik listesi denetim öğesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|Bir `CMFCPropertyGridFileProperty` nesne inşa eder.|
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCPropertyGridFileProperty::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|`CMFCPropertyGridFileProperty::OnClickButton`|[(CMFCPropertyGridProperty geçersiz kılar::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

### <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridEmlak](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertygridctrl.h

## <a name="cmfcpropertygridfilepropertycmfcpropertygridfileproperty"></a><a name="cmfcpropertygridfileproperty"></a>CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty

Bir `CMFCPropertyGridFileProperty` nesne inşa eder.

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
[içinde] Mülk adı.

*bOpenFileDialog*<br/>
[içinde] **Dosya Aç** iletişim kutusunu açmak için DOĞRU; **Dosyayı Kaydet** iletişim kutusunu açmak için FALSE.

*strFileName*<br/>
[içinde] İlk dosya adı.

*lpszDefExt*<br/>
[içinde] Bir veya daha fazla dosya adı uzantıları dizesi. Varsayılan değer NULL'dur.

*Dwflags*<br/>
[içinde] İletişim kutusu bayrakları. Varsayılan değer, OFN_HIDEREADONLY ve OFN_OVERWRITEPROMPT bitwise birleşimidir.

*lpszFiltre*<br/>
[içinde] Bir veya daha fazla dosya filtresi dizesi. Varsayılan değer NULL'dur.

*lpszDescr*<br/>
[içinde] Özellik öğesi açıklaması. Varsayılan değer NULL'dur.

*Dwdata*<br/>
[içinde] Özellik öğesi ile ilişkili uygulamaya özgü veriler. Örneğin, 32 bit tamsayı veya diğer verilere işaretçi. Varsayılan değer 0’dır.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Kullanılabilir bayrakların tam listesi için [OPENFILENAME yapısına](/windows/win32/api/commdlg/ns-commdlg-openfilenamew)bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın oluşturucusu kullanarak bir nesnenin nasıl oluşturulacak olduğunu `CMFCPropertyGridFileProperty` gösterir. Bu örnek Visual [Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl Sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty Sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
