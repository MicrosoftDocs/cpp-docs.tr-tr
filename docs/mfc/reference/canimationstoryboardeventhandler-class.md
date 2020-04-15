---
title: CAnimationStoryboardEventHandler Sınıfı
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
ms.openlocfilehash: 36b8b524591693775403d66fdc1f0754aaf67778
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364997"
---
# <a name="canimationstoryboardeventhandler-class"></a>CAnimationStoryboardEventHandler Sınıfı

Bir hikaye şeridinin durumu değiştirildiğinde veya bir film şeridi güncelleştirildiğinde Animasyon API'sı tarafından çağrılan bir geri arama uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|Bir `CAnimationStoryboardEventHandler` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationStoryboardEventHandler::CreateInstance](#createinstance)|Geri `CAnimationStoryboardEventHandler` arama örneği oluşturur.|
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Bir `OnStoryboardStatusChanged` film şeridinin durumu değiştiğinde oluşan olayları işler `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`(Geçersiz kılar.)|
|[CAnimationStoryboardEventHandler::OnStoryboardGüncel](#onstoryboardupdated)|Bir `OnStoryboardUpdated` film şeridi güncelleştirildiğinde oluşan olayları işler `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`(Geçersiz kılar.)|
|[CAnimationStoryboardEventHandler::SetAnimationController](#setanimationcontroller)|Olayları yönlendirmek için animasyon denetleyicisine işaretçi saklar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi `IUIAnimationStoryboard::SetStoryboardEventHandler` oluşturulur ve yönteme geçirilir, ne zaman . `CAnimationController::EnableStoryboardEventHandler`

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationStoryboardEventHandlerBase`

`CAnimationStoryboardEventHandler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationstoryboardeventhandlercanimationstoryboardeventhandler"></a><a name="canimationstoryboardeventhandler"></a>CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler

CAnimationStoryboardEventHandler nesnesi oluşturuyor.

```
CAnimationStoryboardEventHandler();
```

## <a name="canimationstoryboardeventhandlercreateinstance"></a><a name="createinstance"></a>CAnimationStoryboardEventHandler::CreateInstance

CAnimationStoryboardEventHandler geri çağırma bir örneği oluşturur.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationStoryboardEventHandler** ppHandler);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacak animasyon denetleyicisi için bir işaretçi.

*ppHandler*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="canimationstoryboardeventhandleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a>CAnimationStoryboardEventHandler::OnStoryboardStatusChanged

Bir film şeridinin durumu değiştiğinde meydana gelen OnStoryboardStatusChanged olayları işler

```
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Parametreler

*Film şeridi*<br/>
Durumu değişen bir film şeridi için işaretçi.

*newDurum*<br/>
Yeni hikaye şeridi durumunu belirtir.

*öncekiDurum*<br/>
Önceki film şeridi durumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

yöntem başarılı olursa S_OK; aksi takdirde E_FAIL.

## <a name="canimationstoryboardeventhandleronstoryboardupdated"></a><a name="onstoryboardupdated"></a>CAnimationStoryboardEventHandler::OnStoryboardGüncel

Bir film şeridi güncelleştirildiğinde ortaya çıkan OnStoryboardGüncel olayları işler

```
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```

### <a name="parameters"></a>Parametreler

*Film şeridi*<br/>
Güncelleştirilen bir film şeridi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

yöntem başarılı olursa S_OK; aksi takdirde E_FAIL.

## <a name="canimationstoryboardeventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>CAnimationStoryboardEventHandler::SetAnimationController

Olayları yönlendirmek için animasyon denetleyicisine işaretçi saklar.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacak animasyon denetleyicisi için bir işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
