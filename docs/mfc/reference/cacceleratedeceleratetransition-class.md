---
title: CAccelerateDecelerateTransition sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: 1e55e81b4d9b5c324f86bfd141b74d9faa362d94
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507735"
---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateTransition sınıfı

Hızlandırma-yavaşlatma geçişi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Bir geçiş nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAccelerateDecelerateTransition:: Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. ( [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create)geçersiz kılar.)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Süreyi hızlandırarak harcanan sürenin oranı.|
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Süre yavaşlatıcı harcanan sürenin oranı.|
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Geçişin süresi.|
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Geçişin sonundaki animasyon değişkeninin değeri.|

## <a name="remarks"></a>Açıklamalar

Hızlandırmasız bir geçiş sırasında animasyon değişkeni hızlanır ve sonra belirtilen değerde sona ermek üzere geçiş süresince yavaşlar. Farklı hızlandırma ve yavaşlatma oranları belirterek değişkenin bağımsız olarak ne kadar hızlı hızlaracağını ve yavaşlatmayı kontrol edebilirsiniz. İlk hız sıfır olduğunda, ivme oranı, değişkenin harcayacağı sürenin kesiri olur; aynı şekilde yavaşlalama oranına sahiptir. İlk hız sıfır değilse, sıfıra ulaşan hız ve geçişin sonuna kadar geçen sürenin kesiri olur. Hızlandırma oranı ve yavaşlatma oranı en fazla 1,0 olmalıdır. Tüm geçişler otomatik olarak temizlendiğinden, Yeni işleç kullanılarak ayrılmaları önerilir. Encapsulated IUIAnimationTransition COM nesnesi, NULL olana kadar CAnimationController:: AnimateGroup tarafından oluşturulur. Bu COM nesnesi oluşturulduktan sonra üye değişkenlerinin değiştirilmesinin etkisi olmaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

##  <a name="cacceleratedeceleratetransition"></a>CAccelerateDecelerateTransition::CAccelerateDecelerateTransition

Bir geçiş nesnesi oluşturur.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Geçişin süresi.

*Sonlandırdeğer*<br/>
Geçişin sonundaki animasyon değişkeninin değeri.

*accelerationRatio*<br/>
Süreyi hızlandırarak harcanan sürenin oranı.

*decelerationRatio*<br/>
Süre yavaşlatıcı harcanan sürenin oranı.

##  <a name="create"></a>CAccelerateDecelerateTransition:: Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişlerin kitaplığını tanımlayan [ıuıanimationgeçişli Tionlibrary arabirimine](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa doğru; Aksi halde yanlış.

##  <a name="m_accelerationratio"></a>CAccelerateDecelerateTransition::m_accelerationRatio

Süreyi hızlandırarak harcanan sürenin oranı.

```
DOUBLE m_accelerationRatio;
```

##  <a name="m_decelerationratio"></a>CAccelerateDecelerateTransition::m_decelerationRatio

Süre yavaşlatıcı harcanan sürenin oranı.

```
DOUBLE m_decelerationRatio;
```

##  <a name="m_duration"></a>CAccelerateDecelerateTransition::m_duration

Geçişin süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>CAccelerateDecelerateTransition::m_finalValue

Geçişin sonundaki animasyon değişkeninin değeri.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
