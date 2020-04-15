---
title: CMFCToolBarFontSizeComboBox Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
ms.openlocfilehash: 09811b14ed805b1965015a32a25c0b67c947ff4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358302"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox Sınıfı

Kullanıcının yazı tipi boyutunu seçmesini sağlayan açılan kutu denetimi içeren araç çubuğu düğmesi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Bir `CMFCToolBarFontSizeComboBox` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Seçili yazı tipi boyutunu twip'lerde döndürür.|
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Açılan kutu listesini, belirli bir yazı tipi için desteklenen tüm yazı tipi boyutlarıyla doldurur.|
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Yazı tipi boyutunu twip olarak ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir `CMFCToolBarFontSizeComboBox` kullanıcının yazı tipi ve yazı tipi boyutunu seçmesini sağlamak için [cmfcToolBarFontComboBox Sınıf](../../mfc/reference/cmfctoolbarfontcombobox-class.md) nesnesi ile birlikte bir nesne kullanabilirsiniz.

Yazı tipi açılan kutu düğmesi eklediğinizde, bir araç çubuğuna yazı tipi boyutu açılan kutu düğmesi ekleyebilirsiniz. Daha fazla bilgi için [CMFCToolBarFontComboBox Class'a](../../mfc/reference/cmfctoolbarfontcombobox-class.md)bakın.

Kullanıcı bir nesnede yeni bir `CMFCToolBarFontComboBox` yazı tipi seçtiğinde, [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) yöntemini kullanarak yazı tipi boyutu açılan kutusunu bu yazı tipi için desteklenen boyutlarla doldurabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCToolBarFontSizeComboBox` `CMFCToolBarFontSizeComboBox` nesneyi yapılandırmak için sınıfta çeşitli yöntemlerin nasıl kullanılacağını gösterir. Örnek, metin kutusundan twip'lerde yazı tipi boyutununasıl alınca, yazı tipi boyutu açılan kutusunu verilen yazı tipinin tüm geçerli boyutlarıyla nasıl doldurup twip'lerde yazı tipi boyutunu nasıl belirtileceğini göstermektedir. Bu kod parçacığı Word Pad [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[Cmfctoolbarcomboboxbutton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarfontcombobox.h

## <a name="cmfctoolbarfontsizecomboboxcmfctoolbarfontsizecombobox"></a><a name="cmfctoolbarfontsizecombobox"></a>CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox

Bir `CMFCToolBarFontSizeComboBox` nesne inşa eder.

```
CMFCToolBarFontSizeComboBox();
```

## <a name="cmfctoolbarfontsizecomboboxgettwipsize"></a><a name="gettwipsize"></a>CMFCToolBarFontSizeComboBox::GetTwipSize

Yazı tipi boyutu açılan kutusunun metin kutusundan twip'lerde yazı tipi boyutunu alır.

```
int GetTwipSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

İade değeri pozitifse, twip'deki yazı tipi boyutudur. Açılan kutunun metin kutusu boşsa -1'dir. Bir hata oluşursa -2'dir.

## <a name="cmfctoolbarfontsizecomboboxrebuildfontsizes"></a><a name="rebuildfontsizes"></a>CMFCToolBarFontSizeComboBox::RebuildFontSizes

Bir yazı tipi boyutu açılan kutusunu, verilen yazı tipinin tüm geçerli boyutlarıyla doldurur.

```
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>Parametreler

*strFontName*<br/>
[içinde] Bir yazı tipi adı belirtir.

### <a name="remarks"></a>Açıklamalar

Bir yazı tipi açılan kutusunda seçim ve [CMFCToolBarFontComboBox Sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)gibi yazı tipi boyutu açılan kutusu arasında eşitlemek istediğinizde bu işlevi arayın.

## <a name="cmfctoolbarfontsizecomboboxsettwipsize"></a><a name="settwipsize"></a>CMFCToolBarFontSizeComboBox::SetTwipSize

Belirtilen boyutu (twip cinsinden) noktalardaki en yakın boyuta yuvarlar ve ardından açılan kutuda seçili boyutu bu değere ayarlar.

```
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
[içinde] Ayarlamak için yazı tipi boyutunu (twip olarak) belirtir.

### <a name="remarks"></a>Açıklamalar

Önceki geçerli yazı tipi boyutunu daha sonra [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) yöntemini arayarak alabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton Sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo Sınıfı](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
