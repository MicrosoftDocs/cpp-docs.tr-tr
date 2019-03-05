---
title: CMFCPropertyGridFileProperty sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 5022063fe7eb8242f01684438e2fdeeeedc80616
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302903"
---
# <a name="cmfcpropertygridfileproperty-class"></a>CMFCPropertyGridFileProperty sınıfı

`CMFCPropertyGridFileProperty` Sınıfı, bir dosya seçimi iletişim kutusunu açan bir özellik listesi denetim öğesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|Oluşturur bir `CMFCPropertyGridFileProperty` nesne.|
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCPropertyGridFileProperty::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|`CMFCPropertyGridFileProperty::OnClickButton`|(Geçersiz kılmaları [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

### <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxpropertygridctrl.h

##  <a name="cmfcpropertygridfileproperty"></a>  CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty

Oluşturur bir `CMFCPropertyGridFileProperty` nesne.

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
[in] Özellik adı.

*bOpenFileDialog*<br/>
[in] Açık true bir **Dosya Aç** ; iletişim kutusu Açmak için yanlış bir **dosyayı Kaydet** iletişim kutusu.

*strFileName*<br/>
[in] İlk dosya adı.

*lpszDefExt*<br/>
[in] Bir veya daha fazla dosya adı uzantıları bir dize. Varsayılan değer NULL olur.

*CertOpenStore*<br/>
[in] İletişim kutusu bayraklar. Bitsel bir birleşimi (veya) OFN_HIDEREADONLY ve OFN_OVERWRITEPROMPT varsayılan değerdir.

*lpszFilter*<br/>
[in] Bir veya daha fazla dosya filtreleri dizesi. Varsayılan değer NULL olur.

*lpszDescr*<br/>
[in] Özellik öğesi açıklaması. Varsayılan değer NULL olur.

*dwData*<br/>
[in] Özellik öğesi ile ilişkilendirilen uygulamaya özgü verileri. Örneğin, 32-bit tamsayı veya diğer veri işaretçisi. Varsayılan değer 0’dır.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Kullanılabilir bayrakları tam bir listesi için bkz. [LPSTRFİLE yapısı](/windows/desktop/api/commdlg/ns-commdlg-tagofna).

### <a name="example"></a>Örnek

Aşağıdaki örnek Oluşturucusu kullanarak bir nesne oluşturma işlemini gösterir `CMFCPropertyGridFileProperty` sınıfı. Bu örneğin parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl Sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty Sınıfı](../../mfc/reference/cmfcpropertygridproperty-class.md)
