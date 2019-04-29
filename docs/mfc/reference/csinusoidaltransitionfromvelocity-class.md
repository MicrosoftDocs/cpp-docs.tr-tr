---
title: CSinusoidalTransitionFromVelocity Class
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
ms.openlocfilehash: f61effb6dacdd1076784de8e825a3acec192474c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324473"
---
# <a name="csinusoidaltransitionfromvelocity-class"></a>CSinusoidalTransitionFromVelocity Class

Animasyon değişkeninin başlangıç hızı tarafından belirlenen bir genliğe sahip sinüzoidal hızlı geçişi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CSinusoidalTransitionFromVelocity : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity](#csinusoidaltransitionfromvelocity)|Geçiş bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity::m_duration](#m_duration)|Geçiş süresi.|
|[CSinusoidalTransitionFromVelocity::m_period](#m_period)|Salınıma sinüzoidal wave, saniye cinsinden süre.|

## <a name="remarks"></a>Açıklamalar

Animasyon değişkeninin değeri başlangıç değeri bir sinüzoidal aralıklı geçişi tüm süresince oscillates. Geçiş başladığında salınım değerine animasyon değişkenin hız tarafından belirlenir. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işleci kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Üye değişkenleri tüketimi bu COM nesnesi oluşturulmasını etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="create"></a>  CSinusoidalTransitionFromVelocity::Create

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

##  <a name="csinusoidaltransitionfromvelocity"></a>  CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity

Geçiş bir nesne oluşturur.

```
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,
    UI_ANIMATION_SECONDS period);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Geçiş süresi.

*Dönem*<br/>
Salınıma sinüzoidal wave, saniye cinsinden süre.

##  <a name="m_duration"></a>  CSinusoidalTransitionFromVelocity::m_duration

Geçiş süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_period"></a>  CSinusoidalTransitionFromVelocity::m_period

Salınıma sinüzoidal wave, saniye cinsinden süre.

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
