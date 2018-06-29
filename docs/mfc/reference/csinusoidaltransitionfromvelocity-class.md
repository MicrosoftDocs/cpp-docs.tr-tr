---
title: CSinusoidalTransitionFromVelocity sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_period
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromVelocity [MFC], CSinusoidalTransitionFromVelocity
- CSinusoidalTransitionFromVelocity [MFC], Create
- CSinusoidalTransitionFromVelocity [MFC], m_duration
- CSinusoidalTransitionFromVelocity [MFC], m_period
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9f5cc55adac2bf5900d9891635a025716b9c1f3
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078585"
---
# <a name="csinusoidaltransitionfromvelocity-class"></a>CSinusoidalTransitionFromVelocity sınıfı
Animasyon değişkeni ilk hız tarafından belirlenen bir genliğidir olan hız sinusoidal geçiş yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSinusoidalTransitionFromVelocity : public CBaseTransition;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity](#csinusoidaltransitionfromvelocity)|Bir geçiş nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::m_duration](#m_duration)|Geçiş süresi.|  
|[CSinusoidalTransitionFromVelocity::m_period](#m_period)|Sinusoidal wave oscillation saniye cinsinden süre.|  
  
## <a name="remarks"></a>Açıklamalar  
 Animasyon değişkenin değerini ilk değer bir aralık sinusoidal geçiş süresini oscillates. Geçiş başladığında oscillation genliğidir animasyon değişkenin hız tarafından belirlenir. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işlecini kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Bu COM nesnesinin oluşturulmasını etkisizdir sonra üye değişkenleri değiştirme.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="create"></a>  CSinusoidalTransitionFromVelocity::Create  
 Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parametreler  
 *pLibrary*  
 Standart geçişleri oluşturulmasında sorumludur geçiş kitaplığı için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçiş başarılı bir şekilde oluşturulursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="csinusoidaltransitionfromvelocity"></a>  CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity  
 Bir geçiş nesnesi oluşturur.  
  
```  
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,  
    UI_ANIMATION_SECONDS period);
```  
  
### <a name="parameters"></a>Parametreler  
 *Süre*  
 Geçiş süresi.  
  
 *Süresi*  
 Sinusoidal wave oscillation saniye cinsinden süre.  
  
##  <a name="m_duration"></a>  CSinusoidalTransitionFromVelocity::m_duration  
 Geçiş süresi.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_period"></a>  CSinusoidalTransitionFromVelocity::m_period  
 Sinusoidal wave oscillation saniye cinsinden süre.  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
