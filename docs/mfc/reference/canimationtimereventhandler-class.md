---
description: 'Daha fazla bilgi edinin: CAnimationTimerEventHandler sınıfı'
title: CAnimationTimerEventHandler sınıfı
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
ms.openlocfilehash: 5d5f3e07eeb7ffe3f3bb226afd566330808303ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336755"
---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler sınıfı

, Zamanlama olayları gerçekleştiğinde animasyon API 'Sı tarafından çağrılan bir geri çağırma uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationTimerEventHandler:: CreateInstance](#createinstance)|Geri çağırma örneği oluşturur `CAnimationTimerEventHandler` .|
|[CAnimationTimerEventHandler:: OnPostUpdate](#onpostupdate)|Bir animasyon güncelleştirmesi tamamlandıktan sonra oluşan olayları işler. (Geçersiz kılmalar `CUIAnimationTimerEventHandlerBase::OnPostUpdate` .)|
|[CAnimationTimerEventHandler:: OnPreUpdate](#onpreupdate)|Animasyon güncelleştirme başlamadan önce oluşan olayları işler. (Geçersiz kılmalar `CUIAnimationTimerEventHandlerBase::OnPreUpdate` .)|
|[CAnimationTimerEventHandler:: Onrenderingtoolow](#onrenderingtooslow)|Bir animasyonun işleme çerçevesi oranı, istenen en düşük kare hızının altına düştüğünde oluşan olayları işler. (Geçersiz kılmalar `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow` .)|
|[CAnimationTimerEventHandler:: SetAnimationController](#setanimationcontroller)|Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi oluşturulur ve CAnimationController:: EnableAnimationTimerEventHandler öğesini çağırdığınızda IUIAnimationTimer:: SetTimerEventHandler öğesine geçirilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationtimereventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationTimerEventHandler:: CreateInstance

CAnimationTimerEventHandler geri çağrısının bir örneğini oluşturur.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olay alacak bir animasyon denetleyicisi işaretçisi.

*ppTimerEventHandler*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="canimationtimereventhandleronpostupdate"></a><a name="onpostupdate"></a> CAnimationTimerEventHandler:: OnPostUpdate

Bir animasyon güncelleştirmesi tamamlandıktan sonra oluşan olayları işler.

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL.

## <a name="canimationtimereventhandleronpreupdate"></a><a name="onpreupdate"></a> CAnimationTimerEventHandler:: OnPreUpdate

Animasyon güncelleştirme başlamadan önce oluşan olayları işler.

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL.

## <a name="canimationtimereventhandleronrenderingtooslow"></a><a name="onrenderingtooslow"></a> CAnimationTimerEventHandler:: Onrenderingtoolow

Bir animasyonun işleme çerçevesi oranı, istenen en düşük kare hızının altına düştüğünde oluşan olayları işler.

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>Parametreler

*fps*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL.

## <a name="canimationtimereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationTimerEventHandler:: SetAnimationController

Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olay alacak bir animasyon denetleyicisi işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
