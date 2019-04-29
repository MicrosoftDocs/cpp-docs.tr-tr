---
title: CSmoothStopTransition Class
ms.date: 11/04/2016
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
ms.openlocfilehash: 89496c1b867d6fbb498f56271de7b45afef7edc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323888"
---
# <a name="csmoothstoptransition-class"></a>CSmoothStopTransition Class

Yumuşak bitişli geçişi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CSmoothStopTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSmoothStopTransition::CSmoothStopTransition](#csmoothstoptransition)|Yumuşak bitişli geçişi oluşturur ve onun en uzun süre ve son değer başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSmoothStopTransition::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CSmoothStopTransition::m_dblFinalValue](#m_dblfinalvalue)|Geçiş sonunda animasyon değişkeninin değeri.|
|[CSmoothStopTransition::m_maximumDuration](#m_maximumduration)|Geçişi en uzun süresi.|

## <a name="remarks"></a>Açıklamalar

Verilen son değer yaklaştığında ve sıfır bir hız ile ulaştığında bitişli geçişi yavaşlar. Geçiş süresi, ilk ve son değerleri ve belirtilen en uzun süre arasındaki fark başlangıç hızı tarafından belirlenir. Hiçbir çözüm tek bir parabolik yay oluşan varsa, bu yöntem, bir üçüncü derece geçişi oluşturur. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işleci kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Üye değişkenleri tüketimi bu COM nesnesi oluşturulmasını etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="create"></a>  CSmoothStopTransition::Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişleri oluşturulması için sorumlu geçiş kitaplığı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa TRUE; Aksi durumda FALSE.

##  <a name="csmoothstoptransition"></a>  CSmoothStopTransition::CSmoothStopTransition

Yumuşak bitişli geçişi oluşturur ve onun en uzun süre ve son değer başlatır.

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Parametreler

*maximumDuration*<br/>
Geçişi en uzun süresi.

*dblFinalValue*<br/>
Geçiş sonunda animasyon değişkeninin değeri.

##  <a name="m_dblfinalvalue"></a>  CSmoothStopTransition::m_dblFinalValue

Geçiş sonunda animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_maximumduration"></a>  CSmoothStopTransition::m_maximumDuration

Geçişi en uzun süresi.

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
