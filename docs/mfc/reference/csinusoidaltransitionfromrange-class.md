---
description: 'Daha fazla bilgi edinin: Csinusoidalınlationtionfromrange sınıfı'
title: Csinusoidalınlationtionfromrange sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
ms.openlocfilehash: 5d00b1cbfb8fe9b76a5a69bd1c9f10316ddf8141
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264576"
---
# <a name="csinusoidaltransitionfromrange-class"></a>Csinusoidalınlationtionfromrange sınıfı

Belirli bir sılation aralığına sahip bir sinusoidal Aralık geçişini kapsüller.

## <a name="syntax"></a>Syntax

```
class CSinusoidalTransitionFromRange : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Csinusoidalslationtionfromrange:: Csinusoidalrationfromrange](#csinusoidaltransitionfromrange)|Bir geçiş nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Csinusoidalgeçişli Tionfromrange:: Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. ( [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create)geçersiz kılar.)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Csinusoidalgeçişli Tionfromrange:: m_dblMaximumValue](#m_dblmaximumvalue)|Sinusoidal dalgasının en üstünde animasyon değişkeninin değeri.|
|[Csinusoidalgeçişli Tionfromrange:: m_dblMinimumValue](#m_dblminimumvalue)|Sinusoidal Wave 'nin bir Trough üzerindeki animasyon değişkeninin değeri.|
|[Csinusoidalgeçişli Tionfromrange:: m_duration](#m_duration)|Geçişin süresi.|
|[Csinusoidalgeçişli Tionfromrange:: m_period](#m_period)|Saniyeler içinde sinusoidal dalgasının sınlation süresi.|
|[Csinusoidalgeçişli Tionfromrange:: m_slope](#m_slope)|Geçişin başlangıcında eğim.|

## <a name="remarks"></a>Açıklamalar

Animasyon değişkeninin değeri, bir sinusoidal Aralık geçişinin tüm süresi boyunca belirtilen en düşük ve en yüksek değerler arasında dalgalanmaktadır. Eğim parametresi, diğer parametreler tarafından belirtilen iki olası sinüs dalgaları arasında belirsizliği ortadan kaldırmak için kullanılır. Tüm geçişler otomatik olarak temizlendiğinden, Yeni işleç kullanılarak ayrılmaları önerilir. Encapsulated IUIAnimationTransition COM nesnesi, NULL olana kadar CAnimationController:: AnimateGroup tarafından oluşturulur. Bu COM nesnesi oluşturulduktan sonra üye değişkenlerinin değiştirilmesinin etkisi olmaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[Csinusoidalgeçişli Tionfromrange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="csinusoidaltransitionfromrangecreate"></a><a name="create"></a> Csinusoidalgeçişli Tionfromrange:: Create

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

## <a name="csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a> Csinusoidalslationtionfromrange:: Csinusoidalrationfromrange

Bir geçiş nesnesi oluşturur.

```
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblMinimumValue,
    DOUBLE dblMaximumValue,
    UI_ANIMATION_SECONDS period,
    UI_ANIMATION_SLOPE slope);
```

### <a name="parameters"></a>Parametreler

*süre*<br/>
Geçişin süresi.

*dblMinimumValue*<br/>
Sinusoidal Wave 'nin bir Trough üzerindeki animasyon değişkeninin değeri.

*dblMaximumValue*<br/>
Sinusoidal dalgasının en üstünde animasyon değişkeninin değeri.

*dönemini*<br/>
Saniyeler içinde sinusoidal dalgasının sınlation süresi.

*eğilmiş*<br/>
Geçişin başlangıcında eğim.

## <a name="csinusoidaltransitionfromrangem_dblmaximumvalue"></a><a name="m_dblmaximumvalue"></a> Csinusoidalgeçişli Tionfromrange:: m_dblMaximumValue

Sinusoidal dalgasının en üstünde animasyon değişkeninin değeri.

```
DOUBLE m_dblMaximumValue;
```

## <a name="csinusoidaltransitionfromrangem_dblminimumvalue"></a><a name="m_dblminimumvalue"></a> Csinusoidalgeçişli Tionfromrange:: m_dblMinimumValue

Sinusoidal Wave 'nin bir Trough üzerindeki animasyon değişkeninin değeri.

```
DOUBLE m_dblMinimumValue;
```

## <a name="csinusoidaltransitionfromrangem_duration"></a><a name="m_duration"></a> Csinusoidalgeçişli Tionfromrange:: m_duration

Geçişin süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromrangem_period"></a><a name="m_period"></a> Csinusoidalgeçişli Tionfromrange:: m_period

Saniyeler içinde sinusoidal dalgasının sınlation süresi.

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="csinusoidaltransitionfromrangem_slope"></a><a name="m_slope"></a> Csinusoidalgeçişli Tionfromrange:: m_slope

Geçişin başlangıcında eğim.

```
UI_ANIMATION_SLOPE m_slope;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
