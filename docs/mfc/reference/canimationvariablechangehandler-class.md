---
title: CAnimationVariableChangeHandler Sınıfı
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
ms.openlocfilehash: 2dc8f2c03f9df34012fb9db1ed5e5b0bb448b17f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755047"
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler Sınıfı

Animasyon değişkeninin değeri değiştiğinde Animasyon API'si tarafından çağrılan bir geri arama uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Bir `CAnimationVariableChangeHandler` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|Nesne örneği `CAnimationVariableChangeHandler` oluşturur.|
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|Animasyon değişkeninin değeri değiştiğinde çağrılır. (Geçersiz `CUIAnimationVariableChangeHandlerBase::OnValueChanged`kılar .)|
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|Olayları yönlendirmek için animasyon denetleyicisine işaretçi saklar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi `IUIAnimationVariable::SetVariableChangeHandler` oluşturulur ve yönteme geçirilir, ne zaman ya `CAnimationVariable::EnableValueChangedEvent` da `CAnimationBaseObject::EnableValueChangedEvent` (bir animasyon nesnesi içinde kapsüllenmiş tüm animasyon değişkenleri için bu olayı sağlar).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationvariablechangehandleronvaluechanged"></a><a name="onvaluechanged"></a>CAnimationVariableChangeHandler::OnValueChanged

Animasyon değişkeninin değeri değiştiğinde çağrılır.

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>Parametreler

*Film şeridi*<br/>
Değişkeni animateden hikaye tahtası.

*Değişken*<br/>
Güncelleştirilen animasyon değişkeni.

*Newvalue*<br/>
Yeni değer.

*öncekiDeğer*<br/>
Önceki değer.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="canimationvariablechangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>CAnimationVariableChangeHandler::SetAnimationController

Olayları yönlendirmek için animasyon denetleyicisine işaretçi saklar.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacak animasyon denetleyicisi için bir işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
