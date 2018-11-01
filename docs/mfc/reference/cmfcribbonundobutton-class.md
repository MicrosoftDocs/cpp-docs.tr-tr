---
title: CMFCRibbonUndoButton sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
ms.openlocfilehash: 78d6b3423f19fe0cf3caf3aa0184fbe779a6c029
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512901"
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton sınıfı

`CMFCRibbonUndoButton` Sınıfı en son kullanıcı komutları içeren bir açılan liste düğmesi uygular. Kullanıcılar, bir veya daha fazla en son komutları Yinele veya geri almak için aşağı açılan listeden seçebilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Yeni bir oluşturur `CMFCRibbonUndoButton` , belirttiğiniz komut kimliği, metin etiketi ve üst nesne görüntü listesinden görüntü kullanarak bir nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Yeni bir eylem eylemleri listesine ekler.|
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Aşağı açılan liste eylem listesini temizler.|
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Aşağı açılan listeden bir kullanıcı seçili öğe sayısını belirler.|
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Nesne bir menü içerip içermediğini belirtir.|

## <a name="remarks"></a>Açıklamalar

`CMFCRibbonUndoButton` Sınıfı yanıdaki açılan listeyi temsil etmek için bir yığın kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonUndoButton` sınıfı ve Eylemler listesine yeni bir eylem ekleyin. Bu kod parçacığı parçasıdır [Şerit araçları örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxribbonundobutton.h

##  <a name="addundoaction"></a>  CMFCRibbonUndoButton::AddUndoAction

Yeni bir eylem eylemleri listesine ekler.

```
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
[in] Aşağı açılan listeden görüntülenen eylem etiketi.

##  <a name="cleanupundolist"></a>  CMFCRibbonUndoButton::CleanUpUndoList

Aşağı açılan liste eylem listesini temizler.

```
void CleanUpUndoList();
```

##  <a name="cmfcribbonundobutton"></a>  CMFCRibbonUndoButton::CMFCRibbonUndoButton

Yeni bir oluşturur `CMFCRibbonUndoButton` , belirttiğiniz komut kimliği, metin etiketi ve üst nesne görüntü listesinden görüntü kullanarak bir nesne.

```
CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex=-1,
    int nLargeImageIndex=-1);

CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
[in] Komut tanımlayıcısını belirtir.

*lpszText*<br/>
[in] Düğmenin metin etiketini belirtir.

*nSmallImageIndex*<br/>
[in] Üst nesne düğmenin küçük resmi için resim listesi içindeki sıfır tabanlı dizin.

*nLargeImageIndex*<br/>
[in] Görüntü listesi için üst nesnenin içindeki sıfır tabanlı dizin düğmenin büyük görüntünün.

*hIcon*<br/>
[in] Bir düğmenin resim olarak kullanabileceğiniz bir simge tanıtıcı.

##  <a name="getactionnumber"></a>  CMFCRibbonUndoButton::GetActionNumber

Aşağı açılan listeden bir kullanıcı seçili öğe sayısını belirler.

```
int GetActionNumber() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir kullanıcı seçili öğe sayısı.

##  <a name="hasmenu"></a>  CMFCRibbonUndoButton::HasMenu

Nesne bir menü içerip içermediğini belirtir.

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery Sınıfı](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
