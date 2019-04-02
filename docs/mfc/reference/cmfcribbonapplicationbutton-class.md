---
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
ms.openlocfilehash: 01b6937ee597766922597fda5664c78f75be6b67
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772169"
---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton sınıfı

Uygular uygulama penceresinin sol üst köşedeki özel bir düğme bulunur. Tıklandığında, düğmeyi genellikle ortak içeren bir menü açılır **dosya** gibi komutlar **açık**, **Kaydet**, ve **çıkış**.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|Oluşturur ve başlatır bir `CMFCRibbonApplicationButton` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|`CMFCRibbonApplicationButton::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCRibbonApplicationButton::SetImage](#setimage)|Görüntü şeridi uygulama düğmeyi atar.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCRibbonApplicationButton` sınıfı. Örnek uygulama düğmeyi görüntü atama ve araç ipucu ayarlama işlemini gösterir. Bu kod parçacığı parçasıdır [çizmek istemci örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxRibbonBar.h

##  <a name="cmfcribbonapplicationbutton"></a>  CMFCRibbonApplicationButton::CMFCRibbonApplicationButton

Oluşturur ve başlatır bir [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) nesne.

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
  CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>Parametreler

*uiBmpResID*<br/>
Uygulama çubuğunda görüntülemek için kaynak Kimliğini görüntü.

*hBmp*<br/>
Uygulama çubuğunda görüntülenecek bir bit eşlem işleyici.

### <a name="remarks"></a>Açıklamalar

Şerit uygulaması uygulama penceresinin sol üst köşede bulunan özel bir düğme düğmesidir. Bir kullanıcı bu düğmeyi tıkladığında, uygulama genellikle ortak içeren bir menü açılır **dosya** gibi komutlar **açık**, **Kaydet**, ve **çıkış**.

##  <a name="setimage"></a>  CMFCRibbonApplicationButton::SetImage

Görüntü uygulama düğmeyi atar.

```
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>Parametreler

*uiBmpResID*<br/>
[in] Uygulama çubuğunda görüntülemek için kaynak Kimliğini görüntü.

*hBmp*<br/>
[in] Uygulama çubuğunda görüntülenecek bir bit eşlem işleyici.

### <a name="remarks"></a>Açıklamalar

Düğme oluşturduktan sonra yeni bir görüntü için Şerit uygulama düğmesini atamak için bu yöntemi kullanın. Uygulama düğmesi, uygulama penceresinin sol üst köşede bulunur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
