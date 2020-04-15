---
title: CAnimationTimerEventHandler Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
ms.openlocfilehash: 72b6e5d8d9d4823795a1fb053c5f2374cb80fba4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320008"
---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler Sınıfı

Zamanlama olayları oluştuğunda Animasyon API'sı tarafından çağrılan bir geri arama uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|Geri `CAnimationTimerEventHandler` arama örneği oluşturur.|
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|Animasyon güncelleştirmesi tamamlandıktan sonra oluşan olayları işler. (Geçersiz `CUIAnimationTimerEventHandlerBase::OnPostUpdate`kılar .)|
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|Animasyon güncelleştirmesi başlamadan önce meydana gelen olayları işler. (Geçersiz `CUIAnimationTimerEventHandlerBase::OnPreUpdate`kılar .)|
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|Animasyonun oluşturma kare hızı minimum istenen kare hızının altına düştüğünde oluşan olayları işler. (Geçersiz `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`kılar .)|
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|Olayları yönlendirmek için animasyon denetleyicisine işaretçi saklar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi oluşturulur ve IUIAnimationTimer geçirilir::SetTimerEventHandler cAnimationController::EnableAnimationTimerEventHandler çağırdığınızda.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationtimereventhandlercreateinstance"></a><a name="createinstance"></a>CAnimationTimerEventHandler::CreateInstance

CAnimationTimerEventHandler geri çağırma örneği oluşturur.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacak animasyon denetleyicisi için bir işaretçi.

*ppTimerEventHandler*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="canimationtimereventhandleronpostupdate"></a><a name="onpostupdate"></a>CAnimationTimerEventHandler::OnPostUpdate

Animasyon güncelleştirmesi tamamlandıktan sonra oluşan olayları işler.

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>Dönüş Değeri

yöntem başarılı olursa S_OK; aksi takdirde E_FAIL.

## <a name="canimationtimereventhandleronpreupdate"></a><a name="onpreupdate"></a>CAnimationTimerEventHandler::OnPreUpdate

Animasyon güncelleştirmesi başlamadan önce meydana gelen olayları işler.

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>Dönüş Değeri

yöntem başarılı olursa S_OK; aksi takdirde E_FAIL.

## <a name="canimationtimereventhandleronrenderingtooslow"></a><a name="onrenderingtooslow"></a>CAnimationTimerEventHandler::OnRenderingTooSlow

Animasyonun oluşturma kare hızı minimum istenen kare hızının altına düştüğünde oluşan olayları işler.

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>Parametreler

*Fps*

### <a name="return-value"></a>Dönüş Değeri

yöntem başarılı olursa S_OK; aksi takdirde E_FAIL.

## <a name="canimationtimereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>CAnimationTimerEventHandler::SetAnimationController

Olayları yönlendirmek için animasyon denetleyicisine işaretçi saklar.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacak animasyon denetleyicisi için bir işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
