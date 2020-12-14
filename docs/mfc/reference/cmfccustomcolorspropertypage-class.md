---
description: 'Şu konuda daha fazla bilgi edinin: CMFCCustomColorsPropertyPage sınıfı'
title: CMFCCustomColorsPropertyPage sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: 9a1e5a83f2dcb291b266c3ef8fcd65422d30135a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193350"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage sınıfı

Renk iletişim kutusunda özel renkler seçebileceğiniz bir özellik sayfasını temsil eder.

## <a name="syntax"></a>Syntax

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|`CMFCCustomColorsPropertyPage::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CMFCCustomColorsPropertyPage::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCCustomColorsPropertyPage:: Setup](#setup)|Özellik sayfasının renk bileşenlerini ayarlar.|

### <a name="remarks"></a>Açıklamalar

`CMFCColorDialog`Sınıfı, özel renk özellik sayfasını göstermek için bu sınıfı kullanır. Hakkında daha fazla bilgi için `CMFCColorDialog` bkz. [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `CMFCCustomColorsPropertyPage` ve özellik sayfasının renk bileşenlerini nasıl ayarlayabileceğinizi gösterir.

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcustomcolorspropertypage. h

## <a name="cmfccustomcolorspropertypagesetup"></a><a name="setup"></a> CMFCCustomColorsPropertyPage:: Setup

Özellik sayfasının renk bileşenlerini ayarlar.

```cpp
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parametreler

*Sağ*\
'ndaki RGB değerinin kırmızı bileşeni.

*Acil*\
'ndaki RGB değerinin yeşil bileşeni.

*Kenarı*\
'ndaki RGB değerinin mavi bileşeni.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, geçerli RGB 'yi ve özellik sayfasının ilişkili HLS (ton, açıklık ve doygunluk) renk değerlerini güncelleştirir. [CMFCColorDialog:: SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) yöntemi, Framework renk iletişim kutusunu başlattığında veya Kullanıcı farenin sol düğmesine bastığında bu yöntemi çağırır. Hakkında daha fazla bilgi için `CMFCColorDialog` bkz. [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCStandardColorsPropertyPage sınıfı](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
