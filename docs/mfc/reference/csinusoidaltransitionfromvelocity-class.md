---
description: 'Daha fazla bilgi edinin: Csinusoidalınlationtionfromvelocity sınıfı'
title: Csinusoidalgeçişli Tionfromvelocity sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_period
helpviewer_keywords:
- CSinusoidalTransitionFromVelocity [MFC], CSinusoidalTransitionFromVelocity
- CSinusoidalTransitionFromVelocity [MFC], Create
- CSinusoidalTransitionFromVelocity [MFC], m_duration
- CSinusoidalTransitionFromVelocity [MFC], m_period
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
ms.openlocfilehash: 96f4a4c6343f3635f3b60480f49c5af6e6f1e089
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342760"
---
# <a name="csinusoidaltransitionfromvelocity-class"></a>Csinusoidalgeçişli Tionfromvelocity sınıfı

Animasyon değişkeninin ilk hızına göre belirlenen bir genlik değeri olan bir sinusoidal-hız geçişini kapsüller.

## <a name="syntax"></a>Syntax

```
class CSinusoidalTransitionFromVelocity : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Csinusoidalrationfromvelocity:: Csinusoidalsonfromvelocity](#csinusoidaltransitionfromvelocity)|Bir geçiş nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Csinusoidalgeçişli Tionfromvelocity:: Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. ( [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create)geçersiz kılar.)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Csinusoidalrationfromvelocity:: m_duration](#m_duration)|Geçişin süresi.|
|[Csinusoidalrationfromvelocity:: m_period](#m_period)|Saniyeler içinde sinusoidal dalgasının sınlation süresi.|

## <a name="remarks"></a>Açıklamalar

Animasyon değişkeninin değeri, bir sinusoidal Aralık geçişinin tüm süresi boyunca ilk değeri etrafında atlar. Sılation genliği, geçiş başladığında animasyon değişkeninin hızına göre belirlenir. Tüm geçişler otomatik olarak temizlendiğinden, Yeni işleç kullanılarak ayrılmaları önerilir. Encapsulated IUIAnimationTransition COM nesnesi, NULL olana kadar CAnimationController:: AnimateGroup tarafından oluşturulur. Bu COM nesnesi oluşturulduktan sonra üye değişkenlerinin değiştirilmesinin etkisi olmaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[Csinusoidalrationfromvelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="csinusoidaltransitionfromvelocitycreate"></a><a name="create"></a> Csinusoidalgeçişli Tionfromvelocity:: Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişlerin oluşturulmasından sorumlu olan geçiş kitaplığı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa doğru; Aksi halde yanlış.

## <a name="csinusoidaltransitionfromvelocitycsinusoidaltransitionfromvelocity"></a><a name="csinusoidaltransitionfromvelocity"></a> Csinusoidalrationfromvelocity:: Csinusoidalsonfromvelocity

Bir geçiş nesnesi oluşturur.

```
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,
    UI_ANIMATION_SECONDS period);
```

### <a name="parameters"></a>Parametreler

*süre*<br/>
Geçişin süresi.

*dönemini*<br/>
Saniyeler içinde sinusoidal dalgasının sınlation süresi.

## <a name="csinusoidaltransitionfromvelocitym_duration"></a><a name="m_duration"></a> Csinusoidalrationfromvelocity:: m_duration

Geçişin süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromvelocitym_period"></a><a name="m_period"></a> Csinusoidalrationfromvelocity:: m_period

Saniyeler içinde sinusoidal dalgasının sınlation süresi.

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
