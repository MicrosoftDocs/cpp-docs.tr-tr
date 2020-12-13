---
description: 'Daha fazla bilgi edinin: CAnimationVariableIntegerChangeHandler sınıfı'
title: CAnimationVariableIntegerChangeHandler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableIntegerChangeHandler [MFC], CAnimationVariableIntegerChangeHandler
- CAnimationVariableIntegerChangeHandler [MFC], CreateInstance
- CAnimationVariableIntegerChangeHandler [MFC], OnIntegerValueChanged
- CAnimationVariableIntegerChangeHandler [MFC], SetAnimationController
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
ms.openlocfilehash: 53a0a1838e021294b4ccc870e6f01b873233a0c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336730"
---
# <a name="canimationvariableintegerchangehandler-class"></a>CAnimationVariableIntegerChangeHandler sınıfı

Animasyon değişkeninin değeri değiştiğinde animasyon API 'Sı tarafından çağrılan bir geri çağırma uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler:: CAnimationVariableIntegerChangeHandler](#canimationvariableintegerchangehandler)|Bir `CAnimationVariableIntegerChangeHandler` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler:: CreateInstance](#createinstance)|Geri çağırma örneği oluşturur `CAnimationVariableIntegerChangeHandler` .|
|[CAnimationVariableIntegerChangeHandler:: OnIntegerValueChanged](#onintegervaluechanged)|Bir animasyon değişkeninin değeri değiştiğinde çağırılır. (Geçersiz kılmalar `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged` .)|
|[CAnimationVariableIntegerChangeHandler:: SetAnimationController](#setanimationcontroller)|Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi oluşturulur ve IUIAnimationVariable:: EnableIntegerValueChangedEvent veya CAnimationBaseObject:: EnableIntegerValueChangedEvent çağırdığınızda (bir animasyon nesnesinde kapsüllenmiş tüm animasyon değişkenleri için bu olayı sağlar).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[MFC sınıfları](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationvariableintegerchangehandlercanimationvariableintegerchangehandler"></a><a name="canimationvariableintegerchangehandler"></a> CAnimationVariableIntegerChangeHandler:: CAnimationVariableIntegerChangeHandler

Bir CAnimationVariableIntegerChangeHandler nesnesi oluşturur.

```
CAnimationVariableIntegerChangeHandler ();
```

## <a name="canimationvariableintegerchangehandlercreateinstance"></a><a name="createinstance"></a> CAnimationVariableIntegerChangeHandler:: CreateInstance

CAnimationVariableIntegerChangeHandler geri çağrısının bir örneğini oluşturur.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olay alacak bir animasyon denetleyicisi işaretçisi.

*ppHandler*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="canimationvariableintegerchangehandleronintegervaluechanged"></a><a name="onintegervaluechanged"></a> CAnimationVariableIntegerChangeHandler:: OnIntegerValueChanged

Bir animasyon değişkeninin değeri değiştiğinde çağırılır.

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>Parametreler

*görsel taslak*<br/>
Değişkeni hareketlendirilen film şeridi.

*değişken*<br/>
Güncelleştirilmiş animasyon değişkeni.

*Değer*<br/>
Yeni yuvarlatılmış değer.

*previousValue*<br/>
Önceki yuvarlatılmış değer.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL.

## <a name="canimationvariableintegerchangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationVariableIntegerChangeHandler:: SetAnimationController

Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olay alacak bir animasyon denetleyicisi işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
