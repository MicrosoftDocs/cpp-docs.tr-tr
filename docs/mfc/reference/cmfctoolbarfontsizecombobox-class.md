---
title: CMFCToolBarFontSizeComboBox sınıfı
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
ms.openlocfilehash: a1dd85ed7bf80f5307bf0bd07ef5ef74875c8562
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258950"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox sınıfı

Bir yazı tipi boyutu seçmesini sağlayan bir birleşik giriş kutusu denetimi içeren bir araç çubuğu düğmesi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Oluşturur bir `CMFCToolBarFontSizeComboBox` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Seçili yazı tipi boyutunu twip cinsinden döndürür.|
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Tüm desteklenen yazı tipi boyutlarını belirtilen bir yazı tipi birleşik giriş kutusu liste doldurur.|
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Yazı tipi boyutunu twip cinsinden ayarlar.|

## <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz bir `CMFCToolBarFontSizeComboBox` nesnesi ile birlikte bir [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md) yazı tipi ve yazı tipi boyutu seçmesini etkinleştirmek için nesne.

Bir yazı tipi birleşik giriş kutusu düğmesi eklediğiniz bir araç çubuğuna bir yazı tipi boyutu birleşik giriş kutusu düğmesi ekleyebilirsiniz. Daha fazla bilgi için [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

Kullanıcı, yeni bir yazı tipi seçtiğinde bir `CMFCToolBarFontComboBox` nesne doldurabilirsiniz yazı tipi boyutu birleşik giriş kutusu, yazı tipi için desteklenen boyutları kullanarak [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) yöntemi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCToolBarFontSizeComboBox` yapılandırmak için sınıf bir `CMFCToolBarFontSizeComboBox` nesne. Örneğin, metin kutusundan twip cinsinden yazı tipi boyutunu almak, tüm geçerli verilen yazı tipi boyutlarını ile yazı tipi boyutu birleşik giriş kutusu doldurun ve yazı tipi boyutunu twip cinsinden belirtin gösterilmektedir. Bu kod parçacığı parçasıdır [Word paneli örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtoolbarfontcombobox.h

##  <a name="cmfctoolbarfontsizecombobox"></a>  CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox

Oluşturur bir `CMFCToolBarFontSizeComboBox` nesne.

```
CMFCToolBarFontSizeComboBox();
```

##  <a name="gettwipsize"></a>  CMFCToolBarFontSizeComboBox::GetTwipSize

Bir yazı tipi boyutu açılan kutunun metin kutusundan twip cinsinden yazı tipi boyutunu alır.

```
int GetTwipSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri pozitif ise twip yazı tipi boyutu var. Açılan kutunun metin kutusu boşsa, -1'dir. Bir hata oluşursa, -2 ' dir.

##  <a name="rebuildfontsizes"></a>  CMFCToolBarFontSizeComboBox::RebuildFontSizes

Bir yazı tipi boyutu birleşik giriş kutusu, tüm geçerli verilen yazı tipi boyutlarını ile doldurur.

```
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>Parametreler

*strFontName*<br/>
[in] Bir yazı tipi adı belirtir.

### <a name="remarks"></a>Açıklamalar

Seçimi bir yazı tipi birleşik giriş kutusunda arasında bir yazı tipi boyutu birleşik giriş kutusu gibi eşitlemek istediğiniz zaman bu işlevi çağırın. bir [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

##  <a name="settwipsize"></a>  CMFCToolBarFontSizeComboBox::SetTwipSize

Yuvarlar belirtilen değerle birleşik giriş kutusunda seçili boyutu (twip cinsinden) en yakın boyutu noktaları ve ardından ayarlar için boyutu.

```
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
[in] Ayarlanacak yazı tipi boyutu (twip) belirtir.

### <a name="remarks"></a>Açıklamalar

Çağırarak, daha sonra bir önceki geçerli yazı tipi boyutunu alabilirsiniz [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) yöntemi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton Sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo Sınıfı](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: Araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
