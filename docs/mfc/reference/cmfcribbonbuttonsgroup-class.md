---
description: 'Daha fazla bilgi edinin: CMFCRibbonButtonsGroup Class'
title: CMFCRibbonButtonsGroup sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
ms.openlocfilehash: 0b86ce6ff21bd36daaac9d68ce511ae395141170
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293839"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup sınıfı

Sınıfı, bir `CMFCRibbonButtonsGroup` Grup içinde bir şerit düğme kümesini düzenlemenizi sağlar. Gruptaki tüm düğmeler, yatay olarak birbirlerine ve kenarlıkta çevreye doğrudan bitişik.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Bir `CMFCRibbonButtonsGroup` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonButtonsGroup:: AddButton](#addbutton)|Bir gruba düğme ekler.|
|[CMFCRibbonButtonsGroup:: AddButtons](#addbuttons)|Bir gruba düğme listesi ekler.|
|[CMFCRibbonButtonsGroup:: GetButton](#getbutton)|Belirtilen dizinde bulunan düğmeye bir işaretçi döndürür.|
|[CMFCRibbonButtonsGroup:: GetCount](#getcount)|Gruptaki düğmelerin sayısını döndürür.|
|[CMFCRibbonButtonsGroup:: Getıgesize](#getimagesize)|Şerit grubundaki normal görüntülerin görüntü boyutunu döndürür ( [CMFCRibbonBaseElement:: Getıgesize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize)geçersiz kılar.)|
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Şerit öğesinin normal boyutunu döndürür ( [CMFCRibbonBaseElement:: GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonButtonsGroup:: Hasımages](#hasimages)|`CMFCRibbonButtonsGroup`Nesnenin araç çubuğu görüntülerini içerip içermediğini bildirir.|
|[CMFCRibbonButtonsGroup:: OnDrawImage](#ondrawimage)|Düğmenin normal, vurgulanmış veya devre dışı olmasına bağlı olarak, belirtilen düğme için uygun görüntüyü çizer.|
|[CMFCRibbonButtonsGroup:: RemoveAll](#removeall)|Nesneden tüm düğmeleri kaldırır `CMFCRibbonButtonsGroup` .|
|[CMFCRibbonButtonsGroup:: Setıges](#setimages)|Görüntüleri gruba atar.|
|[CMFCRibbonButtonsGroup:: SetParentCategory](#setparentcategory)|`CMFCRibbonCategory` `CMFCRibbonButtonsGroup` Nesnenin üst öğesini ve içindeki tüm düğmeleri ayarlar ( [CMFCRibbonBaseElement:: SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory)geçersiz kılar)|

## <a name="remarks"></a>Açıklamalar

Grup [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) öğesinden türetilir ve tek bir varlık olarak yönetilebilir. Grubu herhangi bir panele veya açılır menüye yerleştirebilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCRibbonButtonsGroup` . Örnek, bir nesnenin nasıl oluşturulduğunu `CMFCRibbonButtonsGroup` , şerit düğme grubuna görüntü atamayı ve Şerit düğmesi grubuna düğme eklemeyi gösterir. Bu kod parçacığı, [Çizim istemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonbuttonsgroup. h

## <a name="cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a> CMFCRibbonButtonsGroup:: AddButton

Bir gruba düğme ekler.

```cpp
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Parametreler

*pButton*<br/>
'ndaki Eklenecek düğmeye yönelik bir işaretçi.

## <a name="cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a> CMFCRibbonButtonsGroup:: AddButtons

Bir gruba düğme listesi ekler.

```cpp
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>Parametreler

*lstButtons*<br/>
'ndaki Eklemek istediğiniz düğmelere yönelik işaretçilerin bir listesi.

## <a name="cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a> CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup

Bir `CMFCRibbonButtonsGroup` nesnesi oluşturur.

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Parametreler

*pButton*<br/>
'ndaki Yeni oluşturulan nesneye eklenecek bir düğmeyi belirtir `CMFCRibbonButtonsGroup` .

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a> CMFCRibbonButtonsGroup:: GetButton

Belirtilen dizinde bulunan düğmeye bir işaretçi döndürür.

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>Parametreler

*i*<br/>
'ndaki Döndürülecek bir düğmenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde bulunan düğmeye yönelik bir işaretçi. Belirtilen dizin Aralık dışında olduğunda NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a> CMFCRibbonButtonsGroup:: GetCount

Gruptaki düğmelerin sayısını döndürür.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gruptaki düğmelerin sayısı.

## <a name="cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a> CMFCRibbonButtonsGroup:: Getıgesize

Korumalı üyenin kaynak görüntü boyutunu alır `CMFCToolBarImages` `m_Images` .

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsa, araç çubuğu görüntülerinin kaynak resim boyutunu veya `CSize` değilse sıfır değerini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonButtonsGroup::GetRegularSize

Şerit grubu öğesinin olası en büyük boyutunu alır.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Şerit grubunun cihaz bağlamına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a> CMFCRibbonButtonsGroup:: Hasımages

`CMFCRibbonButtonsGroup`Nesnenin araç çubuğu görüntülerini içerip içermediğini bildirir.

```
BOOL HasImages() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korunan `CMFCToolBarImages` üye `m_Images` herhangi bir görüntü içeriyorsa true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a> CMFCRibbonButtonsGroup:: OnDrawImage

Düğmenin normal, vurgulanmış veya devre dışı olmasına bağlı olarak, belirtilen düğme için uygun görüntüyü çizer.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Nesnenin cihaz bağlamına yönelik işaretçi `CMFCRibbonButtonsGroup` .

*rectImage*<br/>
'ndaki Görüntünün çizileceği dikdörtgen.

*pButton*<br/>
'ndaki Resmin çizildiği düğme.

*Nımageındex*<br/>
'ndaki Düğmeye çizilecek görüntünün dizini (normal, vurgulanan veya devre dışı düğmeler için üç görüntü dizilerindeki bir).

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a> CMFCRibbonButtonsGroup:: RemoveAll

Nesneden tüm düğmeleri kaldırır `CMFCRibbonButtonsGroup` .

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a> CMFCRibbonButtonsGroup:: Setıges

Şerit düğme grubuna görüntüler atar.

```cpp
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>Parametreler

*Pımages*<br/>
'ndaki Normal görüntüler.

*Fotıges*<br/>
'ndaki Sık kullanılan görüntüler.

*pDisabledImages*<br/>
'ndaki Devre dışı görüntüler.

### <a name="remarks"></a>Açıklamalar

`SetImages`Bir gruba düğme eklemeden önce çağırın. Görüntü sayısı, gruba eklenecek düğme sayısına eşit veya daha büyük olmalıdır.

> [!NOTE]
> Etkin görüntüler, Kullanıcı düğmenin üzerine geldiğinde görüntülenen görüntülerdir. Devre dışı bırakılmış görüntüler, düğme devre dışı bırakıldığında görüntülenen görüntülerdir.

## <a name="cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a> CMFCRibbonButtonsGroup:: SetParentCategory

Nesnenin üst öğesini `CMFCRibbonCategory` `CMFCRibbonButtonsGroup` ve içindeki tüm düğmeleri ayarlar.

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>Parametreler

*pCategory*<br/>
'ndaki Ayarlanacak üst kategoriye yönelik işaretçi (şerit denetimlerindeki sekmeli gruplar kategoriler olarak adlandırılır).

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
