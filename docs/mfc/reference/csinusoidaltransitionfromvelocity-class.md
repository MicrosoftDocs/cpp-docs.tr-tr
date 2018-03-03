---
title: "CSinusoidalTransitionFromVelocity sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9189a7ea43591509767346737566a40f5961ec3b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
##  <a name="create"></a>CSinusoidalTransitionFromVelocity::Create  
 Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parametreler  
 `pLibrary`  
 Standart geçişleri oluşturulmasında sorumludur geçiş kitaplığı için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçiş başarılı bir şekilde oluşturulursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="csinusoidaltransitionfromvelocity"></a>CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity  
 Bir geçiş nesnesi oluşturur.  
  
```  
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,  
    UI_ANIMATION_SECONDS period);
```  
  
### <a name="parameters"></a>Parametreler  
 `duration`  
 Geçiş süresi.  
  
 `period`  
 Sinusoidal wave oscillation saniye cinsinden süre.  
  
##  <a name="m_duration"></a>CSinusoidalTransitionFromVelocity::m_duration  
 Geçiş süresi.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_period"></a>CSinusoidalTransitionFromVelocity::m_period  
 Sinusoidal wave oscillation saniye cinsinden süre.  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
