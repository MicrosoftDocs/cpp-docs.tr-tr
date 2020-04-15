---
title: CMFCDisableMenuAnimation Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
ms.openlocfilehash: 990f41d2dfa6491d246797322ee275c9648d52a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367579"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation Sınıfı

Açılır menü animasyonuna devre dışı bıraktı.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Bir `CMFCDisableMenuAnimation` nesne inşa eder.|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCDisableMenuAnimation::Geri Yükleme](#restore)|Açılır menüyü görüntülemek için kullanılan çerçevenin önceki animasyonu geri yükler.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|Adı|Açıklama|
|`CMFCDisableMenuAnimation::m_animType`|Önceki açılır menü animasyon türünü depolar.|

### <a name="remarks"></a>Açıklamalar

Açılır menü animasyonunu geçici olarak devre dışı bıraktı (örneğin, fare veya klavye komutlarını işlediğinde) bu yardımcı sınıfı kullanın.

Bir `CMFCDisableMenuAnimation` nesne, kullanım ömrü boyunca açılır menü animasyonunu devre dışı kılabilir. Oluşturucu, geçerli açılır menü animasyon türünü `m_animType` alanda depolar ve `CMFCPopupMenu::NO_ANIMATION`geçerli animasyon türünü . Yıkıcı önceki animasyon türünü geri yükler.

Tek bir `CMFCDisableMenuAnimation` işlev boyunca açılır menü animasyonunu devre dışı kayırmak için yığında bir nesne oluşturabilirsiniz. Işlevler arasında açılır menü animasyonu devre dışı `CMFCDisableMenuAnimation` kalmak istiyorsanız, yığında bir nesne oluşturun ve açılır menü animasyonuna geri yüklemek istediğinizde silin.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, menü animasyonunu geçici olarak devre dışı kısımak için yığının nasıl kullanılacağı gösterilmektedir.

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpopupmenu.h

## <a name="cmfcdisablemenuanimationrestore"></a><a name="restore"></a>CMFCDisableMenuAnimation::Geri Yükleme

Açılır menüyü görüntülemek için kullanılan çerçevenin önceki animasyonu geri yükler.

```
void Restore ();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir `CMFCDisableMenuAnimation` açılır menü görüntülemek için kullanılan çerçeve önceki animasyonu geri yüklemek için yıkıcı tarafından çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopUpMenü Sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)
