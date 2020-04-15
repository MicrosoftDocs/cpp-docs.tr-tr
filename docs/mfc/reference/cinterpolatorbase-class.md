---
title: CInterpolatorBase Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: e5294aabc42301e2f874d5b8328d648f4deeb3c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372363"
---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase Sınıfı

Animasyon değişkeninin yeni bir değerini hesaplaması gerektiğinde Animasyon API'sı tarafından çağrılan bir geri arama uygular.

## <a name="syntax"></a>Sözdizimi

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|Nesneyi `CInterpolatorBase` inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CInterpolatorBase::CreateInstance](#createinstance)|Bir örneğini `CInterpolatorBase` oluşturur ve olayları işleyecek olan özel enterpolatöriçin bir işaretçi depolar.|
|[CInterpolatorBase::GetDependencies](#getdependencies)|Enterpolatörün bağımlılıklarını alır. (Geçersiz `CUIAnimationInterpolatorBase::GetDependencies`kılar .)|
|[CInterpolatorBase::GetDuration](#getduration)|Enterpolatörün süresini alır. (Geçersiz `CUIAnimationInterpolatorBase::GetDuration`kılar .)|
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Enterpolatörün yol açtığı son değeri alır. (Geçersiz `CUIAnimationInterpolatorBase::GetFinalValue`kılar .)|
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Değeri belirli bir ofsetteki enterpolasyonlar (Geçersiz Kılar `CUIAnimationInterpolatorBase::InterpolateValue`.)|
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Hızı belirli bir ofsette interpolates (Overrides `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Olayları işleyen özel enterpolatör için bir işaretçi depolar.|
|[CInterpolatorBase::SetDuration](#setduration)|Enterpolatörün süresini ayarlar (Geçersiz `CUIAnimationInterpolatorBase::SetDuration`kılar.)|
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Enterpolatörün başlangıç değerini ve hızını ayarlar. (Geçersiz `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`kılar .)|

## <a name="remarks"></a>Açıklamalar

Bu işleyici oluşturulur ve `IUIAnimationTransitionFactory::CreateTransition` bir `CCustomTransition` nesne animasyon başlatma işleminin bir parçası olarak `CAnimationController::AnimateGroup`oluşturulur (tarafından başlatılan) geçirilir. Genellikle doğrudan bu sınıfı kullanmak gerekmez, sadece işaretçi sisizin `CCustomInterpolator`oluşturucuya geçirilen bir -türetilmiş sınıf, tüm olayları `CCustomTransition`bozan.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="cinterpolatorbasecinterpolatorbase"></a><a name="cinterpolatorbase"></a>CInterpolatorBase::CInterpolatorBase

CInterpolatorBase nesnesini oluşturuyor.

```
CInterpolatorBase();
```

## <a name="cinterpolatorbasecreateinstance"></a><a name="createinstance"></a>CInterpolatorBase::CreateInstance

CInterpolatorBase bir örnek oluşturur ve olayları işleme olacak özel interpolator, bir işaretçi depolar.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>Parametreler

*pInterpolator*<br/>
Özel enterpolatör için bir işaretçi.

*ppHandler*<br/>
Çıkış. İşlev döndüğünde CInterpolatorBase örneğine işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

## <a name="cinterpolatorbasegetdependencies"></a><a name="getdependencies"></a>CInterpolatorBase::GetDependencies

Enterpolatörün bağımlılıklarını alır.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parametreler

*ilkDeğer Bağımlılıkları*<br/>
Çıkış. Enterpolatörün setinitialvalueAndVelocity geçirilen ilk değere bağlı yönleri.

*ilkVelocityDependencies*<br/>
Çıkış. İlk hıza bağlı olarak interpolatörün yönleri SetInitialValueAndVelocity'ye geçer.

*süreBağımlılıklar*<br/>
Çıkış. İnterpolatörün SetDuration'e geçirilen süreye bağlı yönleri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. CCustomInterpolator ayarlanmazsa veya özel uygulama GetDependencies yönteminden FALSE döndürür saE_FAIL döndürür.

## <a name="cinterpolatorbasegetduration"></a><a name="getduration"></a>CInterpolatorBase::GetDuration

Enterpolatörün süresini alır.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Çıkış. Geçiş süresi, saniye cinsinden.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. CCustomInterpolator ayarlanmazsa veya özel uygulama GetDuration yönteminden FALSE döndürürse E_FAIL döndürür.

## <a name="cinterpolatorbasegetfinalvalue"></a><a name="getfinalvalue"></a>CInterpolatorBase::GetFinalValue

Enterpolatörün yol açtığı son değeri alır.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Çıkış. Geçiş sonundaki değişkenin son değeri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. CCustomInterpolator ayarlanmazsa veya özel uygulama GetFinalValue yönteminden FALSE döndürürse E_FAIL döndürür.

## <a name="cinterpolatorbaseinterpolatevalue"></a><a name="interpolatevalue"></a>CInterpolatorBase::InterpolateValue

Değeri belirli bir ofsette interpolates

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*Uzaklık*<br/>
Geçişin başlangıcından itibaren mahsup. Ofset her zaman sıfırdan büyük veya eşit ve geçiş süresinden daha azdır. Geçiş süresi sıfır ise bu yöntem çağrılmaz.

*Değer*<br/>
Çıkış. İnterpolated değeri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. CCustomInterpolator ayarlanmazsa veya özel uygulama InterpolateValue yönteminden FALSE döndürürse E_FAIL döndürür.

## <a name="cinterpolatorbaseinterpolatevelocity"></a><a name="interpolatevelocity"></a>CInterpolatorBase::InterpolateVelocity

Hızı belirli bir ofsette interpolates

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>Parametreler

*Uzaklık*<br/>
Geçişin başlangıcından itibaren mahsup. Ofset her zaman sıfırdan büyük veya eşit ve geçiş süresinden daha az veya eşittir. Geçiş süresi sıfır ise bu yöntem çağrılmaz.

*Hız*<br/>
Çıkış. Dengedeki değişkenin hızı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. CCustomInterpolator ayarlanmazveya özel uygulama InterpolateVelocity yönteminden FALSE döndürür E_FAIL döndürür.

## <a name="cinterpolatorbasesetcustominterpolator"></a><a name="setcustominterpolator"></a>CInterpolatorBase::SetCustomInterpolator

Olayları işleyen özel enterpolatör için bir işaretçi depolar.

```
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parametreler

*pInterpolator*<br/>
Özel enterpolatör için bir işaretçi.

## <a name="cinterpolatorbasesetduration"></a><a name="setduration"></a>CInterpolatorBase::SetDuration

Enterpolatörün süresini ayarlar

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Geçiş süresi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. CCustomInterpolator ayarlanmazsa veya özel uygulama SetDuration yönteminden FALSE döndürürse E_FAIL döndürür.

## <a name="cinterpolatorbasesetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a>CInterpolatorBase::SetInitialValueAndVelocity

Enterpolatörün başlangıç değerini ve hızını ayarlar.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametreler

*ınitialvalue*<br/>
Geçişin başındaki değişkenin değeri.

*ilkHız*<br/>
Geçişin başlangıcındaki değişkenin hızı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. CCustomInterpolator ayarlanmazsa veya özel uygulama SetInitialValueAndVelocity yönteminden FALSE döndürür saE_FAIL döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
