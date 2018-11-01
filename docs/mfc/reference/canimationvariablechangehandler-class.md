---
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
ms.openlocfilehash: 589691f8bb2bc14eba46245082ff972ca6b97fcc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604410"
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler sınıfı

Animasyon değişkeninin bir değeri değiştiğinde animasyon API'sı tarafından çağrılan bir geri arama gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Oluşturur bir `CAnimationVariableChangeHandler` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|Örneği oluşturur `CAnimationVariableChangeHandler` nesne.|
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|Bir animasyon değişkeninin bir değeri değiştirildiğinde çağırılır. (Geçersiz kılmaları `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.)|
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|Animasyon denetleyicisini rota olaylar için bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi oluşturulur ve geçirilen `IUIAnimationVariable::SetVariableChangeHandler` yöntemi çağırdığınızda, `CAnimationVariable::EnableValueChangedEvent` veya `CAnimationBaseObject::EnableValueChangedEvent` (Bu olay için bir animasyon nesnesinde tüm animasyon değişkenleri sağlar).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="onvaluechanged"></a>  CAnimationVariableChangeHandler::OnValueChanged

Bir animasyon değişkeninin bir değeri değiştirildiğinde çağırılır.

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>Parametreler

*görsel taslak*<br/>
Değişken animasyon film şeridi.

*Değişkeni*<br/>
Animasyon değişkenin güncelleştirildi.

*newValue*<br/>
Yeni değeri.

*previousValue*<br/>
Önceki değer.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="setanimationcontroller"></a>  CAnimationVariableChangeHandler::SetAnimationController

Animasyon denetleyicisini rota olaylar için bir işaretçi depolar.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacaksınız animasyon denetleyicisini bir işaretçi.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
