---
description: 'Daha fazla bilgi edinin: CAnimationManagerEventHandler sınıfı'
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
ms.openlocfilehash: aab944c23822486bbc04bb7710d257dd8c42beed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207952"
---
# <a name="canimationmanagereventhandler-class"></a>CAnimationManagerEventHandler sınıfı

, Bir animasyon yöneticisinin durumu değiştirildiğinde animasyon API 'Sı tarafından çağrılan bir geri çağırma uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationManagerEventHandler:: CAnimationManagerEventHandler](#canimationmanagereventhandler)|Bir `CAnimationManagerEventHandler` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationManagerEventHandler:: CreateInstance](#createinstance)|Nesnesinin bir örneğini oluşturur `CAnimationManagerEventHandler` .|
|[CAnimationManagerEventHandler:: OnManagerStatusChanged](#onmanagerstatuschanged)|Animasyon Yöneticisi durumu değiştiğinde çağırılır. (Geçersiz kılmalar `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged` .)|
|[CAnimationManagerEventHandler:: SetAnimationController](#setanimationcontroller)|Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu olay işleyicisi oluşturulur ve CAnimationController:: EnableAnimationManagerEvent öğesini çağırdığınızda IUIAnimationManager:: SetManagerEventHandler yöntemine geçirilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationmanagereventhandlercanimationmanagereventhandler"></a><a name="canimationmanagereventhandler"></a> CAnimationManagerEventHandler:: CAnimationManagerEventHandler

Visual Studio 2010 SP1 gereklidir.

Bir CAnimationManagerEventHandler nesnesi oluşturur.

```
CAnimationManagerEventHandler();
```

## <a name="canimationmanagereventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationManagerEventHandler:: CreateInstance

Visual Studio 2010 SP1 gereklidir.

CAnimationManagerEventHandler nesnesinin bir örneğini oluşturur.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olay alacak bir animasyon denetleyicisi işaretçisi.

*ppManagerEventHandler*<br/>
Çıktıların. Yöntem başarılı olursa, bir animasyon yöneticisinin durum güncelleştirmelerini işleyecek COM nesnesine bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="canimationmanagereventhandleronmanagerstatuschanged"></a><a name="onmanagerstatuschanged"></a> CAnimationManagerEventHandler:: OnManagerStatusChanged

Visual Studio 2010 SP1 gereklidir.

Animasyon Yöneticisi durumu değiştiğinde çağırılır.

```
IFACEMETHOD(OnManagerStatusChanged)(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Parametreler

*newStatus*<br/>
Yeni durum.

*previousStatus*<br/>
Önceki durum.

### <a name="return-value"></a>Dönüş Değeri

Geçerli uygulama her zaman S_OK döndürür;

## <a name="canimationmanagereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationManagerEventHandler:: SetAnimationController

Visual Studio 2010 SP1 gereklidir.

Olayları yönlendirmek için animasyon denetleyicisine bir işaretçi depolar.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametreler

*pAnimationController*<br/>
Olay alacak bir animasyon denetleyicisi işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
