---
description: 'Daha fazla bilgi edinin: CAnimationVariableChangeHandler sınıfı'
title: CAnimationVariableChangeHandler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
ms.openlocfilehash: 1c97bc908a29bfb7edf2222f6df117fefdaf4091
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207884"
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler sınıfı

Animasyon değişkeninin değeri değiştiğinde animasyon API 'Sı tarafından çağrılan bir geri çağırma uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Bir `CAnimationVariableChangeHandler` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|Nesnesinin bir örneğini oluşturur `CAnimationVariableChangeHandler` .|
|[CAnimationVariableChangeHandler:: OnValueChanged](#onvaluechanged)|Bir animasyon değişkeninin değeri değiştiğinde çağırılır. (Geçersiz kılmalar `CUIAnimationVariableChangeHandlerBase::OnValueChanged` .)|
|[CAnimationVariableChangeHandler:: SetAnimationController](#setanimationcontroller)|Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi `IUIAnimationVariable::SetVariableChangeHandler` , veya öğesini çağırdığınızda `CAnimationVariable::EnableValueChangedEvent` `CAnimationBaseObject::EnableValueChangedEvent` (bir animasyon nesnesinde kapsüllenmiş tüm animasyon değişkenleri için bu olayı sağlayan) yöntemi oluşturulur ve yöntemine geçirilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationvariablechangehandleronvaluechanged"></a><a name="onvaluechanged"></a> CAnimationVariableChangeHandler:: OnValueChanged

Bir animasyon değişkeninin değeri değiştiğinde çağırılır.

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>Parametreler

*görsel taslak*<br/>
Değişkeni hareketlendirilen film şeridi.

*değişken*<br/>
Güncelleştirilmiş animasyon değişkeni.

*Değer*<br/>
Yeni değer.

*previousValue*<br/>
Önceki değer.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="canimationvariablechangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationVariableChangeHandler:: SetAnimationController

Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olay alacak bir animasyon denetleyicisi işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
