---
title: Canimationvariableıntegerchangehandler sınıfı
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
ms.openlocfilehash: 66d740d7042ed2e19b6fe3a87345d7abb096f12c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449640"
---
# <a name="canimationvariableintegerchangehandler-class"></a>Canimationvariableıntegerchangehandler sınıfı

Animasyon değişkeninin bir değeri değiştiğinde animasyon API'sı tarafından çağrılan bir geri arama gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](#canimationvariableintegerchangehandler)|Oluşturur bir `CAnimationVariableIntegerChangeHandler` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler::CreateInstance](#createinstance)|Örneği oluşturur `CAnimationVariableIntegerChangeHandler` geri çağırma.|
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](#onintegervaluechanged)|Bir animasyon değişkeninin bir değeri değiştirildiğinde çağırılır. (Geçersiz kılmaları `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`.)|
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](#setanimationcontroller)|Animasyon denetleyicisini rota olaylar için bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi oluşturulur ve CAnimationVariable::EnableIntegerValueChangedEvent veya (sağlayan CAnimationBaseObject::EnableIntegerValueChangedEvent çağırdığınızda IUIAnimationVariable::SetVariableIntegerChangeHandler yöntemine geçirilen Bu olay için bir animasyon nesnesinde tüm animasyon değişkenleri).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[MFC Sınıfları](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="canimationvariableintegerchangehandler"></a>  CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler

Canimationvariableıntegerchangehandler bir nesne oluşturur.

```
CAnimationVariableIntegerChangeHandler ();
```

##  <a name="createinstance"></a>  CAnimationVariableIntegerChangeHandler::CreateInstance

Canimationvariableıntegerchangehandler geri çağırma örneği oluşturur.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacaksınız animasyon denetleyicisini bir işaretçi.

*ppHandler*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="onintegervaluechanged"></a>  CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged

Bir animasyon değişkeninin bir değeri değiştirildiğinde çağırılır.

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>Parametreler

*görsel taslak*<br/>
Değişken animasyon film şeridi.

*Değişkeni*<br/>
Animasyon değişkenin güncelleştirildi.

*newValue*<br/>
Yeni yuvarlanan değer.

*previousValue*<br/>
Önceki yuvarlanan değer.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL.

##  <a name="setanimationcontroller"></a>  CAnimationVariableIntegerChangeHandler::SetAnimationController

Animasyon denetleyicisini rota olaylar için bir işaretçi depolar.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacaksınız animasyon denetleyicisini bir işaretçi.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
