---
title: CCustomInterpolator sınıfı | Microsoft Docs
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
ms.openlocfilehash: b093ff87d7f2c8c52b6745be4e2a31580fce0fce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="ccustominterpolator-class"></a>CCustomInterpolator sınıfı
Temel bir ara uygular.  
  
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
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|İçin bir ara müşteri adayları son değerini alır.|  
|[CCustomInterpolator::Init](#init)|Süre ve son değer başlatır.|  
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|Belirtilen uzaklık değeri ilişkilendirileceğini.|  
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|Verilen uzaklığındaki hız ilişkilendirileceğini|  
|[CCustomInterpolator::SetDuration](#setduration)|Bir Ara'nın süresi ayarlar.|  
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Bir Ara'nın ilk değer ve hız ayarlar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|Ara değerli değeri.|  
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|Ara değerli hız.|  
|[CCustomInterpolator::m_duration](#m_duration)|Geçiş süresi.|  
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|Geçiş işleminin sonunda bir değişkenin son değeri.|  
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|Geçiş başlangıcında değişkeninin değeri.|  
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|Geçiş başlangıcında değişkeni hız.|  
  
## <a name="remarks"></a>Açıklamalar  
 CCustomInterpolator bir sınıf türetin ve bir özel ilişkilendirme algoritması uygulamak için tüm gerekli yöntemleri geçersiz kılın. Bu sınıf için bir işaretçi CCustomTransition için parametre olarak geçirilen.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CCustomInterpolator`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="ccustominterpolator"></a>  CCustomInterpolator::CCustomInterpolator  
 Özel bir ara nesnesi oluşturur ve 0 varsayılan olarak tüm değerlerini ayarlar.  
  
```  
CCustomInterpolator();

 
CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `duration`  
 Geçiş süresi.  
  
 `finalValue`  
  
### <a name="remarks"></a>Açıklamalar  
 Süre ve daha sonra kodunuzda son değerini başlatmak için CCustomInterpolator::Init kullanın.  
  
##  <a name="getdependencies"></a>  CCustomInterpolator::GetDependencies  
 Bir Ara'nın bağımlılıkları alır.  
  
```  
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,  
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,  
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>Parametreler  
 `initialValueDependencies`  
 Çıktı. İlk değerine bağımlı özelliklerini ınterpolator için SetInitialValueAndVelocity geçirildi.  
  
 `initialVelocityDependencies`  
 Çıktı. İlk hız üzerinde bağımlı özelliklerini ınterpolator için SetInitialValueAndVelocity geçirildi.  
  
 `durationDependencies`  
 Çıktı. Süreye göre bağımlı özelliklerini ınterpolator için SetDuration geçirildi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız isterseniz, geçersiz kılınan uygulamasından false değerini döndürür.  
  
##  <a name="getduration"></a>  CCustomInterpolator::GetDuration  
 Bir Ara'nın süresi alır.  
  
```  
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>Parametreler  
 `duration`  
 Çıktı. Saniye cinsinden geçiş süresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız isterseniz, geçersiz kılınan uygulamasından false değerini döndürür.  
  
##  <a name="getfinalvalue"></a>  CCustomInterpolator::GetFinalValue  
 İçin bir ara müşteri adayları son değerini alır.  
  
```  
virtual BOOL GetFinalValue(DOUBLE* value);
```  
  
### <a name="parameters"></a>Parametreler  
 `value`  
 Çıktı. Geçiş işleminin sonunda bir değişkenin son değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız isterseniz, geçersiz kılınan uygulamasından false değerini döndürür.  
  
##  <a name="init"></a>  CCustomInterpolator::Init  
 Süre ve son değer başlatır.  
  
```  
void Init(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `duration`  
 Geçiş süresi.  
  
 `finalValue`  
 Geçiş işleminin sonunda bir değişkenin son değeri.  
  
##  <a name="interpolatevalue"></a>  CCustomInterpolator::InterpolateValue  
 Belirtilen uzaklık değeri ilişkilendirileceğini.  
  
```  
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* value);
```  
  
### <a name="parameters"></a>Parametreler  
 `value`  
 Çıktı. Ara değerli değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız isterseniz, geçersiz kılınan uygulamasından false değerini döndürür.  
  
##  <a name="interpolatevelocity"></a>  CCustomInterpolator::InterpolateVelocity  
 Verilen uzaklığındaki hız ilişkilendirileceğini  
  
```  
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* velocity);
```  
  
### <a name="parameters"></a>Parametreler  
 `velocity`  
 Çıktı. Değişken uzaklığındaki hız.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız isterseniz, geçersiz kılınan uygulamasından false değerini döndürür.  
  
##  <a name="m_currentvalue"></a>  CCustomInterpolator::m_currentValue  
 Ara değerli değeri.  
  
```  
DOUBLE m_currentValue;  
```  
  
##  <a name="m_currentvelocity"></a>  CCustomInterpolator::m_currentVelocity  
 Ara değerli hız.  
  
```  
DOUBLE m_currentVelocity;  
```  
  
##  <a name="m_duration"></a>  CCustomInterpolator::m_duration  
 Geçiş süresi.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>  CCustomInterpolator::m_finalValue  
 Geçiş işleminin sonunda bir değişkenin son değeri.  
  
```  
DOUBLE m_finalValue;  
```  
  
##  <a name="m_initialvalue"></a>  CCustomInterpolator::m_initialValue  
 Geçiş başlangıcında değişkeninin değeri.  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="m_initialvelocity"></a>  CCustomInterpolator::m_initialVelocity  
 Geçiş başlangıcında değişkeni hız.  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="setduration"></a>  CCustomInterpolator::SetDuration  
 Bir Ara'nın süresi ayarlar.  
  
```  
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Parametreler  
 `duration`  
 Geçiş süresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız isterseniz, geçersiz kılınan uygulamasından false değerini döndürür.  
  
##  <a name="setinitialvalueandvelocity"></a>  CCustomInterpolator::SetInitialValueAndVelocity  
 Bir Ara'nın ilk değer ve hız ayarlar.  
  
```  
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,  
    DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Parametreler  
 `initialValue`  
 Geçiş başlangıcında değişkeninin değeri.  
  
 `initialVelocity`  
 Geçiş başlangıcında değişkeni hız.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel uygulama her zaman TRUE değerini döndürür. Olay başarısız isterseniz, geçersiz kılınan uygulamasından false değerini döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
