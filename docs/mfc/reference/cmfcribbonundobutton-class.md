---
title: CMFCRibbonUndoButton Sınıfı
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
ms.openlocfilehash: 15cf93d39057f0e235779d47cf24d920d80a807d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753504"
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton Sınıfı

Sınıf, `CMFCRibbonUndoButton` en son kullanıcı komutlarını içeren bir açılır liste düğmesi uygular. Kullanıcılar, açılır listeden en son komutlardan birini veya birkaçını yeniden yapmak veya geri almak için seçebilir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Belirttiğiniz komut `CMFCRibbonUndoButton` kimliğini, metin etiketini ve ana nesnenin resim listesindeki görüntüleri kullanarak yeni bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Eylemler listesine yeni bir eylem ekler.|
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Açılan liste olan eylem listesini temizler.|
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Açılan listede n için seçilen kullanıcının seçtiği öğe sayısını belirler.|
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Nesnenin menü bulunup içermediğini gösterir.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CMFCRibbonUndoButton` açılır listeyi temsil etmek için bir yığın kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCRibbonUndoButton` nasıl oluşturup eylem listesine yeni bir eylem ekleyeceğini gösterir. Bu kod parçacığı [Şerit Gadget'lar örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGaleri](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonundobutton.h

## <a name="cmfcribbonundobuttonaddundoaction"></a><a name="addundoaction"></a>CMFCRibbonUndoButton::AddUndoAction

Eylemler listesine yeni bir eylem ekler.

```cpp
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Açılan listede görüntülenecek eylem etiketi.

## <a name="cmfcribbonundobuttoncleanupundolist"></a><a name="cleanupundolist"></a>CMFCRibbonUndoButton::CleanUpUndoList

Açılan liste olan eylem listesini temizler.

```cpp
void CleanUpUndoList();
```

## <a name="cmfcribbonundobuttoncmfcribbonundobutton"></a><a name="cmfcribbonundobutton"></a>CMFCRibbonUndoButton::CMFCRibbonUndoButton

Belirttiğiniz komut `CMFCRibbonUndoButton` kimliğini, metin etiketini ve ana nesnenin resim listesindeki görüntüleri kullanarak yeni bir nesne oluşturur.

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

*Nıd*<br/>
[içinde] Komut tanımlayıcısını belirtir.

*lpszMetin*<br/>
[içinde] Düğmenin metin etiketini belirtir.

*nSmallImageIndex*<br/>
[içinde] Düğmenin küçük görüntüsü için ana nesnenin görüntü listesindeki sıfır tabanlı dizin.

*nLargeImageIndex*<br/>
[içinde] Düğmenin büyük görüntüsü için ana nesnenin görüntü listesindeki sıfır tabanlı dizin.

*Hıcon*<br/>
[içinde] Düğme nin görüntüsü olarak kullanabileceğiniz bir simgenin tutamacı.

## <a name="cmfcribbonundobuttongetactionnumber"></a><a name="getactionnumber"></a>CMFCRibbonUndoButton::GetActionNumber

Açılan listede n için seçilen kullanıcının seçtiği öğe sayısını belirler.

```
int GetActionNumber() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcının seçtiği öğe sayısı.

## <a name="cmfcribbonundobuttonhasmenu"></a><a name="hasmenu"></a>CMFCRibbonUndoButton::HasMenu

Nesnenin menü bulunup içermediğini gösterir.

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery Sınıfı](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
