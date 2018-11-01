---
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
ms.openlocfilehash: ae185a81267dce68cda6bc27c5e327b3335a1018
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436405"
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel sınıfı

Bir Şerit için tıklanmayan bir metin etiketi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|Oluşturur ve başlatır bir `CMFCRibbonLabel` nesnesi ile belirtilen metin dizesi.|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|`CMFCRibbonLabel::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Geçerli Şerit label öğesinin erişilebilirlik verileri belirler. (Geçersiz kılmaları [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

### <a name="remarks"></a>Açıklamalar

Bir Şerit etiketi oluşturduktan sonra çağırarak bir paneline Ekle [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

Hızlı Erişim Araç çubuğuna, Şerit etiket ekleyemezsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxRibbonLabel.h

##  <a name="cmfcribbonlabel"></a>  CMFCRibbonLabel::CMFCRibbonLabel

Oluşturur ve başlatır bir [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) nesnesini belirtilen metin dizesini görüntüler.

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
[in] Etikette görüntülenecek metin.

*bIsMultiLine*<br/>
[in] Etiket çok satırlı etiket olduğunu belirtmek için TRUE; Aksi takdirde FALSE.

##  <a name="setaccdata"></a>  CMFCRibbonLabel::SetACCData

Geçerli Şerit label öğesinin erişilebilirlik verileri belirler.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
[in] Geçerli Şerit etiketin üst pencereyi temsil eder.

*Veri*<br/>
[out] Bir nesne türü `CAccessibilityData` geçerli Şerit etiket erişilebilirlik verilerle doldurulur.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise *veri* parametre başarıyla geçerli Şerit etiketin erişilebilirlik verilerle doldurulmuş; Aksi takdirde FALSE.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
