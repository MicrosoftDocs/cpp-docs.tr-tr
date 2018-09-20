---
title: Cınterpolatorbase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
dev_langs:
- C++
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5287c54aad0a4ec41145f8241123489ea74d19f7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407917"
---
# <a name="cinterpolatorbase-class"></a>Cınterpolatorbase sınıfı

Bunu animasyon değişkenin yeni değerini hesaplamak zorunda kaldığında animasyon API'sı tarafından çağrılan bir geri arama gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|Yapıları `CInterpolatorBase` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CInterpolatorBase::CreateInstance](#createinstance)|Örneği oluşturur `CInterpolatorBase` ve olayları işleme özel bir ara bir işaretçi depolar.|
|[CInterpolatorBase::GetDependencies](#getdependencies)|Bir Ara'nın bağımlılıkları alır. (Geçersiz kılmaları `CUIAnimationInterpolatorBase::GetDependencies`.)|
|[CInterpolatorBase::GetDuration](#getduration)|Bir Ara'nın süresi alır. (Geçersiz kılmaları `CUIAnimationInterpolatorBase::GetDuration`.)|
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Ara değer hesaplayıcı, müşteri adayları son değerini alır. (Geçersiz kılmaları `CUIAnimationInterpolatorBase::GetFinalValue`.)|
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Belirtilen bir uzaklık değeri ilişkilendirir (geçersiz kılmaları `CUIAnimationInterpolatorBase::InterpolateValue`.)|
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Belirtilen bir uzaklık hız ilişkilendirir (geçersiz kılmaları `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Olayları işleme özel bir ara bir işaretçi depolar.|
|[CInterpolatorBase::SetDuration](#setduration)|Bir Ara'nın süresi ayarlar (geçersiz kılmaları `CUIAnimationInterpolatorBase::SetDuration`.)|
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Bir Ara'nın ilk değer ve hız ayarlar. (Geçersiz kılmaları `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|

## <a name="remarks"></a>Açıklamalar

Bu işleyici oluşturulur ve geçirilen `IUIAnimationTransitionFactory::CreateTransition` olduğunda bir `CCustomTransition` nesne animasyon başlatma işleminin bir parçası olarak oluşturuluyor (başlatan `CAnimationController::AnimateGroup`). Genellikle doğrudan bu sınıfı kullanmanız gerekmez, hemen tüm olaylara routs bir `CCustomInterpolator`-türetilmiş sınıf, işaretçi oluşturucusuna geçirilen, `CCustomTransition`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="cinterpolatorbase"></a>  CInterpolatorBase::CInterpolatorBase

Cınterpolatorbase nesnesi oluşturur.

```
CInterpolatorBase();
```

##  <a name="createinstance"></a>  CInterpolatorBase::CreateInstance

Cınterpolatorbase örneği oluşturur ve olayları işleme özel bir ara bir işaretçi depolar.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>Parametreler

*pInterpolator*<br/>
Özel bir ara bir işaretçi.

*ppHandler*<br/>
Çıktı. İşlevi döndüğünde Cınterpolatorbase örneğine bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

##  <a name="getdependencies"></a>  CInterpolatorBase::GetDependencies

Bir Ara'nın bağımlılıkları alır.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parametreler

*initialValueDependencies*<br/>
Çıktı. Başlangıç değerine bağımlı bir ara yönleri için SetInitialValueAndVelocity geçirildi.

*initialVelocityDependencies*<br/>
Çıktı. Başlangıç hızı üzerinde bağımlı bir ara yönleri için SetInitialValueAndVelocity geçirildi.

*durationDependencies*<br/>
Çıktı. Ara değer hesaplayıcı süresine bağlıdır yönleri için SetDuration geçirildi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustomınterpolator ayarlı değil veya özel uygulama GetDependencies yöntemi false değerini döndürür, E_FAIL döndürür.

##  <a name="getduration"></a>  CInterpolatorBase::GetDuration

Bir Ara'nın süresi alır.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Çıktı. Saniye cinsinden geçiş süresi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustomınterpolator ayarlı değil veya özel uygulama GetDuration yöntemi false değerini döndürür, E_FAIL döndürür.

##  <a name="getfinalvalue"></a>  CInterpolatorBase::GetFinalValue

Ara değer hesaplayıcı, müşteri adayları son değerini alır.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Çıktı. Bir değişken geçiş sonunda son değeri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustomınterpolator ayarlı değil veya özel uygulama GetFinalValue yöntemi false değerini döndürür, E_FAIL döndürür.

##  <a name="interpolatevalue"></a>  CInterpolatorBase::InterpolateValue

Belirtilen bir uzaklık değeri ilişkilendirir

```
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*uzaklık*<br/>
Geçiş başından uzaklığı. Uzaklık her zaman değerinden büyük veya sıfıra eşit ve geçiş süresinden daha az. Bu yöntem, geçiş süresini sıfır ise çağrılmaz.

*value*<br/>
Çıktı. İlişkilendirilmiş değer.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustomınterpolator ayarlı değil veya özel uygulama InterpolateValue yöntemi false değerini döndürür, E_FAIL döndürür.

##  <a name="interpolatevelocity"></a>  CInterpolatorBase::InterpolateVelocity

Belirtilen bir uzaklık hız ilişkilendirir

```
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```

### <a name="parameters"></a>Parametreler

*uzaklık*<br/>
Geçiş başından uzaklığı. Uzaklık her zaman büyük veya sıfıra eşit ve geçiş süresini küçüktür veya eşittir. Bu yöntem, geçiş süresini sıfır ise çağrılmaz.

*Hız*<br/>
Çıktı. Değişkenin uzaklığında hız.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustomınterpolator ayarlı değil veya özel uygulama InterpolateVelocity yöntemi false değerini döndürür, E_FAIL döndürür.

##  <a name="setcustominterpolator"></a>  CInterpolatorBase::SetCustomInterpolator

Olayları işleme özel bir ara bir işaretçi depolar.

```
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parametreler

*pInterpolator*<br/>
Özel bir ara bir işaretçi.

##  <a name="setduration"></a>  CInterpolatorBase::SetDuration

Bir Ara'nın süresi ayarlar

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Geçiş süresi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustomınterpolator ayarlı değil veya özel uygulama SetDuration yöntemi false değerini döndürür, E_FAIL döndürür.

##  <a name="setinitialvalueandvelocity"></a>  CInterpolatorBase::SetInitialValueAndVelocity

Bir Ara'nın ilk değer ve hız ayarlar.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue,
  __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametreler

*initialValue*<br/>
Geçiş başlangıcında değişkeninin değeri.

*initialVelocity*<br/>
Geçiş başlangıcında değişkenin hız.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustomınterpolator ayarlı değil veya özel uygulama SetInitialValueAndVelocity yöntemi false değerini döndürür, E_FAIL döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
