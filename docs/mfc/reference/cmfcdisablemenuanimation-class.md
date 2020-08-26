---
title: CMFCDisableMenuAnimation sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
ms.openlocfilehash: 97a93e000b3e12d8ec4824100059581216b1b8d9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840771"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation sınıfı

Açılır menü animasyonunu devre dışı bırakır.

## <a name="syntax"></a>Syntax

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Bir `CMFCDisableMenuAnimation` nesnesi oluşturur.|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCDisableMenuAnimation:: restore](#restore)|Çerçevenin bir açılan menüyü göstermek için kullandığı önceki animasyonu geri yükler.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|-|-|
|`CMFCDisableMenuAnimation::m_animType`|Önceki açılan menü animasyon türünü depolar.|

### <a name="remarks"></a>Açıklamalar

Açılır menü animasyonunu geçici olarak devre dışı bırakmak için bu yardımcı sınıfı kullanın (örneğin, fare veya klavye komutlarını işlem sırasında).

Bir `CMFCDisableMenuAnimation` nesne, yaşam süresi boyunca açılır menü animasyonunu devre dışı bırakır. Oluşturucu geçerli açılır menü animasyon türünü `m_animType` alana depolar ve geçerli animasyon türünü olarak ayarlar `CMFCPopupMenu::NO_ANIMATION` . Yıkıcı önceki animasyon türünü geri yükler.

`CMFCDisableMenuAnimation`Tek bir işlevde açılır menü animasyonunu devre dışı bırakmak için yığında bir nesne oluşturabilirsiniz. İşlevler arasında açılan menü animasyonunu devre dışı bırakmak istiyorsanız, `CMFCDisableMenuAnimation` yığında bir nesne oluşturun ve ardından açılır menü animasyonunu geri yüklemek istediğinizde silin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, menü animasyonunu geçici olarak devre dışı bırakmak için yığının nasıl kullanılacağını gösterir.

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpopupmenu. h

## <a name="cmfcdisablemenuanimationrestore"></a><a name="restore"></a> CMFCDisableMenuAnimation:: restore

Çerçevenin bir açılan menüyü göstermek için kullandığı önceki animasyonu geri yükler.

```cpp
void Restore ();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CMFCDisableMenuAnimation` Framework 'ün bir açılan menüyü göstermek için kullandığı önceki animasyonu geri yüklemek için yıkıcısı tarafından çağırılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)
