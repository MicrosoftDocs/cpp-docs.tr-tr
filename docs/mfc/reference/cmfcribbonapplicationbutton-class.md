---
title: CMFCRibbonApplicationButton Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
ms.openlocfilehash: b28d075c5fcc4313e1a62ae731b3fad8ef4d8a12
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749936"
---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton Sınıfı

Uygulama penceresinin sol üst köşesinde bulunan özel bir düğme uygular. Tıklatıldığında, düğme genellikle **Aç**, **Kaydet**ve **Çık**gibi yaygın **Dosya** komutlarını içeren bir menü açar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|Bir `CMFCRibbonApplicationButton` nesne yi inşa eder ve başharfe ait hale raz.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CMFCRibbonApplicationButton::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCRibbonApplicationButton::SetImage](#setimage)|Şerit uygulama düğmesine bir resim atar.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCRibbonApplicationButton` nasıl kullanılacağını göstermektedir. Örnek, bir resmin uygulama düğmesine nasıl atayılabildiğini ve araç ucunu nasıl ayarlayacağını gösterir. Bu kod snippet [Çekme İstemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonBar.h

## <a name="cmfcribbonapplicationbuttoncmfcribbonapplicationbutton"></a><a name="cmfcribbonapplicationbutton"></a>CMFCRibbonApplicationButton::CMFCRibbonApplicationButton

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) nesnesi kurar ve başlayır.

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>Parametreler

*uiBmpResID*<br/>
Uygulama düğmesinde görüntülenecek görüntünün kaynak kimliği.

*hBmp*<br/>
Uygulama düğmesinde görüntülenecek bit eşlenin tutamacı.

### <a name="remarks"></a>Açıklamalar

Şerit uygulama düğmesi, uygulama penceresinin sol üst köşesinde bulunan özel bir düğmedir. Bir kullanıcı bu düğmeyi tıklattığında, uygulama genellikle **Aç,** **Kaydet**ve **Çık**gibi yaygın **Dosya** komutları içeren bir menü açar.

## <a name="cmfcribbonapplicationbuttonsetimage"></a><a name="setimage"></a>CMFCRibbonApplicationButton::SetImage

Uygulama düğmesine bir resim atar.

```cpp
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>Parametreler

*uiBmpResID*<br/>
[içinde] Uygulama düğmesinde görüntülenecek görüntünün kaynak kimliği.

*hBmp*<br/>
[içinde] Uygulama düğmesinde görüntülenecek bit eşlenin tutamacı.

### <a name="remarks"></a>Açıklamalar

Düğmeyi oluşturduktan sonra şerit uygulama düğmesine yeni bir resim atamak için bu yöntemi kullanın. Uygulama düğmesi, uygulama penceresinin sol üst köşesinde yer alır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
