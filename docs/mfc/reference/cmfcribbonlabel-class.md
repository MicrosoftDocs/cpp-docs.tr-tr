---
description: 'Daha fazla bilgi edinin: CMFCRibbonLabel sınıfı'
title: CMFCRibbonLabel sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
ms.openlocfilehash: 0699e76dfe90b87cd813d18d076adf23f8512bee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321832"
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel sınıfı

Şerit için tıklatılabilir olmayan bir metin etiketi uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonLabel:: Cmfcribbonetiketi](#cmfcribbonlabel)|`CMFCRibbonLabel`Belirtilen metin dizesiyle bir nesne oluşturur ve başlatır.|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CMFCRibbonLabel::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCRibbonLabel:: SetACCData](#setaccdata)|Geçerli şerit etiketi öğesi için erişilebilirlik verilerini belirler. ( [CMFCRibbonButton:: SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata)geçersiz kılar.)|

### <a name="remarks"></a>Açıklamalar

Bir şerit etiketi oluşturduktan sonra, [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)öğesini çağırarak bir panele ekleyin.

Hızlı erişim araç çubuğuna şerit etiketi ekleyemezsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)

[Cmfcribbonetiketi](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonLabel. h

## <a name="cmfcribbonlabelcmfcribbonlabel"></a><a name="cmfcribbonlabel"></a> CMFCRibbonLabel:: Cmfcribbonetiketi

Belirtilen metin dizesini görüntüleyen bir [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) nesnesi oluşturur ve başlatır.

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
'ndaki Etikette görünecek metin.

*bIsMultiLine*<br/>
'ndaki Etiketin çok satırlı bir etiket olduğunu belirtmek için TRUE; Aksi takdirde, FALSE.

## <a name="cmfcribbonlabelsetaccdata"></a><a name="setaccdata"></a> CMFCRibbonLabel:: SetACCData

Geçerli şerit etiketi öğesi için erişilebilirlik verilerini belirler.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
'ndaki Geçerli şerit etiketinin üst penceresini temsil eder.

*data*<br/>
dışı `CAccessibilityData` Geçerli şerit etiketinin erişilebilirlik verileriyle doldurulan türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

*Veri* parametresi geçerli şerit etiketinin erişilebilirlik verileriyle başarıyla DOLDURULDıYSA true. Aksi takdirde, FALSE.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
