---
title: CAnimationManagerEventHandler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::OnManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationManagerEventHandler [MFC], CAnimationManagerEventHandler
- CAnimationManagerEventHandler [MFC], CreateInstance
- CAnimationManagerEventHandler [MFC], OnManagerStatusChanged
- CAnimationManagerEventHandler [MFC], SetAnimationController
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
ms.openlocfilehash: 497b6e0f5bdeb817eccb0bb42f66763a97da2af0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445740"
---
# <a name="canimationmanagereventhandler-class"></a>CAnimationManagerEventHandler sınıfı

Animasyon yöneticisinin durumu değiştirildiğinde animasyon API'sı tarafından çağrılan bir geri arama gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](#canimationmanagereventhandler)|Oluşturur bir `CAnimationManagerEventHandler` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationManagerEventHandler::CreateInstance](#createinstance)|Örneği oluşturur `CAnimationManagerEventHandler` nesne.|
|[CAnimationManagerEventHandler::OnManagerStatusChanged](#onmanagerstatuschanged)|Animasyon yöneticisinin durumu değiştirildiğinde çağrılır. (Geçersiz kılmaları `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`.)|
|[CAnimationManagerEventHandler::SetAnimationController](#setanimationcontroller)|Animasyon denetleyicisini rota olaylar için bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi oluşturulur ve CAnimationController::EnableAnimationManagerEvent çağırdığınızda IUIAnimationManager::SetManagerEventHandler yöntemine geçirilen.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="canimationmanagereventhandler"></a>  CAnimationManagerEventHandler::CAnimationManagerEventHandler

Visual Studio 2010 SP1 gereklidir.

CAnimationManagerEventHandler bir nesne oluşturur.

```
CAnimationManagerEventHandler();
```

##  <a name="createinstance"></a>  CAnimationManagerEventHandler::CreateInstance

Visual Studio 2010 SP1 gereklidir.

CAnimationManagerEventHandler nesnesinin örneğini oluşturur.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacaksınız animasyon denetleyicisini bir işaretçi.

*ppManagerEventHandler*<br/>
Çıktı. Yöntem başarılı olursa durum güncelleştirmeleri için animasyon yöneticisinin işleyecek bir COM nesnesine bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="onmanagerstatuschanged"></a>  CAnimationManagerEventHandler::OnManagerStatusChanged

Visual Studio 2010 SP1 gereklidir.

Animasyon yöneticisinin durumu değiştirildiğinde çağrılır.

```
IFACEMETHOD(OnManagerStatusChanged)(
  UI_ANIMATION_MANAGER_STATUS newStatus,
  UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Parametreler

*newStatus*<br/>
Yeni durum.

*previousStatus*<br/>
Önceki durumu.

### <a name="return-value"></a>Dönüş Değeri

Her zaman geçerli uygulama S_OK döndürür;

##  <a name="setanimationcontroller"></a>  CAnimationManagerEventHandler::SetAnimationController

Visual Studio 2010 SP1 gereklidir.

Animasyon denetleyicisini rota olaylar için bir işaretçi depolar.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olayları alacaksınız animasyon denetleyicisini bir işaretçi.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
