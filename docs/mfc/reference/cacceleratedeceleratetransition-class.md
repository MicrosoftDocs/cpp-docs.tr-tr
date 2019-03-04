---
title: CAccelerateDecelerateTransition sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: dbebe794ba76ae4abd3d1e3ea6bc8ee31bc3007f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278866"
---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateTransition sınıfı

Uygular-hızlandırma yavaşlatma geçişi.

## <a name="syntax"></a>Sözdizimi

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Geçiş bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAccelerateDecelerateTransition::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Hızlandırma süresi için harcadığı sürenin oranı.|
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Süre yavaşlatma harcadığı sürenin oranı.|
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Geçiş süresi.|
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Geçiş sonunda animasyon değişkeninin değeri.|

## <a name="remarks"></a>Açıklamalar

Bir hızlandırın sırasında-hızlandırma yavaşlatma geçişi, animasyon değişkenini hızlandırır ve belirtilen bir değer bitiş geçiş süresi boyunca ardından yavaşlar. Ne kadar hızlı değişkeni hızlandırır ve bağımsız olarak, farklı hızlandırma ve yavaşlama oranları belirterek decelerates denetleyebilirsiniz. Başlangıç hızı sıfır olduğunda hızlandırma oranına değişkeni hızlandırma harcadığınız süreyi bölümüdür; benzer şekilde ile yavaşlama oranı. Başlangıç hızı sıfır olmayan, bunu sıfır ve geçiş sonuna ulaşmadan hız arasındaki sürenin ise. Hızlandırma oranına ve yavaşlama oranını en fazla 1.0 toplamak. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işleci kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Üye değişkenleri tüketimi bu COM nesnesi oluşturulmasını etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="cacceleratedeceleratetransition"></a>  CAccelerateDecelerateTransition::CAccelerateDecelerateTransition

Geçiş bir nesne oluşturur.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Geçiş süresi.

*finalValue*<br/>
Geçiş sonunda animasyon değişkeninin değeri.

*accelerationRatio*<br/>
Hızlandırma süresi için harcadığı sürenin oranı.

*decelerationRatio*<br/>
Süre yavaşlatma harcadığı sürenin oranı.

##  <a name="create"></a>  CAccelerateDecelerateTransition::Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Bir işaretçi bir [IUIAnimationTransitionLibrary arabirimi](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), standart geçişleri kitaplığını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa TRUE; Aksi durumda FALSE.

##  <a name="m_accelerationratio"></a>  CAccelerateDecelerateTransition::m_accelerationRatio

Hızlandırma süresi için harcadığı sürenin oranı.

```
DOUBLE m_accelerationRatio;
```

##  <a name="m_decelerationratio"></a>  CAccelerateDecelerateTransition::m_decelerationRatio

Süre yavaşlatma harcadığı sürenin oranı.

```
DOUBLE m_decelerationRatio;
```

##  <a name="m_duration"></a>  CAccelerateDecelerateTransition::m_duration

Geçiş süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>  CAccelerateDecelerateTransition::m_finalValue

Geçiş sonunda animasyon değişkeninin değeri.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
