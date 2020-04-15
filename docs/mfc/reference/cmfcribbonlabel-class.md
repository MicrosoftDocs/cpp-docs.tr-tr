---
title: CMFCRibbonLabel Sınıfı
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
ms.openlocfilehash: cd30e374441661368d3ea7abf5177424f8dffb3c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375131"
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel Sınıfı

Şerit için tıklanabilir olmayan bir metin etiketi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonLabel::CMFCRibbonEtiket](#cmfcribbonlabel)|Belirtilen metin dizesiyle `CMFCRibbonLabel` bir nesne yi inşa eder ve başharfe atar.|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CMFCRibbonLabel::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Geçerli şerit etiket öğesiiçin erişilebilirlik verilerini belirler. [(CMFCRibbonButton geçersiz kılar::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

### <a name="remarks"></a>Açıklamalar

Bir şerit etiketi oluşturduktan sonra CMFCRibbonPanel'i arayarak bir panele [ekleyin::Ekle.](../../mfc/reference/cmfcribbonpanel-class.md#add)

Hızlı Erişim Araç Çubuğu'na şerit etiketi ekleyemezsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEtiket](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonLabel.h

## <a name="cmfcribbonlabelcmfcribbonlabel"></a><a name="cmfcribbonlabel"></a>CMFCRibbonLabel::CMFCRibbonEtiket

Belirtilen metin dizesini görüntüleyen bir [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) nesnesi oluşturuyor ve baş harflerini algılar.

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
[içinde] Etikette görünecek metin.

*bIsMultiLine*<br/>
[içinde] Etiketin çok satırlı bir etiket olduğunu belirtmek için TRUE; aksi takdirde, YANLIŞ.

## <a name="cmfcribbonlabelsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonLabel::SetACCData

Geçerli şerit etiket öğesiiçin erişilebilirlik verilerini belirler.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
[içinde] Geçerli şerit etiketinin ana penceresini temsil eder.

*Veri*<br/>
[çıkış] Geçerli şerit `CAccessibilityData` etiketinin erişilebilirlik verileriyle doldurulan tür degisi.

### <a name="return-value"></a>Dönüş Değeri

*Veri* parametresi geçerli şerit etiketinin erişilebilirlik verileriyle başarıyla doldurulduysa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
