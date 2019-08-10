---
title: Centerpolatorbase sınıfı
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
ms.openlocfilehash: d1fc675b1014ab9a099e8310b52b7458f2bff65f
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916211"
---
# <a name="cinterpolatorbase-class"></a>Centerpolatorbase sınıfı

Animasyon değişkeninin yeni bir değerini hesaplamak zorunda olduğunda animasyon API 'SI tarafından çağrılan bir geri çağırma uygular.

## <a name="syntax"></a>Sözdizimi

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Centerpolatorbase:: Centerpolatorbase](#cinterpolatorbase)|`CInterpolatorBase` Nesnesini oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Centerpolatorbase:: CreateInstance](#createinstance)|Bir örneği `CInterpolatorBase` oluşturur ve olayları işlemek için özel bir ara değer için bir işaretçi depolar.|
|[Centerpolatorbase:: GetDependencies](#getdependencies)|Enterpolatörü 'nin bağımlılıklarını alır. (Geçersiz `CUIAnimationInterpolatorBase::GetDependencies`kılmalar.)|
|[Centerpolatorbase:: GetDuration](#getduration)|Enterpolatör 'ın süresini alır. (Geçersiz `CUIAnimationInterpolatorBase::GetDuration`kılmalar.)|
|[Centerpolatorbase:: GetFinalValue](#getfinalvalue)|Enterpolatörü 'nin müşteri adaylarına son değeri alır. (Geçersiz `CUIAnimationInterpolatorBase::GetFinalValue`kılmalar.)|
|[Centerpolatorbase:: Enterpolatevalue](#interpolatevalue)|Verilen bir uzaklığında değeri enterpolasyonlar (geçersiz kılmalar `CUIAnimationInterpolatorBase::InterpolateValue`.)|
|[Centerpolatorbase:: Enterpolatevelocity](#interpolatevelocity)|Verilen bir uzaklığa göre hızı enterpolasyonlar (geçersiz `CUIAnimationInterpolatorBase::InterpolateVelocity`kılmalar.)|
|[Centerpolatorbase:: Setcustominterpolatör](#setcustominterpolator)|Olayları işlemek için özel bir ara değer denetimi için bir işaretçi depolar.|
|[Centerpolatorbase:: SetDuration](#setduration)|Enterpolatör 'ın süresini (geçersiz kılmalar `CUIAnimationInterpolatorBase::SetDuration`) ayarlar.|
|[Centerpolatorbase:: SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Enterpolatör 'un ilk değerini ve hızını ayarlar. (Geçersiz `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`kılmalar.)|

## <a name="remarks"></a>Açıklamalar

Bu işleyici oluşturulur ve animasyon başlatma işleminin `IUIAnimationTransitionFactory::CreateTransition` (tarafından `CCustomTransition` `CAnimationController::AnimateGroup`başlatılan) bir parçası olarak bir nesne oluşturulduğunda öğesine geçirilir. Genellikle, bu sınıfı doğrudan kullanmanız gerekmez, işaretçi `CCustomInterpolator` `CCustomTransition`oluşturucuya geçilen tüm olayları yalnızca türetilmiş bir sınıfa döner.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

##  <a name="cinterpolatorbase"></a>Centerpolatorbase:: Centerpolatorbase

Cınterlatorbase nesnesini oluşturur.

```
CInterpolatorBase();
```

##  <a name="createinstance"></a>Centerpolatorbase:: CreateInstance

Cınterlatorbase 'in bir örneğini oluşturur ve olayları işlemek için özel bir ara değer atma için bir işaretçi depolar.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>Parametreler

*Ince merdiven*<br/>
Özel enterpolatörü işaretçisi.

*ppHandler*<br/>
Çıktıların. İşlev döndürüldüğünde CInterpolatorBase örneğine yönelik bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

##  <a name="getdependencies"></a>Centerpolatorbase:: GetDependencies

Enterpolatörü 'nin bağımlılıklarını alır.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parametreler

*ınitialvaluedependencies*<br/>
Çıktıların. SetInitialValueAndVelocity öğesine geçirilen ilk değere bağlı olan ara değer ayırmanın yönleri.

*initialVelocityDependencies*<br/>
Çıktıların. SetInitialValueAndVelocity öğesine geçirilen ilk hıza bağlı olan ara değer ayırmanın yönleri.

*durationDependencies*<br/>
Çıktıların. SetDuration 'a geçirilen süreye bağlı olan ara değer ayırmanın yönleri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustominterpolatör ayarlanmamışsa, veya özel uygulama GetDependencies yönteminden FALSE değerini döndürürse E_FAıL 'yi döndürür.

##  <a name="getduration"></a>Centerpolatorbase:: GetDuration

Enterpolatör 'ın süresini alır.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Çıktıların. Geçişin süresi (saniye cinsinden).

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustominterpolatör ayarlanmamışsa veya özel uygulama GetDuration yönteminden FALSE değerini döndürürse E_FAıL 'yi döndürür.

##  <a name="getfinalvalue"></a>Centerpolatorbase:: GetFinalValue

Enterpolatörü 'nin müşteri adaylarına son değeri alır.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Çıktıların. Geçişin sonundaki bir değişkenin son değeri.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustominterpolatör ayarlanmamışsa, veya özel uygulama GetFinalValue yönteminden FALSE değerini döndürürse E_FAıL 'yi döndürür.

##  <a name="interpolatevalue"></a>Centerpolatorbase:: Enterpolatevalue

Verilen bir uzaklığında değeri enterpolasyonlar

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*konumu*<br/>
Geçişin başlangıcından itibaren fark. Konum her zaman sıfıra eşit veya daha büyük ve geçiş süresinden küçüktür. Bu yöntem, geçişin süresi sıfırsa çağrılmaz.

*value*<br/>
Çıktıların. Enterpolasyonlu değer.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustominterpolatör ayarlanmamışsa veya özel uygulama, Enterpolatevalue yönteminden yanlış döndürürse, E_FAıL değerini döndürür.

##  <a name="interpolatevelocity"></a>Centerpolatorbase:: Enterpolatevelocity

Verilen bir uzaklığa göre hızı enterpolasyonlar

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>Parametreler

*konumu*<br/>
Geçişin başlangıcından itibaren fark. Konum her zaman sıfıra eşit veya daha büyük ve geçişin süresinden küçük ya da buna eşit. Bu yöntem, geçişin süresi sıfırsa çağrılmaz.

*mı*<br/>
Çıktıların. Uzaklığında değişkenin hızı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustominterpolatör ayarlanmamışsa veya özel uygulama, Enterpolatevelocity yönteminden yanlış döndürürse, E_FAıL değerini döndürür.

##  <a name="setcustominterpolator"></a>Centerpolatorbase:: Setcustominterpolatör

Olayları işlemek için özel bir ara değer denetimi için bir işaretçi depolar.

```
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parametreler

*Ince merdiven*<br/>
Özel enterpolatörü işaretçisi.

##  <a name="setduration"></a>Centerpolatorbase:: SetDuration

Enterpolatör 'ın süresini ayarlar

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Geçişin süresi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustominterpolatör ayarlanmamışsa veya özel uygulama SetDuration yönteminden FALSE değerini döndürürse E_FAıL 'yi döndürür.

##  <a name="setinitialvalueandvelocity"></a>Centerpolatorbase:: SetInitialValueAndVelocity

Enterpolatör 'un ilk değerini ve hızını ayarlar.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametreler

*InitialValue*<br/>
Geçişin başlangıcında değişkenin değeri.

*InitialVelocity*<br/>
Geçişin başlangıcında değişkenin hızı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Ccustominterpolatör ayarlanmamışsa veya özel uygulama SetInitialValueAndVelocity yönteminden FALSE döndürürse, E_FAıL değerini döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
