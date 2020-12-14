---
description: 'Daha fazla bilgi edinin: CCubicTransition sınıfı'
title: CCubicTransition sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::Create
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalVelocity
- AFXANIMATIONCONTROLLER/CCubicTransition::m_duration
helpviewer_keywords:
- CCubicTransition [MFC], CCubicTransition
- CCubicTransition [MFC], Create
- CCubicTransition [MFC], m_dblFinalValue
- CCubicTransition [MFC], m_dblFinalVelocity
- CCubicTransition [MFC], m_duration
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
ms.openlocfilehash: 2e83aa10e013595c80a87b5d79cddf80bc46b6ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227786"
---
# <a name="ccubictransition-class"></a>CCubicTransition sınıfı

Üçüncü dereceden geçişi kapsüller.

## <a name="syntax"></a>Syntax

```
class CCubicTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCubicTransition:: CCubicTransition](#ccubictransition)|Bir geçiş nesnesi oluşturur ve parametrelerini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCubicTransition:: Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. ( [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create)geçersiz kılar.)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCubicTransition:: m_dblFinalValue](#m_dblfinalvalue)|Geçişin sonundaki animasyon değişkeninin değeri.|
|[CCubicTransition:: m_dblFinalVelocity](#m_dblfinalvelocity)|Geçişin sonundaki değişkenin hızı.|
|[CCubicTransition:: m_duration](#m_duration)|Geçişin süresi.|

## <a name="remarks"></a>Açıklamalar

Üçüncü dereceden geçiş sırasında animasyon değişkeninin değeri, belirtilen bir hızdan itibaren geçiş süresince ilk değerinden belirtilen bir son değere değişir. Tüm geçişler otomatik olarak temizlendiğinden, Yeni işleç kullanılarak ayrılmaları önerilir. Encapsulated IUIAnimationTransition COM nesnesi, NULL olana kadar CAnimationController:: AnimateGroup tarafından oluşturulur. Bu COM nesnesi oluşturulduktan sonra üye değişkenlerinin değiştirilmesinin etkisi olmaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCubicTransition`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="ccubictransitionccubictransition"></a><a name="ccubictransition"></a> CCubicTransition:: CCubicTransition

Bir geçiş nesnesi oluşturur ve parametrelerini başlatır.

```
CCubicTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE finalVelocity);
```

### <a name="parameters"></a>Parametreler

*süre*<br/>
Geçişin süresi.

*Sonlandırdeğer*<br/>
Geçişin sonundaki animasyon değişkeninin değeri.

*Sonlandırım*<br/>
Geçişin sonundaki değişkenin hızı.

## <a name="ccubictransitioncreate"></a><a name="create"></a> CCubicTransition:: Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişlerin kitaplığını tanımlayan [ıuıanimationgeçişli Tionlibrary arabirimine](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa doğru; Aksi halde yanlış.

## <a name="ccubictransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a> CCubicTransition:: m_dblFinalValue

Geçişin sonundaki animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

## <a name="ccubictransitionm_dblfinalvelocity"></a><a name="m_dblfinalvelocity"></a> CCubicTransition:: m_dblFinalVelocity

Geçişin sonundaki değişkenin hızı.

```
DOUBLE m_dblFinalVelocity;
```

## <a name="ccubictransitionm_duration"></a><a name="m_duration"></a> CCubicTransition:: m_duration

Geçişin süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
