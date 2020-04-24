---
title: CMFCRibbonButtonsGrup Sınıfı
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
ms.openlocfilehash: d690e8bf306234e7b742a4c6a0917e5430d92d10
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754109"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGrup Sınıfı

Sınıf, `CMFCRibbonButtonsGroup` bir grup halinde şerit düğmeleri kümesi düzenlemenizi sağlar. Gruptaki tüm düğmeler yatay olarak birbirine doğrudan bitişik ve bir kenarlık içinde çevrilidir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Bir `CMFCRibbonButtonsGroup` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::Ekle Düğmesi](#addbutton)|Gruba bir düğme ekler.|
|[CMFCRibbonButtonsGroup::Düğme Ekle](#addbuttons)|Gruba düğmelerin listesini ekler.|
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Belirtilen bir dizinte bulunan düğmeye bir işaretçi döndürür.|
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Gruptaki düğme sayısını verir.|
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Şerit grubundaki normal görüntülerin görüntü boyutunu döndürür [(CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize)'yi geçersiz kılar.)|
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Şerit öğesinin normal boyutunu verir [(CMFCRibbonBaseElement geçersiz kılar::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Nesnenin `CMFCRibbonButtonsGroup` araç çubuğu görüntüleri bulunup içermediğini bildirir.|
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Düğmenin normal, vurgulanmış veya devre dışı bırakıldığına bağlı olarak, belirtilen düğme için uygun görüntüyü çizer.|
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Nesnedeki `CMFCRibbonButtonsGroup` tüm düğmeleri kaldırır.|
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Gruba görüntü atar.|
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Nesnenin `CMFCRibbonCategory` üst öğesini ve içindeki tüm düğmeleri ayarlar [(CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).) `CMFCRibbonButtonsGroup`|

## <a name="remarks"></a>Açıklamalar

Grup [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) türetilmiştir ve tek bir varlık olarak işlenebilir. Grubu herhangi bir panelveya açılır menüde konumlandırabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCRibbonButtonsGroup` nasıl kullanılacağını göstermektedir. Örnek, bir `CMFCRibbonButtonsGroup` nesnenin nasıl oluşturulabildiğini, şerit düğmeleri grubuna görüntüleri nasıl atayının ve şerit düğmeleri grubuna nasıl bir düğme ekleyeceğini gösterir. Bu kod snippet [Çekme İstemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonbuttonsgroup.h

## <a name="cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a>CMFCRibbonButtonsGroup::Ekle Düğmesi

Gruba bir düğme ekler.

```cpp
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Parametreler

*pDüğme*<br/>
[içinde] Eklemek için bir düğmeye işaretçi.

## <a name="cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a>CMFCRibbonButtonsGroup::Düğme Ekle

Gruba düğmelerin listesini ekler.

```cpp
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>Parametreler

*lstDüğmeler*<br/>
[içinde] Eklemek istediğiniz düğmelere işaretçilerlistesi.

## <a name="cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a>CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup

Bir `CMFCRibbonButtonsGroup` nesne inşa eder.

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Parametreler

*pDüğme*<br/>
[içinde] Yeni oluşturulan `CMFCRibbonButtonsGroup` nesneye eklemek için bir düğme belirtir.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a>CMFCRibbonButtonsGroup::GetButton

Belirtilen bir dizinte bulunan düğmeye bir işaretçi döndürür.

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>Parametreler

*Ⅰ*<br/>
[içinde] Dönmek için bir düğmenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde bulunan düğmeye işaretçi. Belirtilen dizin kapsama alanı dışındaysa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a>CMFCRibbonButtonsGroup::GetCount

Gruptaki düğme sayısını verir.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gruptaki düğme sayısı.

## <a name="cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a>CMFCRibbonButtonsGroup::GetImageSize

Korumalı `CMFCToolBarImages` üyenin `m_Images`kaynak görüntü boyutunu alır.

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsa araç çubuğu görüntülerinin kaynak görüntü boyutunu veya `CSize` yoksa sıfır görüntüsünü verir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonButtonsGroup::GetRegularSize

Şerit grubu öğesinin mümkün olan en yüksek boyutunu alır.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Şerit grubunun aygıt bağlamını işaretçi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a>CMFCRibbonButtonsGroup::HasImages

Nesnenin `CMFCRibbonButtonsGroup` araç çubuğu görüntüleri bulunup içermediğini bildirir.

```
BOOL HasImages() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korunan `CMFCToolBarImages` üye `m_Images` herhangi bir görüntü içeriyorsa TRUE veya false içeriyorsa TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a>CMFCRibbonButtonsGroup::OnDrawImage

Düğmenin normal, vurgulanmış veya devre dışı bırakıldığına bağlı olarak, belirtilen düğme için uygun görüntüyü çizer.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Nesnenin aygıt bağlamına `CMFCRibbonButtonsGroup` işaretçi.

*rectImage*<br/>
[içinde] Görüntüyü çizecek dikdörtgen.

*pDüğme*<br/>
[içinde] Görüntüyü çizmek için düğme.

*nImageIndex*<br/>
[içinde] Düğmeye çizecek görüntü dizini (normal, vurgulanmış veya devre dışı bırakılan düğmeler için üç görüntü dizisinden birinde).

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a>CMFCRibbonButtonsGroup::RemoveAll

Nesnedeki `CMFCRibbonButtonsGroup` tüm düğmeleri kaldırır.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a>CMFCRibbonButtonsGroup::SetImages

Görüntüleri şerit düğmeleri grubuna atar.

```cpp
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>Parametreler

*pImages*<br/>
[içinde] Normal görüntüler.

*pHotImages*<br/>
[içinde] Sıcak görüntüler.

*pDisabledImages*<br/>
[içinde] Devre dışı bırakılmış görüntüler.

### <a name="remarks"></a>Açıklamalar

Gruba `SetImages` düğme eklemeden önce arayın. Görüntü sayısı, gruba eklenecek düğme sayısına daha büyük veya eşit olmalıdır.

> [!NOTE]
> Sıcak görüntüler, kullanıcı düğmenin üzerinde gezinirken görüntülenen görüntülerdir. Devre dışı bırakılan görüntüler, düğme devre dışı bırakıldığında görüntülenen görüntülerdir.

## <a name="cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a>CMFCRibbonButtonsGroup::SetParentCategory

`CMFCRibbonButtonsGroup` Nesnenin üst `CMFCRibbonCategory` öğesini ve içindeki tüm düğmeleri ayarlar.

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>Parametreler

*pKategori*<br/>
[içinde] Ayarlamak için üst kategoriişaretçisi (şerit denetimlerinde sekmeli gruplara kategoriler denir).

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
