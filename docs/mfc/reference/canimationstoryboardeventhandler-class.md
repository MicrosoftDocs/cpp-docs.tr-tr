---
description: 'Daha fazla bilgi edinin: CAnimationStoryboardEventHandler Class'
title: CAnimationStoryboardEventHandler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
ms.openlocfilehash: 7208ba91ec78a6de688699183b55a691b8e3d28d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254748"
---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler sınıfı

Film şeridinin durumu değiştirildiğinde veya bir görsel taslak güncelleştirilirken animasyon API 'Sı tarafından çağrılan bir geri çağırma uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|Bir `CAnimationStoryboardEventHandler` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationStoryboardEventHandler:: CreateInstance](#createinstance)|Geri çağırma örneği oluşturur `CAnimationStoryboardEventHandler` .|
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|`OnStoryboardStatusChanged`Bir görsel taslak durumu değiştiğinde oluşan olayları işler (geçersiz kılmalar `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged` .)|
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](#onstoryboardupdated)|`OnStoryboardUpdated`Film şeridi güncelleştirilirken oluşan olayları işler (geçersiz kılmalar `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated` .)|
|[CAnimationStoryboardEventHandler:: SetAnimationController](#setanimationcontroller)|Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi `IUIAnimationStoryboard::SetStoryboardEventHandler` , öğesini çağırdığınızda oluşturulur ve yöntemine geçirilir `CAnimationController::EnableStoryboardEventHandler` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationStoryboardEventHandlerBase`

`CAnimationStoryboardEventHandler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationstoryboardeventhandlercanimationstoryboardeventhandler"></a><a name="canimationstoryboardeventhandler"></a> CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler

Bir CAnimationStoryboardEventHandler nesnesi oluşturur.

```
CAnimationStoryboardEventHandler();
```

## <a name="canimationstoryboardeventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationStoryboardEventHandler:: CreateInstance

CAnimationStoryboardEventHandler geri çağrısının bir örneğini oluşturur.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationStoryboardEventHandler** ppHandler);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olay alacak bir animasyon denetleyicisi işaretçisi.

*ppHandler*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="canimationstoryboardeventhandleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a> CAnimationStoryboardEventHandler::OnStoryboardStatusChanged

Film şeridinin durumu değiştiğinde oluşan OnStoryboardStatusChanged olaylarını işler

```
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Parametreler

*görsel taslak*<br/>
Bir film şeridi için durumu değişmiş olan bir işaretçi.

*newStatus*<br/>
Yeni görsel taslak durumunu belirtir.

*previousStatus*<br/>
Önceki görsel taslak durumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL.

## <a name="canimationstoryboardeventhandleronstoryboardupdated"></a><a name="onstoryboardupdated"></a> CAnimationStoryboardEventHandler::OnStoryboardUpdated

Bir film şeridi güncelleştirilirken oluşan OnStoryboardUpdated olaylarını işler

```
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```

### <a name="parameters"></a>Parametreler

*görsel taslak*<br/>
Görsel taslağa yönelik bir işaretçi güncelleştirildi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL.

## <a name="canimationstoryboardeventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationStoryboardEventHandler:: SetAnimationController

Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olay alacak bir animasyon denetleyicisi işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
