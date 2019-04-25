---
title: CDiscreteTransition sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::Create
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_delay
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_hold
helpviewer_keywords:
- CDiscreteTransition [MFC], CDiscreteTransition
- CDiscreteTransition [MFC], Create
- CDiscreteTransition [MFC], m_dblFinalValue
- CDiscreteTransition [MFC], m_delay
- CDiscreteTransition [MFC], m_hold
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
ms.openlocfilehash: dc2311f7dae71f7c3848b7825b297ec5c9747859
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168017"
---
# <a name="cdiscretetransition-class"></a>CDiscreteTransition sınıfı

Bir ayrık geçişi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CDiscreteTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDiscreteTransition::CDiscreteTransition](#cdiscretetransition)|Bir ayrık geçişi nesnesi oluşturur ve parametrelerini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDiscreteTransition::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDiscreteTransition::m_dblFinalValue](#m_dblfinalvalue)|Geçiş sonunda animasyon değişkeninin değeri.|
|[CDiscreteTransition::m_delay](#m_delay)|Son değer anlık geçiş gecikme, süre miktarı.|
|[CDiscreteTransition::m_hold](#m_hold)|Değişkenin son değerini tutmak saat miktarı.|

## <a name="remarks"></a>Açıklamalar

Bir ayrık geçişi sırasında animasyon değişkenin ilk değer belirtilen gecikme süresi ve ardından anahtarlara anında belirtilen son değer ve bu değer, kalan için bir verilen Durma süresini kalır. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işleci kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Üye değişkenleri tüketimi bu COM nesnesi oluşturulmasını etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="cdiscretetransition"></a>  CDiscreteTransition::CDiscreteTransition

Bir ayrık geçişi nesnesi oluşturur ve parametrelerini başlatır.

```
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,
    DOUBLE dblFinalValue,
    UI_ANIMATION_SECONDS hold);
```

### <a name="parameters"></a>Parametreler

*gecikme*<br/>
Son değer anlık geçiş gecikme, süre miktarı.

*dblFinalValue*<br/>
Geçiş sonunda animasyon değişkeninin değeri.

*tutun*<br/>
Değişkenin son değerini tutmak saat miktarı.

##  <a name="create"></a>  CDiscreteTransition::Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

*pLibrary*<br/>
Bir işaretçi bir [IUIAnimationTransitionLibrary arabirimi](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), standart geçişleri kitaplığını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa TRUE; Aksi durumda FALSE.

##  <a name="m_dblfinalvalue"></a>  CDiscreteTransition::m_dblFinalValue

Geçiş sonunda animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_delay"></a>  CDiscreteTransition::m_delay

Son değer anlık geçiş gecikme, süre miktarı.

```
UI_ANIMATION_SECONDS m_delay;
```

##  <a name="m_hold"></a>  CDiscreteTransition::m_hold

Değişkenin son değerini tutmak saat miktarı.

```
UI_ANIMATION_SECONDS m_hold;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
