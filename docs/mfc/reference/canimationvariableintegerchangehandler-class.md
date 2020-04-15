---
title: CAnimationVariableIntegerChangeHandler Sınıfı
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
ms.openlocfilehash: 261f8eb17953c047fcc8ec05ae48dc369de4614c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377033"
---
# <a name="canimationvariableintegerchangehandler-class"></a>CAnimationVariableIntegerChangeHandler Sınıfı

Animasyon değişkeninin değeri değiştiğinde Animasyon API'si tarafından çağrılan bir geri arama uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](#canimationvariableintegerchangehandler)|Bir `CAnimationVariableIntegerChangeHandler` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler::CreateInstance](#createinstance)|Geri `CAnimationVariableIntegerChangeHandler` arama örneği oluşturur.|
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](#onintegervaluechanged)|Animasyon değişkeninin değeri değiştiğinde çağrılır. (Geçersiz `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`kılar .)|
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](#setanimationcontroller)|Olayları yönlendirmek için animasyon denetleyicisine işaretçi saklar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi oluşturulur ve IUIAnimationVariable geçirilir::SetVariableIntegerChangeHandler yöntemi, CAnimationVariable::EnableIntegerValueChangedEvent veya CAnimationBaseObject::EnableIntegerValueChangedEvent (bir animasyon nesnesi içinde kapsüllenmiş tüm animasyon değişkenleri için bu olayı sağlar) çağırdığınızda.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[MFC Sınıfları](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationvariableintegerchangehandlercanimationvariableintegerchangehandler"></a><a name="canimationvariableintegerchangehandler"></a>CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler

CAnimationVariableIntegerChangeHandler nesnesi oluşturuyor.

```
CAnimationVariableIntegerChangeHandler ();
```

## <a name="canimationvariableintegerchangehandlercreateinstance"></a><a name="createinstance"></a>CAnimationVariableIntegerChangeHandler::CreateInstance

CAnimationVariableIntegerChangeHandler geri çağırma bir örneği oluşturur.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacak animasyon denetleyicisi için bir işaretçi.

*ppHandler*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="canimationvariableintegerchangehandleronintegervaluechanged"></a><a name="onintegervaluechanged"></a>CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged

Animasyon değişkeninin değeri değiştiğinde çağrılır.

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>Parametreler

*Film şeridi*<br/>
Değişkeni animateden hikaye tahtası.

*Değişken*<br/>
Güncelleştirilen animasyon değişkeni.

*Newvalue*<br/>
Yeni yuvarlatılmış değer.

*öncekiDeğer*<br/>
Önceki yuvarlatılmış değer.

### <a name="return-value"></a>Dönüş Değeri

yöntem başarılı olursa S_OK; aksi takdirde E_FAIL.

## <a name="canimationvariableintegerchangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>CAnimationVariableIntegerChangeHandler::SetAnimationController

Olayları yönlendirmek için animasyon denetleyicisine işaretçi saklar.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacak animasyon denetleyicisi için bir işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
