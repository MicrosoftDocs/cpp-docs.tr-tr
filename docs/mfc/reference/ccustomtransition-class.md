---
title: CCustomTransition sınıfı
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
ms.openlocfilehash: af600704f82a0cad402948286fa0d4b11dca0c71
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578379"
---
# <a name="ccustomtransition-class"></a>CCustomTransition sınıfı

Özel bir geçiş uygular.

## <a name="syntax"></a>Sözdizimi

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCustomTransition::CCustomTransition](#ccustomtransition)|Bir özel geçiş nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCustomTransition::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Bu geçişle ilişkilendirilmiş bir animasyon değişkenini uygulanacak bir başlangıç değeri ayarlar.|
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Bu geçişle ilişkilendirilmiş bir animasyon değişkenini uygulanacak bir başlangıç hızı ayarlar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|Başlangıç değeri ile SetInitialValue belirtilip belirtilmediğini belirtir.|
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|Başlangıç hızı ile SetInitialVelocity belirtilip belirtilmediğini belirtir.|
|[CCustomTransition::m_initialValue](#m_initialvalue)|Başlangıç değeri depolar.|
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|Başlangıç hızı depolar.|
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|Özel bir ara bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Özel geçişleri geliştiricilerin CCustomTransitions sınıfı sağlar. Oluşturulmuş ve standart bir geçiş kullanılır, ancak oluşturucusuna bir işaretçi özel bir ara parametre olarak kabul eder. Özel geçişlerini kullanmak için aşağıdaki adımları gerçekleştirin: 1. Ccustomınterpolator bir sınıf türetin ve en az uygulamak InterpolateValue yöntemi. 2. Özel bir ara nesne ömrünü kullanıldığı animasyon süreden uzun olmasını sağlayın. 3. CCustomTransition nesne örneğini (yeni işleç kullanarak) ve bir işaretçi Oluşturucudaki özel bir ara geçirebilirsiniz. 4. Bu parametreler için özel ilişkilendirme gerekliyse CCustomTransition::SetInitialValue ve CCustomTransition::SetInitialVelocity çağırın. 5. İşaretçi değeri ile özel algoritması animasyonlu animasyon nesnesinin AddTransition yöntemine özel geçiş geçirin. 6. Animasyon nesnesinin değerini değiştirdiğinizde Windows animasyon API'sı Ccustomınterpolator InterpolateValue (ve ilgili diğer yöntemleri) çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="ccustomtransition"></a>  CCustomTransition::CCustomTransition

Bir özel geçiş nesnesi oluşturur.

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parametreler

*pInterpolator*<br/>
Özel bir ara bir işaretçi.

##  <a name="create"></a>  CCustomTransition::Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>Parametreler

*pFactory*<br/>
Özel bir geçiş oluşturmak için sorumlu geçiş fabrikası için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ilk değer ve bu geçiş ile ilişkili bir animasyon değişkenini uygulanacak başlangıç hızı da ayarlayabilirsiniz. Bu amaçla framework (CAnimationController::AnimateGroup çağırdığınızda gerçekleşir) geçiş kapsüllenmiş COM nesnesi oluşturmadan önce SetInitialValue ve SetInitialVelocity çağırmak zorunda.

##  <a name="m_binitialvaluespecified"></a>  CCustomTransition::m_bInitialValueSpecified

Başlangıç değeri ile SetInitialValue belirtilip belirtilmediğini belirtir.

```
BOOL m_bInitialValueSpecified;
```

##  <a name="m_binitialvelocityspecified"></a>  CCustomTransition::m_bInitialVelocitySpecified

Başlangıç hızı ile SetInitialVelocity belirtilip belirtilmediğini belirtir.

```
BOOL m_bInitialVelocitySpecified;
```

##  <a name="m_initialvalue"></a>  CCustomTransition::m_initialValue

Başlangıç değeri depolar.

```
DOUBLE m_initialValue;
```

##  <a name="m_initialvelocity"></a>  CCustomTransition::m_initialVelocity

Başlangıç hızı depolar.

```
DOUBLE m_initialVelocity;
```

##  <a name="m_pinterpolator"></a>  CCustomTransition::m_pInterpolator

Özel bir ara bir işaretçi depolar.

```
CCustomInterpolator* m_pInterpolator;
```

##  <a name="setinitialvalue"></a>  CCustomTransition::SetInitialValue

Bu geçişle ilişkilendirilmiş bir animasyon değişkenini uygulanacak bir başlangıç değeri ayarlar.

```
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>Parametreler

*initialValue*

##  <a name="setinitialvelocity"></a>  CCustomTransition::SetInitialVelocity

Bu geçişle ilişkilendirilmiş bir animasyon değişkenini uygulanacak bir başlangıç hızı ayarlar.

```
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametreler

*initialVelocity*

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
