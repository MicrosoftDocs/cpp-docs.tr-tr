---
description: 'Daha fazla bilgi edinin: CCustomTransition sınıfı'
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
ms.openlocfilehash: 22c08cdcedc3a7cbdbe824ac1d98d62cfe810772
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227669"
---
# <a name="ccustomtransition-class"></a>CCustomTransition sınıfı

Özel bir geçiş uygular.

## <a name="syntax"></a>Syntax

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCustomTransition:: CCustomTransition](#ccustomtransition)|Özel bir geçiş nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCustomTransition:: Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. ( [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create)geçersiz kılar.)|
|[CCustomTransition:: SetInitialValue](#setinitialvalue)|Bu geçişle ilişkili bir animasyon değişkenine uygulanacak bir başlangıç değeri ayarlar.|
|[CCustomTransition:: SetInitialVelocity](#setinitialvelocity)|Bu geçişle ilişkili bir animasyon değişkenine uygulanacak bir başlangıç hızı belirler.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCustomTransition:: m_bInitialValueSpecified](#m_binitialvaluespecified)|Başlangıç değerinin SetInitialValue ile belirlenip belirtilmediğini belirtir.|
|[CCustomTransition:: m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|Başlangıç hızın SetInitialVelocity ile belirlenip belirtilmediğini belirtir.|
|[CCustomTransition:: m_initialValue](#m_initialvalue)|İlk değeri depolar.|
|[CCustomTransition:: m_initialVelocity](#m_initialvelocity)|İlk hızı depolar.|
|[CCustomTransition:: m_pInterpolator](#m_pinterpolator)|Özel bir ara değer göstergesi için bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Ccustomgeçişler sınıfı, geliştiricilerin özel geçişler uygulamasına olanak tanır. Oluşturulur ve standart geçiş olarak kullanılır, ancak Oluşturucusu parametre olarak özel bir enterpolatörü işaretçisi olarak kabul eder. Özel geçişleri kullanmak için aşağıdaki adımları gerçekleştirin: 1. Ccustominterpolatör öğesinden bir sınıf türetirsiniz ve en az Enterpolatevalue yöntemi uygulayın. 2. Özel ara değer layıcı nesnesinin kullanım ömrünün, kullanıldığı bir animasyon süresinden daha uzun olması gerekir. 3. Bir CCustomTransition nesnesi (New işlecini kullanarak) örneği oluşturun ve oluşturucuda özel enterpolalatör öğesine bir işaretçi geçirin. 4. Özel ilişkilendirme için bu parametreler gerekliyse CCustomTransition:: SetInitialValue ve CCustomTransition:: SetInitialVelocity öğesini çağırın. 5. Değeri, özel algoritmayla birlikte animasyon eklenecek olan animasyon nesnesinin AddTransition yöntemine özel geçişe geçirin. 6. Animasyon nesnesinin değeri Windows animasyon API 'sini değiştirmeli, Ccustominterpolatör içinde Enterpolatevalue (ve diğer ilgili yöntemleri) yöntemini çağırır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="ccustomtransitionccustomtransition"></a><a name="ccustomtransition"></a> CCustomTransition:: CCustomTransition

Özel bir geçiş nesnesi oluşturur.

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parametreler

*Ince merdiven*<br/>
Özel enterpolatörü işaretçisi.

## <a name="ccustomtransitioncreate"></a><a name="create"></a> CCustomTransition:: Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>Parametreler

*pFactory*<br/>
Özel geçişler oluşturmaktan sorumlu olan geçiş fabrikası için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bu yöntem aynı zamanda, bu geçişle ilişkili bir animasyon değişkenine uygulanacak ilk değeri ve başlangıç hızını ayarlayabilir. Bu amaçla, çerçeve kapsüllenmiş geçiş COM nesnesini oluşturmadan önce SetInitialValue ve SetInitialVelocity çağrısı yapmanız gerekir (CAnimationController:: AnimateGroup ' i çağırdığınızda gerçekleşir).

## <a name="ccustomtransitionm_binitialvaluespecified"></a><a name="m_binitialvaluespecified"></a> CCustomTransition:: m_bInitialValueSpecified

Başlangıç değerinin SetInitialValue ile belirlenip belirtilmediğini belirtir.

```
BOOL m_bInitialValueSpecified;
```

## <a name="ccustomtransitionm_binitialvelocityspecified"></a><a name="m_binitialvelocityspecified"></a> CCustomTransition:: m_bInitialVelocitySpecified

Başlangıç hızın SetInitialVelocity ile belirlenip belirtilmediğini belirtir.

```
BOOL m_bInitialVelocitySpecified;
```

## <a name="ccustomtransitionm_initialvalue"></a><a name="m_initialvalue"></a> CCustomTransition:: m_initialValue

İlk değeri depolar.

```
DOUBLE m_initialValue;
```

## <a name="ccustomtransitionm_initialvelocity"></a><a name="m_initialvelocity"></a> CCustomTransition:: m_initialVelocity

İlk hızı depolar.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustomtransitionm_pinterpolator"></a><a name="m_pinterpolator"></a> CCustomTransition:: m_pInterpolator

Özel bir ara değer göstergesi için bir işaretçi depolar.

```
CCustomInterpolator* m_pInterpolator;
```

## <a name="ccustomtransitionsetinitialvalue"></a><a name="setinitialvalue"></a> CCustomTransition:: SetInitialValue

Bu geçişle ilişkili bir animasyon değişkenine uygulanacak bir başlangıç değeri ayarlar.

```cpp
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>Parametreler

*InitialValue*

## <a name="ccustomtransitionsetinitialvelocity"></a><a name="setinitialvelocity"></a> CCustomTransition:: SetInitialVelocity

Bu geçişle ilişkili bir animasyon değişkenine uygulanacak bir başlangıç hızı belirler.

```cpp
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametreler

*InitialVelocity*

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
