---
description: 'Daha fazla bilgi edinin: Ccustominterpolatör sınıfı'
title: Ccustominterpolatör sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
helpviewer_keywords:
- CCustomInterpolator [MFC], CCustomInterpolator
- CCustomInterpolator [MFC], GetDependencies
- CCustomInterpolator [MFC], GetDuration
- CCustomInterpolator [MFC], GetFinalValue
- CCustomInterpolator [MFC], Init
- CCustomInterpolator [MFC], InterpolateValue
- CCustomInterpolator [MFC], InterpolateVelocity
- CCustomInterpolator [MFC], SetDuration
- CCustomInterpolator [MFC], SetInitialValueAndVelocity
- CCustomInterpolator [MFC], m_currentValue
- CCustomInterpolator [MFC], m_currentVelocity
- CCustomInterpolator [MFC], m_duration
- CCustomInterpolator [MFC], m_finalValue
- CCustomInterpolator [MFC], m_initialValue
- CCustomInterpolator [MFC], m_initialVelocity
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
ms.openlocfilehash: 84fcdc20ce1a90441a508f1469d498095980af83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227760"
---
# <a name="ccustominterpolator-class"></a>Ccustominterpolatör sınıfı

Temel bir enterpolatör uygular.

## <a name="syntax"></a>Syntax

```
class CCustomInterpolator;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Ccustominterpolatör:: Ccustominterpolatör](#ccustominterpolator)|Fazla Yüklendi. Özel bir enterpolatör nesnesi oluşturur ve belirtilen değerlere süreyi ve hızı başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ccustominterpolatör:: GetDependencies](#getdependencies)|Enterpolatörü 'nin bağımlılıklarını alır.|
|[Ccustominterpolatör:: GetDuration](#getduration)|Enterpolatör 'ın süresini alır.|
|[Ccustominterpolatör:: GetFinalValue](#getfinalvalue)|Enterpolatörü 'nin müşteri adaylarına son değeri alır.|
|[Ccustominterpolatör:: Init](#init)|Süreyi ve son değeri başlatır.|
|[Ccustominterpolatör:: Enterpolatevalue](#interpolatevalue)|Verilen bir uzaklığında değeri enterpolasyonlar.|
|[Ccustominterpolatör:: Enterpolatevelocity](#interpolatevelocity)|Verilen bir uzaklığa göre hızı enterpolasyonlar|
|[Ccustominterpolatör:: SetDuration](#setduration)|Enterpolatör 'ın süresini ayarlar.|
|[Ccustominterpolatör:: SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Enterpolatör 'un ilk değerini ve hızını ayarlar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Ccustominterpolatör:: m_currentValue](#m_currentvalue)|Enterpolasyonlu değer.|
|[Ccustominterpolatör:: m_currentVelocity](#m_currentvelocity)|Enterpolasyonlu hız.|
|[Ccustominterpolatör:: m_duration](#m_duration)|Geçişin süresi.|
|[Ccustominterpolatör:: m_finalValue](#m_finalvalue)|Geçişin sonundaki bir değişkenin son değeri.|
|[Ccustominterpolatör:: m_initialValue](#m_initialvalue)|Geçişin başlangıcında değişkenin değeri.|
|[Ccustominterpolatör:: m_initialVelocity](#m_initialvelocity)|Geçişin başlangıcında değişkenin hızı.|

## <a name="remarks"></a>Açıklamalar

Ccustominterpolatör öğesinden bir sınıf türetirsiniz ve özel bir ilişkilendirme algoritması uygulamak için tüm gerekli yöntemleri geçersiz kılın. Bu sınıfa yönelik bir işaretçi CCustomTransition parametresi olarak geçirilmelidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CCustomInterpolator`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="ccustominterpolatorccustominterpolator"></a><a name="ccustominterpolator"></a> Ccustominterpolatör:: Ccustominterpolatör

Özel bir enterpolatör nesnesi oluşturur ve tüm değerleri varsayılan 0 olarak ayarlar.

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parametreler

*süre*<br/>
Geçişin süresi.

*Sonlandırdeğer*

### <a name="remarks"></a>Açıklamalar

Kodun ilerleyen kısımlarında süreyi ve son değeri başlatmak için Ccustominterpolatör:: Init kullanın.

## <a name="ccustominterpolatorgetdependencies"></a><a name="getdependencies"></a> Ccustominterpolatör:: GetDependencies

Enterpolatörü 'nin bağımlılıklarını alır.

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parametreler

*ınitialvaluedependencies*<br/>
Çıktıların. SetInitialValueAndVelocity öğesine geçirilen ilk değere bağlı olan ara değer ayırmanın yönleri.

