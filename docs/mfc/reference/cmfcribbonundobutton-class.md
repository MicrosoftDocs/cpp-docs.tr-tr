---
description: 'Daha fazla bilgi edinin: CMFCRibbonUndoButton sınıfı'
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
ms.openlocfilehash: 8bfc02b61160a5f11a6913736c5dc784c4d00ce4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264940"
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton sınıfı

`CMFCRibbonUndoButton`Sınıfı, en son kullanıcı komutlarını içeren bir açılır liste düğmesi uygular. Kullanıcılar, açılan listeden bir veya daha fazla en son komutlardan birini seçerek veya geri alabilir.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonUndoButton:: CMFCRibbonUndoButton](#cmfcribbonundobutton)|`CMFCRibbonUndoButton`Belirttiğiniz komut kimliğini, metin etiketini ve görüntüleri üst nesnenin görüntü listesinden kullanarak yeni bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonUndoButton:: AddUndoAction](#addundoaction)|Eylemler listesine yeni bir eylem ekler.|
|[CMFCRibbonUndoButton:: CleanUpUndoList](#cleanupundolist)|Açılır liste olan eylem listesini temizler.|
|[CMFCRibbonUndoButton:: GetActionNumber](#getactionnumber)|Bir kullanıcının açılan listeden seçtiği öğelerin sayısını belirler.|
|[CMFCRibbonUndoButton:: HasMenu](#hasmenu)|Nesnenin bir menü içerip içermediğini gösterir.|

## <a name="remarks"></a>Açıklamalar

`CMFCRibbonUndoButton`Sınıfı, açılan listeyi temsil eden bir yığın kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCRibbonUndoButton` ve eylemler listesine yeni bir eylem ekler. Bu kod parçacığı, [Şerit araçları örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)

[Cmfcribbongalerisi](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonundobutton. h

## <a name="cmfcribbonundobuttonaddundoaction"></a><a name="addundoaction"></a> CMFCRibbonUndoButton:: AddUndoAction

Eylemler listesine yeni bir eylem ekler.

```cpp
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Açılan listede görüntülenecek eylem etiketi.

## <a name="cmfcribbonundobuttoncleanupundolist"></a><a name="cleanupundolist"></a> CMFCRibbonUndoButton:: CleanUpUndoList

Açılır liste olan eylem listesini temizler.

```cpp
void CleanUpUndoList();
```

## <a name="cmfcribbonundobuttoncmfcribbonundobutton"></a><a name="cmfcribbonundobutton"></a> CMFCRibbonUndoButton:: CMFCRibbonUndoButton

`CMFCRibbonUndoButton`Belirttiğiniz komut kimliğini, metin etiketini ve görüntüleri üst nesnenin görüntü listesinden kullanarak yeni bir nesne oluşturur.

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

*NID*<br/>
'ndaki Komut tanımlayıcısını belirtir.

*lpszText*<br/>
'ndaki Düğmenin metin etiketini belirtir.

*Nsmallımageındex*<br/>
'ndaki Düğmenin küçük görüntüsü için üst nesnenin görüntü listesinde sıfır tabanlı dizin.

*Nlargeımageındex*<br/>
'ndaki Düğmenin büyük görüntüsü için üst nesnenin görüntü listesinde sıfır tabanlı dizin.

*HICON*<br/>
'ndaki Düğme görüntüsü olarak kullanabileceğiniz simgeye yönelik bir tanıtıcı.

## <a name="cmfcribbonundobuttongetactionnumber"></a><a name="getactionnumber"></a> CMFCRibbonUndoButton:: GetActionNumber

Bir kullanıcının açılan listeden seçtiği öğelerin sayısını belirler.

```
int GetActionNumber() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir kullanıcının seçtiği öğe sayısı.

## <a name="cmfcribbonundobuttonhasmenu"></a><a name="hasmenu"></a> CMFCRibbonUndoButton:: HasMenu

Nesnenin bir menü içerip içermediğini gösterir.

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery sınıfı](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
