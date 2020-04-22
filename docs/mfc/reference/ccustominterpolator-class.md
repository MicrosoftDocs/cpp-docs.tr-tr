---
title: CCustomInterpolator Sınıfı
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
ms.openlocfilehash: 00ce0661fa3fbde714a7299ecbbd54df7c9bcc36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749166"
---
# <a name="ccustominterpolator-class"></a>CCustomInterpolator Sınıfı

Temel bir enterpolatör uygular.

## <a name="syntax"></a>Sözdizimi

```
class CCustomInterpolator;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|Fazla Yüklendi. Özel bir enterpolatör nesnesi tasarlar ve süre ve hızı belirtilen değerlere başolarak adlandırır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCustomInterpolator::GetDependencies](#getdependencies)|Enterpolatörün bağımlılıklarını alır.|
|[CCustomInterpolator::GetDuration](#getduration)|Enterpolatörün süresini alır.|
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|Enterpolatörün yol açtığı son değeri alır.|
|[CCustomInterpolator::Init](#init)|Süreyi ve son değeri başolarak karşılar.|
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|Değeri belirli bir ofsette interpolates.|
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|Hızı belirli bir ofsette interpolates|
|[CCustomInterpolator::SetDuration](#setduration)|Enterpolatörün süresini ayarlar.|
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Enterpolatörün başlangıç değerini ve hızını ayarlar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|İnterpolated değeri.|
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|İnterpolasyonlu hız.|
|[CCustomInterpolator::m_duration](#m_duration)|Geçiş süresi.|
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|Geçiş sonundaki değişkenin son değeri.|
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|Geçişin başındaki değişkenin değeri.|
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|Geçişin başlangıcındaki değişkenin hızı.|

## <a name="remarks"></a>Açıklamalar

CCustomInterpolator bir sınıf türetmek ve özel bir enterpolasyon algoritması uygulamak için gerekli tüm yöntemleri geçersiz kılmak. Bu sınıfa bir işaretçi CCustomTransition için bir parametre olarak geçirilmelidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CCustomInterpolator`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="ccustominterpolatorccustominterpolator"></a><a name="ccustominterpolator"></a>CCustomInterpolator::CCustomInterpolator

Özel bir enterpolatör nesnesi oluşturuyor ve tüm değerleri varsayılan 0 olarak ayarlar.

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Geçiş süresi.

*finalValue*

### <a name="remarks"></a>Açıklamalar

CCustomInterpolator kullanın::Init daha sonra kodda süre ve son değeri başlatma.

## <a name="ccustominterpolatorgetdependencies"></a><a name="getdependencies"></a>CCustomInterpolator::GetDependencies

Enterpolatörün bağımlılıklarını alır.

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parametreler

*ilkDeğer Bağımlılıkları*<br/>
Çıkış. Enterpolatörün setinitialvalueAndVelocity geçirilen ilk değere bağlı yönleri.

*ilkVelocityDependencies*<br/>
Çıkış. İlk hıza bağlı olarak interpolatörün yönleri SetInitialValueAndVelocity'ye geçer.

*süreBağımlılıklar*<br/>
Çıkış. İnterpolatörün SetDuration'e geçirilen süreye bağlı yönleri.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE döndürür. Olay başarısız olmak istiyorsanız geçersiz kılınan uygulamadan FALSE'u döndürün.

## <a name="ccustominterpolatorgetduration"></a><a name="getduration"></a>CCustomInterpolator::GetDuration

Enterpolatörün süresini alır.

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Çıkış. Geçiş süresi, saniye cinsinden.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE döndürür. Olay başarısız olmak istiyorsanız geçersiz kılınan uygulamadan FALSE'u döndürün.

## <a name="ccustominterpolatorgetfinalvalue"></a><a name="getfinalvalue"></a>CCustomInterpolator::GetFinalValue

Enterpolatörün yol açtığı son değeri alır.

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Çıkış. Geçiş sonundaki değişkenin son değeri.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE döndürür. Olay başarısız olmak istiyorsanız geçersiz kılınan uygulamadan FALSE'u döndürün.

## <a name="ccustominterpolatorinit"></a><a name="init"></a>CCustomInterpolator::Init

Süreyi ve son değeri başolarak karşılar.

```cpp
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Geçiş süresi.

*finalValue*<br/>
Geçiş sonundaki değişkenin son değeri.

## <a name="ccustominterpolatorinterpolatevalue"></a><a name="interpolatevalue"></a>CCustomInterpolator::InterpolateValue

Değeri belirli bir ofsette interpolates.

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Çıkış. İnterpolated değeri.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE döndürür. Olay başarısız olmak istiyorsanız geçersiz kılınan uygulamadan FALSE'u döndürün.

## <a name="ccustominterpolatorinterpolatevelocity"></a><a name="interpolatevelocity"></a>CCustomInterpolator::InterpolateVelocity

Hızı belirli bir ofsette interpolates

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>Parametreler

*Hız*<br/>
Çıkış. Dengedeki değişkenin hızı.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE döndürür. Olay başarısız olmak istiyorsanız geçersiz kılınan uygulamadan FALSE'u döndürün.

## <a name="ccustominterpolatorm_currentvalue"></a><a name="m_currentvalue"></a>CCustomInterpolator::m_currentValue

İnterpolated değeri.

```
DOUBLE m_currentValue;
```

## <a name="ccustominterpolatorm_currentvelocity"></a><a name="m_currentvelocity"></a>CCustomInterpolator::m_currentVelocity

İnterpolasyonlu hız.

```
DOUBLE m_currentVelocity;
```

## <a name="ccustominterpolatorm_duration"></a><a name="m_duration"></a>CCustomInterpolator::m_duration

Geçiş süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="ccustominterpolatorm_finalvalue"></a><a name="m_finalvalue"></a>CCustomInterpolator::m_finalValue

Geçiş sonundaki değişkenin son değeri.

```
DOUBLE m_finalValue;
```

## <a name="ccustominterpolatorm_initialvalue"></a><a name="m_initialvalue"></a>CCustomInterpolator::m_initialValue

Geçişin başındaki değişkenin değeri.

```
DOUBLE m_initialValue;
```

## <a name="ccustominterpolatorm_initialvelocity"></a><a name="m_initialvelocity"></a>CCustomInterpolator::m_initialVelocity

Geçişin başlangıcındaki değişkenin hızı.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustominterpolatorsetduration"></a><a name="setduration"></a>CCustomInterpolator::SetDuration

Enterpolatörün süresini ayarlar.

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Geçiş süresi.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE döndürür. Olay başarısız olmak istiyorsanız geçersiz kılınan uygulamadan FALSE'u döndürün.

## <a name="ccustominterpolatorsetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a>CCustomInterpolator::SetInitialValueAndVelocity

Enterpolatörün başlangıç değerini ve hızını ayarlar.

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametreler

*ınitialvalue*<br/>
Geçişin başındaki değişkenin değeri.

*ilkHız*<br/>
Geçişin başlangıcındaki değişkenin hızı.

### <a name="return-value"></a>Dönüş Değeri

Temel uygulama her zaman TRUE döndürür. Olay başarısız olmak istiyorsanız geçersiz kılınan uygulamadan FALSE'u döndürün.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
