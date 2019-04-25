---
title: CAnimationManagerEventHandler Class
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
ms.openlocfilehash: 6661da55d1091394cff9db4589bc05c721b5ab7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151235"
---
# <a name="canimationmanagereventhandler-class"></a>CAnimationManagerEventHandler Class

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

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
