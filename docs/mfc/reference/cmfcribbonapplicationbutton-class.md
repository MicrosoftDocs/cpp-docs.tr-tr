---
description: 'Daha fazla bilgi edinin: CMFCRibbonApplicationButton sınıfı'
title: CMFCRibbonApplicationButton sınıfı
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
ms.openlocfilehash: 391274c7540e7e52a19c20e17a09b25f37badcd6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289809"
---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton sınıfı

Uygulama penceresinin sol üst köşesinde bulunan özel bir düğme uygular. Tıklandığında düğme, genellikle **Open**, **Save** ve **Exit** gibi ortak **Dosya** komutlarını içeren bir menü açar.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonApplicationButton:: CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|Bir nesnesi oluşturur ve başlatır `CMFCRibbonApplicationButton` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CMFCRibbonApplicationButton::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCRibbonApplicationButton:: SetImage](#setimage)|Şerit uygulama düğmesine bir görüntü atar.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCRibbonApplicationButton` . Örnek, uygulama düğmesine nasıl bir görüntü atanacağını ve araç ipucunu nasıl ayarlayacağınızı gösterir. Bu kod parçacığı, [Çizim istemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonBar. h

## <a name="cmfcribbonapplicationbuttoncmfcribbonapplicationbutton"></a><a name="cmfcribbonapplicationbutton"></a> CMFCRibbonApplicationButton:: CMFCRibbonApplicationButton

Bir [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) nesnesi oluşturur ve başlatır.

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>Parametreler

*Uıımpresd*<br/>
Uygulama düğmesinde görüntülenecek görüntünün kaynak KIMLIĞI.

*hBmp*<br/>
Uygulama düğmesinde görüntülenecek bir bit eşlem tutamacı.

### <a name="remarks"></a>Açıklamalar

Şerit uygulaması düğmesi, uygulama penceresinin sol üst köşesinde bulunan özel bir düğmedir. Kullanıcı bu düğmeye tıkladığında, uygulama, genellikle **Aç**, **Kaydet** ve **Çıkış** gibi ortak **Dosya** komutlarını içeren bir menü açar.

## <a name="cmfcribbonapplicationbuttonsetimage"></a><a name="setimage"></a> CMFCRibbonApplicationButton:: SetImage

Uygulama düğmesine bir görüntü atar.

```cpp
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>Parametreler

*Uıımpresd*<br/>
'ndaki Uygulama düğmesinde görüntülenecek görüntünün kaynak KIMLIĞI.

*hBmp*<br/>
'ndaki Uygulama düğmesinde görüntülenecek bir bit eşlem tutamacı.

### <a name="remarks"></a>Açıklamalar

Düğmeyi oluşturduktan sonra şerit uygulaması düğmesine yeni bir görüntü atamak için bu yöntemi kullanın. Uygulama düğmesi uygulama penceresinin sol üst köşesinde bulunur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
