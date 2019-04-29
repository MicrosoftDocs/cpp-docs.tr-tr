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
ms.openlocfilehash: bf8c598e9e105569e0a5676267e205b3d3939712
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345610"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation sınıfı

Açılır menü animasyon devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Oluşturur bir `CMFCDisableMenuAnimation` nesne.|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCDisableMenuAnimation::Restore](#restore)|Framework'açılır menüyü görüntülemek için kullanılan önceki animasyon geri yükler.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|Ad|Açıklama|
|`CMFCDisableMenuAnimation::m_animType`|Önceki açılır menü animasyon türü depolar.|

### <a name="remarks"></a>Açıklamalar

Geçici olarak (örneğin, fare ve klavye komutları işlemek) açılır menüsünden animasyon devre dışı bırakmak için bu yardımcı sınıfını kullanın.

A `CMFCDisableMenuAnimation` nesne ömrü boyunca açılır menü animasyon devre dışı bırakır. Geçerli açılır menü animasyon türü Oluşturucu depolar `m_animType` alan ve geçerli animasyon türü için kümeleri `CMFCPopupMenu::NO_ANIMATION`. Yok edici, önceki animasyon türü geri yükler.

Oluşturabileceğiniz bir `CMFCDisableMenuAnimation` açılır menü animasyon tek bir işlev boyunca devre dışı bırakmak için yığında nesne. Açılan menü animasyon işlevler arası devre dışı bırakmak isterseniz, bir `CMFCDisableMenuAnimation` yığında nesne ve açılır menüyü animasyon geri yüklemek istediğinizde Sil.

## <a name="example"></a>Örnek

Aşağıdaki örnek, geçici olarak menü animasyon devre dışı bırakmak için yığın kullanmayı gösterir.

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxpopupmenu.h

##  <a name="restore"></a>  CMFCDisableMenuAnimation::Restore

Framework'açılır menüyü görüntülemek için kullanılan önceki animasyon geri yükler.

```
void Restore ();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran `CMFCDisableMenuAnimation` framework açılan menüyü görüntülemek için kullanılan önceki animasyon geri yüklemek için yıkıcı.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu Sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)
