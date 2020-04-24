---
title: CMFCCustomColorsPropertyPage Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: 468d947947fc89f9ebc832cda722d854bb8b4be2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752470"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage Sınıfı

Renk iletişim kutusunda özel renkleri seçebilen bir özellik sayfasını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Varsayılan oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|`CMFCCustomColorsPropertyPage::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CMFCCustomColorsPropertyPage::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCCustomColorsÖzellik::Kurulum](#setup)|Özellik sayfasının renk bileşenlerini ayarlar.|

### <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCColorDialog` özel renk özelliği sayfasını görüntülemek için bu sınıfı kullanır. Hakkında `CMFCColorDialog`daha fazla bilgi için [CMFCColorDialog Class'a](../../mfc/reference/cmfccolordialog-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCCustomColorsPropertyPage` nesnenin nasıl oluşturup özellik sayfasının renk bileşenlerinin ayarlanıştını gösterir.

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[Cpropertypage](../../mfc/reference/cpropertypage-class.md)

[CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcustomcolorspropertypage.h

## <a name="cmfccustomcolorspropertypagesetup"></a><a name="setup"></a>CMFCCustomColorsÖzellik::Kurulum

Özellik sayfasının renk bileşenlerini ayarlar.

```cpp
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*R*|[içinde] RGB değerinin kırmızı bileşeni.|
|*G*|[içinde] RGB değerinin yeşil bileşeni.|
|*B*|[içinde] RGB değerinin mavi bileşeni.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, özellik sayfasının geçerli RGB ve ilişkili HLS (renk tonu, hafiflik ve doygunluk) renk değerlerini güncelleştirir. [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) yöntemi, çerçeve renk iletişim kutusunu açar veya kullanıcı sol fare düğmesine bastığında bu yöntemi çağırır. Hakkında `CMFCColorDialog`daha fazla bilgi için [CMFCColorDialog Class'a](../../mfc/reference/cmfccolordialog-class.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog Sınıfı](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCStandardColorsPropertyPage Sınıfı](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
