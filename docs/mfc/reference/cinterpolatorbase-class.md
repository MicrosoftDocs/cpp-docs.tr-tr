---
title: CInterpolatorBase sınıfı | Microsoft Docs
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
ms.openlocfilehash: c0ca520fe89e04d984e6490c495f2622a6037c79
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase sınıfı
Yeni bir animasyon değişken değerini hesaplamak sahip olduğunda animasyon API tarafından çağrılan bir geri çağırma uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|Yapıları `CInterpolatorBase` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInterpolatorBase::CreateInstance](#createinstance)|Bir örneğini oluşturur `CInterpolatorBase` ve olayları işleme özel bir ara gösteren bir işaretçi depolar.|  
|[CInterpolatorBase::GetDependencies](#getdependencies)|Bir Ara'nın bağımlılıkları alır. (Geçersiz kılmaları `CUIAnimationInterpolatorBase::GetDependencies`.)|  
|[CInterpolatorBase::GetDuration](#getduration)|Bir Ara'nın süresi alır. (Geçersiz kılmaları `CUIAnimationInterpolatorBase::GetDuration`.)|  
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|İçin bir ara müşteri adayları son değerini alır. (Geçersiz kılmaları `CUIAnimationInterpolatorBase::GetFinalValue`.)|  
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Belirtilen uzaklık değeri ilişkilendirileceğini (geçersiz kılmaları `CUIAnimationInterpolatorBase::InterpolateValue`.)|  
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Verilen uzaklığındaki hız ilişkilendirileceğini (geçersiz kılmaları `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|  
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Olayları işleme özel bir ara gösteren bir işaretçi depolar.|  
|[CInterpolatorBase::SetDuration](#setduration)|Bir Ara'nın süresi ayarlar (geçersiz kılmaları `CUIAnimationInterpolatorBase::SetDuration`.)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Bir Ara'nın ilk değer ve hız ayarlar. (Geçersiz kılmaları `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işleyici oluşturulur ve geçirilen `IUIAnimationTransitionFactory::CreateTransition` zaman bir `CCustomTransition` nesne animasyon başlatma işleminin bir parçası olarak oluşturuluyor (başlatan `CAnimationController::AnimateGroup`). Genellikle doğrudan bu sınıfı kullanmanız gerekmez, yalnızca tüm olayları routs bir `CCustomInterpolator`-türetilmiş sınıf, yalnızca işaretçi oluşturucusuna geçirilen `CCustomTransition`.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="cinterpolatorbase"></a>  CInterpolatorBase::CInterpolatorBase  
 CInterpolatorBase nesnesi oluşturur.  
  
```  
CInterpolatorBase();
```  
  
##  <a name="createinstance"></a>  CInterpolatorBase::CreateInstance  
 CInterpolatorBase örneği oluşturur ve olayları işleme özel bir ara gösteren bir işaretçi depolar.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,  
    IUIAnimationInterpolator** ppHandler);
```  
  
### <a name="parameters"></a>Parametreler  
 `pInterpolator`  
 Özel bir ara gösteren bir işaretçi.  
  
 `ppHandler`  
 Çıktı. İşlevi döndüğünde CInterpolatorBase örneği için bir işaretçi içeriyor.  
  
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
 `initialValueDependencies`  
 Çıktı. İlk değerine bağımlı özelliklerini ınterpolator için SetInitialValueAndVelocity geçirildi.  
  
 `initialVelocityDependencies`  
 Çıktı. İlk hız üzerinde bağımlı özelliklerini ınterpolator için SetInitialValueAndVelocity geçirildi.  
  
 `durationDependencies`  
 Çıktı. Süreye göre bağımlı özelliklerini ınterpolator için SetDuration geçirildi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. CCustomInterpolator ayarlanmadı veya özel uygulama GetDependencies yönteminden false değerini döndürür, E_FAIL döndürür.  
  
##  <a name="getduration"></a>  CInterpolatorBase::GetDuration  
 Bir Ara'nın süresi alır.  
  
```  
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>Parametreler  
 `duration`  
 Çıktı. Saniye cinsinden geçiş süresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. CCustomInterpolator ayarlanmadı veya özel uygulama GetDuration yönteminden false değerini döndürür, E_FAIL döndürür.  
  
##  <a name="getfinalvalue"></a>  CInterpolatorBase::GetFinalValue  
 İçin bir ara müşteri adayları son değerini alır.  
  
```  
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```  
  
### <a name="parameters"></a>Parametreler  
 `value`  
 Çıktı. Geçiş işleminin sonunda bir değişkenin son değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. CCustomInterpolator ayarlanmadı veya özel uygulama GetFinalValue yönteminden false değerini döndürür, E_FAIL döndürür.  
  
##  <a name="interpolatevalue"></a>  CInterpolatorBase::InterpolateValue  
 Belirtilen uzaklık değeri ilişkilendirileceğini  
  
```  
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset, 
  __out DOUBLE* value);
```  
  
### <a name="parameters"></a>Parametreler  
 `offset`  
 Geçişin başlangıç uzaklığı. Her zaman daha büyük veya sıfıra eşit ve geçiş süresinden daha az uzaklığı. Geçiş süresi sıfır ise, bu yöntem çağrılmaz.  
  
 `value`  
 Çıktı. Ara değerli değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. CCustomInterpolator ayarlanmadı veya özel uygulama InterpolateValue yönteminden false değerini döndürür, E_FAIL döndürür.  
  
##  <a name="interpolatevelocity"></a>  CInterpolatorBase::InterpolateVelocity  
 Verilen uzaklığındaki hız ilişkilendirileceğini  
  
```  
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```  
  
### <a name="parameters"></a>Parametreler  
 `offset`  
 Geçişin başlangıç uzaklığı. Her zaman sıfırdan büyük veya sıfıra eşit uzaklığı ve geçiş süresini küçük veya buna eşit. Geçiş süresi sıfır ise, bu yöntem çağrılmaz.  
  
 `velocity`  
 Çıktı. Değişken uzaklığındaki hız.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. CCustomInterpolator ayarlanmadı veya özel uygulama InterpolateVelocity yönteminden false değerini döndürür, E_FAIL döndürür.  
  
##  <a name="setcustominterpolator"></a>  CInterpolatorBase::SetCustomInterpolator  
 Olayları işleme özel bir ara gösteren bir işaretçi depolar.  
  
```  
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>Parametreler  
 `pInterpolator`  
 Özel bir ara gösteren bir işaretçi.  
  
##  <a name="setduration"></a>  CInterpolatorBase::SetDuration  
 Bir Ara'nın süresi ayarlar  
  
```  
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Parametreler  
 `duration`  
 Geçiş süresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. CCustomInterpolator ayarlanmadı veya özel uygulama SetDuration yönteminden false değerini döndürür, E_FAIL döndürür.  
  
##  <a name="setinitialvalueandvelocity"></a>  CInterpolatorBase::SetInitialValueAndVelocity  
 Bir Ara'nın ilk değer ve hız ayarlar.  
  
```  
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue, 
  __in DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Parametreler  
 `initialValue`  
 Geçiş başlangıcında değişkeninin değeri.  
  
 `initialVelocity`  
 Geçiş başlangıcında değişkeni hız.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. CCustomInterpolator ayarlanmadı veya özel uygulama SetInitialValueAndVelocity yönteminden false değerini döndürür, E_FAIL döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