*initialVelocityDependencies*<br/>
Çıktıların. SetInitialValueAndVelocity öğesine geçirilen ilk hıza bağlı olan ara değer ayırmanın yönleri.

*durationDependencies*<br/>
Çıktıların. SetDuration 'a geçirilen süreye bağlı olan ara değer ayırmanın yönleri.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olayı başarısız kılmak istiyorsanız, geçersiz kılınan uygulamadan FALSE döndürün.

## <a name="ccustominterpolatorgetduration"></a><a name="getduration"></a> Ccustominterpolatör:: GetDuration

Enterpolatör 'ın süresini alır.

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parametreler

*süre*<br/>
Çıktıların. Geçişin süresi (saniye cinsinden).

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olayı başarısız kılmak istiyorsanız, geçersiz kılınan uygulamadan FALSE döndürün.

## <a name="ccustominterpolatorgetfinalvalue"></a><a name="getfinalvalue"></a> Ccustominterpolatör:: GetFinalValue

Enterpolatörü 'nin müşteri adaylarına son değeri alır.

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*değer*<br/>
Çıktıların. Geçişin sonundaki bir değişkenin son değeri.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olayı başarısız kılmak istiyorsanız, geçersiz kılınan uygulamadan FALSE döndürün.

## <a name="ccustominterpolatorinit"></a><a name="init"></a> Ccustominterpolatör:: Init

Süreyi ve son değeri başlatır.

```cpp
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parametreler

*süre*<br/>
Geçişin süresi.

*Sonlandırdeğer*<br/>
Geçişin sonundaki bir değişkenin son değeri.

## <a name="ccustominterpolatorinterpolatevalue"></a><a name="interpolatevalue"></a> Ccustominterpolatör:: Enterpolatevalue

Verilen bir uzaklığında değeri enterpolasyonlar.

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*değer*<br/>
Çıktıların. Enterpolasyonlu değer.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olayı başarısız kılmak istiyorsanız, geçersiz kılınan uygulamadan FALSE döndürün.

## <a name="ccustominterpolatorinterpolatevelocity"></a><a name="interpolatevelocity"></a> Ccustominterpolatör:: Enterpolatevelocity

Verilen bir uzaklığa göre hızı enterpolasyonlar

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>Parametreler

*hız*<br/>
Çıktıların. Uzaklığında değişkenin hızı.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olayı başarısız kılmak istiyorsanız, geçersiz kılınan uygulamadan FALSE döndürün.

## <a name="ccustominterpolatorm_currentvalue"></a><a name="m_currentvalue"></a> Ccustominterpolatör:: m_currentValue

Enterpolasyonlu değer.

```
DOUBLE m_currentValue;
```

## <a name="ccustominterpolatorm_currentvelocity"></a><a name="m_currentvelocity"></a> Ccustominterpolatör:: m_currentVelocity

Enterpolasyonlu hız.

```
DOUBLE m_currentVelocity;
```

## <a name="ccustominterpolatorm_duration"></a><a name="m_duration"></a> Ccustominterpolatör:: m_duration

Geçişin süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="ccustominterpolatorm_finalvalue"></a><a name="m_finalvalue"></a> Ccustominterpolatör:: m_finalValue

Geçişin sonundaki bir değişkenin son değeri.

```
DOUBLE m_finalValue;
```

## <a name="ccustominterpolatorm_initialvalue"></a><a name="m_initialvalue"></a> Ccustominterpolatör:: m_initialValue

Geçişin başlangıcında değişkenin değeri.

```
DOUBLE m_initialValue;
```

## <a name="ccustominterpolatorm_initialvelocity"></a><a name="m_initialvelocity"></a> Ccustominterpolatör:: m_initialVelocity

Geçişin başlangıcında değişkenin hızı.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustominterpolatorsetduration"></a><a name="setduration"></a> Ccustominterpolatör:: SetDuration

Enterpolatör 'ın süresini ayarlar.

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametreler

*süre*<br/>
Geçişin süresi.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olayı başarısız kılmak istiyorsanız, geçersiz kılınan uygulamadan FALSE döndürün.

## <a name="ccustominterpolatorsetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a> Ccustominterpolatör:: SetInitialValueAndVelocity

Enterpolatör 'un ilk değerini ve hızını ayarlar.

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametreler

*InitialValue*<br/>
Geçişin başlangıcında değişkenin değeri.

*InitialVelocity*<br/>
Geçişin başlangıcında değişkenin hızı.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olayı başarısız kılmak istiyorsanız, geçersiz kılınan uygulamadan FALSE döndürün.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
