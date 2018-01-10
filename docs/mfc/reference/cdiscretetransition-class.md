---
title: "CDiscreteTransition sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::Create
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_delay
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_hold
dev_langs: C++
helpviewer_keywords:
- CDiscreteTransition [MFC], CDiscreteTransition
- CDiscreteTransition [MFC], Create
- CDiscreteTransition [MFC], m_dblFinalValue
- CDiscreteTransition [MFC], m_delay
- CDiscreteTransition [MFC], m_hold
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd4b1b7c868c13176d2cd99204b0bae1e2b9992d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdiscretetransition-class"></a>CDiscreteTransition sınıfı
Bir ayrık geçiş yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDiscreteTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDiscreteTransition::CDiscreteTransition](#cdiscretetransition)|Ayrı geçiş nesnesi oluşturur ve parametreleri başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDiscreteTransition::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDiscreteTransition::m_dblFinalValue](#m_dblfinalvalue)|Geçiş işleminin sonunda animasyon değişkeninin değeri.|  
|[CDiscreteTransition::m_delay](#m_delay)|Son değer anlık anahtarına geciktirmek üzere süre miktarı.|  
|[CDiscreteTransition::m_hold](#m_hold)|Son değeri değişkeni tutmak süre miktarı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrık bir geçiş sırasında animasyon değişkeni ilk değerinde belirtilen gecikme süresi ve ardından anahtarlara eşzamanlı olarak belirtilen bir son değeri ve bu değeri bırakılmalıdır için için verilen tutma süresi kalır. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işlecini kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Bu COM nesnesinin oluşturulmasını etkisizdir sonra üye değişkenleri değiştirme.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="cdiscretetransition"></a>CDiscreteTransition::CDiscreteTransition  
 Ayrı geçiş nesnesi oluşturur ve parametreleri başlatır.  
  
```  
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,  
    DOUBLE dblFinalValue,  
    UI_ANIMATION_SECONDS hold);
```  
  
### <a name="parameters"></a>Parametreler  
 `delay`  
 Son değer anlık anahtarına geciktirmek üzere süre miktarı.  
  
 `dblFinalValue`  
 Geçiş işleminin sonunda animasyon değişkeninin değeri.  
  
 `hold`  
 Son değeri değişkeni tutmak süre miktarı.  
  
##  <a name="create"></a>CDiscreteTransition::Create  
 Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
`pLibrary`  
 Bir işaretçi bir [IUIAnimationTransitionLibrary arabirimi](https://msdn.microsoft.com/library/windows/desktop/dd371897), standart geçişleri kitaplığı tanımlar.  

  
### <a name="return-value"></a>Dönüş Değeri  
 Geçiş başarılı bir şekilde oluşturulursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_dblfinalvalue"></a>CDiscreteTransition::m_dblFinalValue  
 Geçiş işleminin sonunda animasyon değişkeninin değeri.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_delay"></a>CDiscreteTransition::m_delay  
 Son değer anlık anahtarına geciktirmek üzere süre miktarı.  
  
```  
UI_ANIMATION_SECONDS m_delay;  
```  
  
##  <a name="m_hold"></a>CDiscreteTransition::m_hold  
 Son değeri değişkeni tutmak süre miktarı.  
  
```  
UI_ANIMATION_SECONDS m_hold;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
