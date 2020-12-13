---
description: 'Daha fazla bilgi edinin: CMFCToolBarFontSizeComboBox sınıfı'
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
ms.openlocfilehash: a355e62f2ef538372d70b9b2b393bc16bff2ef4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331747"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox sınıfı

Kullanıcının bir yazı tipi boyutu seçmesini sağlayan bir Birleşik giriş kutusu denetimi içeren bir araç çubuğu düğmesi.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox:: CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Bir `CMFCToolBarFontSizeComboBox` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox:: Getdallı psize](#gettwipsize)|Seçili yazı tipi boyutunu twip cinsinden döndürür.|
|[CMFCToolBarFontSizeComboBox:: Rebuildfontboyutlarda](#rebuildfontsizes)|Birleşik giriş kutusu listesini belirtilen bir yazı tipi için desteklenen tüm yazı tipi boyutlarına doldurur.|
|[CMFCToolBarFontSizeComboBox:: Settingwipsize](#settwipsize)|Yazı tipi boyutunu twip cinsinden ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir `CMFCToolBarFontSizeComboBox` kullanıcının bir yazı tipi ve yazı tipi boyutu seçmesini sağlamak için bir nesneyi [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md) nesnesiyle birlikte kullanabilirsiniz.

Bir yazı tipi kutusu açılan kutusu düğmesi eklediğiniz gibi bir araç çubuğuna yazı tipi boyutu açılan kutusu düğmesi ekleyebilirsiniz. Daha fazla bilgi için bkz. [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

Kullanıcı bir nesnede yeni bir yazı tipi seçtiğinde `CMFCToolBarFontComboBox` , [CMFCToolBarFontSizeComboBox:: rebuildfontboyutlarda](#rebuildfontsizes) yöntemini kullanarak yazı tipi boyutu açılan kutusunu bu yazı tipi için desteklenen boyutlarla doldurabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCToolBarFontSizeComboBox` bir nesneyi yapılandırmak için sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCToolBarFontSizeComboBox` . Örnek, metin kutusundan yazı tipi boyutunun twip cinsinden nasıl alınacağını, yazı tipi boyutu Birleşik giriş kutusunu belirtilen yazı tipinin tüm geçerli boyutlarıyla doldurmasını ve yazı tipi boyutunu twip cinsinden belirtmeyi gösterir. Bu kod parçacığı, [sözcük paneli örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarfontcombobox. h

## <a name="cmfctoolbarfontsizecomboboxcmfctoolbarfontsizecombobox"></a><a name="cmfctoolbarfontsizecombobox"></a> CMFCToolBarFontSizeComboBox:: CMFCToolBarFontSizeComboBox

Bir `CMFCToolBarFontSizeComboBox` nesnesi oluşturur.

```
CMFCToolBarFontSizeComboBox();
```

## <a name="cmfctoolbarfontsizecomboboxgettwipsize"></a><a name="gettwipsize"></a> CMFCToolBarFontSizeComboBox:: Getdallı psize

Yazı tipi boyutu Birleşik giriş kutusunun metin kutusundan yazı tipi boyutunu twip olarak alır.

```
int GetTwipSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri pozitif ise, yazı tipi boyutu twip cinsinden olur. Birleşik giriş kutusunun metin kutusu boş ise,-1 ' dir. Bir hata oluşursa-2 ' dir.

## <a name="cmfctoolbarfontsizecomboboxrebuildfontsizes"></a><a name="rebuildfontsizes"></a> CMFCToolBarFontSizeComboBox:: Rebuildfontboyutlarda

Yazı tipi boyutu açılan kutusunu, belirtilen yazı tipinin tüm geçerli boyutlarına göre doldurur.

```cpp
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>Parametreler

*strFontName*<br/>
'ndaki Bir yazı tipi adı belirtir.

### <a name="remarks"></a>Açıklamalar

Bir yazı tipi Birleşik giriş kutusundaki seçim ve [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)gibi bir yazı tipi boyutu açılan kutusu arasında eşitlenmek istediğinizde bu işlevi çağırın.

## <a name="cmfctoolbarfontsizecomboboxsettwipsize"></a><a name="settwipsize"></a> CMFCToolBarFontSizeComboBox:: Settingwipsize

Belirtilen boyutu (twip olarak) punto olarak en yakın boyuta yuvarlar ve sonra Birleşik giriş kutusundaki seçili boyutu bu değere ayarlar.

```cpp
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
'ndaki Ayarlanacak yazı tipi boyutunu (twip olarak) belirtir.

### <a name="remarks"></a>Açıklamalar

Önceki geçerli yazı tipi boyutunu daha sonra [CMFCToolBarFontSizeComboBox:: Getdallı psize](#gettwipsize) metodunu çağırarak elde edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo sınıfı](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
