---
title: CCustomTransition Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
ms.openlocfilehash: 8bdd0ebab0a6e4138e24edff38da9b444745f83a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369322"
---
# <a name="ccustomtransition-class"></a>CCustomTransition Sınıfı

Özel bir geçiş uygular.

## <a name="syntax"></a>Sözdizimi

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCustomTransition::CCustomTransition](#ccustomtransition)|Özel bir geçiş nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCustomTransition::Oluştur](#create)|Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. (CBaseTransition geçersiz [kılar::Oluştur](../../mfc/reference/cbasetransition-class.md#create).)|
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Bu geçişle ilişkili bir animasyon değişkenine uygulanacak bir başlangıç değeri ayarlar.|
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Bu geçişle ilişkili bir animasyon değişkenine uygulanacak bir başlangıç hızı ayarlar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|İlk değerin SetInitialValue ile belirtilip belirtmediğini belirtir.|
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|İlk hızın SetInitialVelocity ile belirtilip belirtilmedigini belirtir.|
|[CCustomTransition::m_initialValue](#m_initialvalue)|Başlangıç değerini depolar.|
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|İlk hızı saklar.|
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|Özel bir enterpolatör için bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

CCustomTransitions sınıfı, geliştiricilerin özel geçişleri uygulamasına olanak tanır. Standart bir geçiş olarak oluşturulur ve kullanılır, ancak oluşturucusu özel bir enterpolatöriçin bir işaretçi parametre olarak kabul eder. Özel geçişleri kullanmak için aşağıdaki adımları gerçekleştirin: 1. CCustomInterpolator bir sınıf türetmek ve en az InterpolateValue yöntemi uygulayın. 2. Özel enterpolatör nesnesinin kullanım ömrünün, kullanıldığı animasyon süresinden daha uzun olduğundan emin olun. 3. Bir CCustomTransition nesnesini anında (operatör yeni kullanarak) anında kullanın ve oluşturucuda özel enterpolatöre işaretçi geçirin. 4. CCustomTransition'ı Arayın:SetInitialValue ve CCustomTransition::Bu parametreler özel enterpolasyon için gerekliyse SetInitialVelocity. 5. Değeri özel algoritma ile animasyonlu olması gereken animasyon nesnesinin AddTransition yöntemine özel geçiş için işaretçiyi geçirin. 6. Animasyon nesnesinin değeri değiştiğinde Windows Animasyon API'si CCustomInterpolator'da InterpolateValue 'i (ve diğer ilgili yöntemleri) arayacaktır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="ccustomtransitionccustomtransition"></a><a name="ccustomtransition"></a>CCustomTransition::CCustomTransition

Özel bir geçiş nesnesi oluşturuyor.

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parametreler

*pInterpolator*<br/>
Özel enterpolatör için bir işaretçi.

## <a name="ccustomtransitioncreate"></a><a name="create"></a>CCustomTransition::Oluştur

Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>Parametreler

*pFactory*<br/>
Özel geçişlerin oluşturulmasından sorumlu geçiş fabrikasıiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu geçişle ilişkili bir animasyon değişkenine uygulanacak başlangıç değerini ve başlangıç hızını da ayarlayabilir. Bu amaçla, çerçeve kapsüllenmiş geçiş COM nesnesini oluşturmadan önce SetInitialValue ve SetInitialVelocity'yi aramanız gerekir (CAnimationController::AnimateGroup'u aradiğinizde gerçekleşir).

## <a name="ccustomtransitionm_binitialvaluespecified"></a><a name="m_binitialvaluespecified"></a>CCustomTransition::m_bInitialValueSpecified

İlk değerin SetInitialValue ile belirtilip belirtmediğini belirtir.

```
BOOL m_bInitialValueSpecified;
```

## <a name="ccustomtransitionm_binitialvelocityspecified"></a><a name="m_binitialvelocityspecified"></a>CCustomTransition::m_bInitialVelocitySpecified

İlk hızın SetInitialVelocity ile belirtilip belirtilmedigini belirtir.

```
BOOL m_bInitialVelocitySpecified;
```

## <a name="ccustomtransitionm_initialvalue"></a><a name="m_initialvalue"></a>CCustomTransition::m_initialValue

Başlangıç değerini depolar.

```
DOUBLE m_initialValue;
```

## <a name="ccustomtransitionm_initialvelocity"></a><a name="m_initialvelocity"></a>CCustomTransition::m_initialVelocity

İlk hızı saklar.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustomtransitionm_pinterpolator"></a><a name="m_pinterpolator"></a>CCustomTransition::m_pInterpolator

Özel bir enterpolatör için bir işaretçi depolar.

```
CCustomInterpolator* m_pInterpolator;
```

## <a name="ccustomtransitionsetinitialvalue"></a><a name="setinitialvalue"></a>CCustomTransition::SetInitialValue

Bu geçişle ilişkili bir animasyon değişkenine uygulanacak bir başlangıç değeri ayarlar.

```
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>Parametreler

*ınitialvalue*

## <a name="ccustomtransitionsetinitialvelocity"></a><a name="setinitialvelocity"></a>CCustomTransition::SetInitialVelocity

Bu geçişle ilişkili bir animasyon değişkenine uygulanacak bir başlangıç hızı ayarlar.

```
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametreler

*ilkHız*

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
