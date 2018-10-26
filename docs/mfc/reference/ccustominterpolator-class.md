---
title: Ccustomınterpolator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c924f49d8b1ec00585c90d5e106a9f6446f521d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072856"
---
# <a name="ccustominterpolator-class"></a>Ccustomınterpolator sınıfı

Temel Ara değer hesaplayıcı uygular.

## <a name="syntax"></a>Sözdizimi

```
class CCustomInterpolator;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|Fazla Yüklendi. Özel bir ara nesnesi oluşturur ve süresi ve hız belirtilen değerlerle başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCustomInterpolator::GetDependencies](#getdependencies)|Bir Ara'nın bağımlılıkları alır.|
|[CCustomInterpolator::GetDuration](#getduration)|Bir Ara'nın süresi alır.|
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|Ara değer hesaplayıcı, müşteri adayları son değerini alır.|
|[CCustomInterpolator::Init](#init)|Süresi ve son değer başlatır.|
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|Belirtilen bir uzaklık değeri ilişkilendirir.|
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|Belirtilen bir uzaklık hız ilişkilendirir|
|[CCustomInterpolator::SetDuration](#setduration)|Bir Ara'nın süresi ayarlar.|
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Bir Ara'nın ilk değer ve hız ayarlar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|İlişkilendirilmiş değer.|
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|İlişkilendirilmiş hız.|
|[CCustomInterpolator::m_duration](#m_duration)|Geçiş süresi.|
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|Bir değişken geçiş sonunda son değeri.|
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|Geçiş başlangıcında değişkeninin değeri.|
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|Geçiş başlangıcında değişkenin hız.|

## <a name="remarks"></a>Açıklamalar

Ccustomınterpolator bir sınıf türetin ve bir özel ilişkilendirme algoritması uygulamak için gerekli tüm yöntemleri geçersiz kılın. Bu sınıf işaretçisine CCustomTransition için parametre olarak geçirilmelidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CCustomInterpolator`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="ccustominterpolator"></a>  CCustomInterpolator::CCustomInterpolator

Özel bir ara nesnesi oluşturur ve 0'ı varsayılan olarak tüm değerlerini ayarlar.

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Geçiş süresi.

*finalValue*

### <a name="remarks"></a>Açıklamalar

CCustomInterpolator::Init süresi ve daha sonra kodunuzda son değerini başlatmak için kullanın.

##  <a name="getdependencies"></a>  CCustomInterpolator::GetDependencies

Bir Ara'nın bağımlılıkları alır.

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parametreler

*initialValueDependencies*<br/>
Çıktı. Başlangıç değerine bağımlı bir ara yönleri için SetInitialValueAndVelocity geçirildi.

*initialVelocityDependencies*<br/>
Çıktı. Başlangıç hızı üzerinde bağımlı bir ara yönleri için SetInitialValueAndVelocity geçirildi.

*durationDependencies*<br/>
Çıktı. Ara değer hesaplayıcı süresine bağlıdır yönleri için SetDuration geçirildi.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız istiyorsanız geçersiz kılınan uygulamasından false değerini döndürür.

##  <a name="getduration"></a>  CCustomInterpolator::GetDuration

Bir Ara'nın süresi alır.

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Çıktı. Saniye cinsinden geçiş süresi.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız istiyorsanız geçersiz kılınan uygulamasından false değerini döndürür.

##  <a name="getfinalvalue"></a>  CCustomInterpolator::GetFinalValue

Ara değer hesaplayıcı, müşteri adayları son değerini alır.

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Çıktı. Bir değişken geçiş sonunda son değeri.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız istiyorsanız geçersiz kılınan uygulamasından false değerini döndürür.

##  <a name="init"></a>  CCustomInterpolator::Init

Süresi ve son değer başlatır.

```
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Geçiş süresi.

*finalValue*<br/>
Bir değişken geçiş sonunda son değeri.

##  <a name="interpolatevalue"></a>  CCustomInterpolator::InterpolateValue

Belirtilen bir uzaklık değeri ilişkilendirir.

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Çıktı. İlişkilendirilmiş değer.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız istiyorsanız geçersiz kılınan uygulamasından false değerini döndürür.

##  <a name="interpolatevelocity"></a>  CCustomInterpolator::InterpolateVelocity

Belirtilen bir uzaklık hız ilişkilendirir

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>Parametreler

*Hız*<br/>
Çıktı. Değişkenin uzaklığında hız.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız istiyorsanız geçersiz kılınan uygulamasından false değerini döndürür.

##  <a name="m_currentvalue"></a>  CCustomInterpolator::m_currentValue

İlişkilendirilmiş değer.

```
DOUBLE m_currentValue;
```

##  <a name="m_currentvelocity"></a>  CCustomInterpolator::m_currentVelocity

İlişkilendirilmiş hız.

```
DOUBLE m_currentVelocity;
```

##  <a name="m_duration"></a>  CCustomInterpolator::m_duration

Geçiş süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>  CCustomInterpolator::m_finalValue

Bir değişken geçiş sonunda son değeri.

```
DOUBLE m_finalValue;
```

##  <a name="m_initialvalue"></a>  CCustomInterpolator::m_initialValue

Geçiş başlangıcında değişkeninin değeri.

```
DOUBLE m_initialValue;
```

##  <a name="m_initialvelocity"></a>  CCustomInterpolator::m_initialVelocity

Geçiş başlangıcında değişkenin hız.

```
DOUBLE m_initialVelocity;
```

##  <a name="setduration"></a>  CCustomInterpolator::SetDuration

Bir Ara'nın süresi ayarlar.

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Geçiş süresi.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız istiyorsanız geçersiz kılınan uygulamasından false değerini döndürür.

##  <a name="setinitialvalueandvelocity"></a>  CCustomInterpolator::SetInitialValueAndVelocity

Bir Ara'nın ilk değer ve hız ayarlar.

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametreler

*initialValue*<br/>
Geçiş başlangıcında değişkeninin değeri.

*initialVelocity*<br/>
Geçiş başlangıcında değişkenin hız.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız istiyorsanız geçersiz kılınan uygulamasından false değerini döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
