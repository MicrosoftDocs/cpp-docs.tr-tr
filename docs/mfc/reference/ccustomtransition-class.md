---
title: CCustomTransition sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
dev_langs:
- C++
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39588a6835b3484fc3961e793596c1190f85f7c4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952758"
---
# <a name="ccustomtransition-class"></a>CCustomTransition sınıfı
Özel bir geçiş uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCustomTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCustomTransition::CCustomTransition](#ccustomtransition)|Bir özel geçiş nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCustomTransition::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Bu geçiş ile ilişkili bir animasyon değişkeni uygulanacak bir başlangıç değeri ayarlar.|  
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Bu geçiş ile ilişkili bir animasyon değişkeni uygulanacak bir ilk hız ayarlar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|İlk değer SetInitialValue ile belirtilen olup olmadığını belirtir.|  
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|İlk hız SetInitialVelocity ile belirtilmiş olup olmadığını belirtir.|  
|[CCustomTransition::m_initialValue](#m_initialvalue)|İlk değerini depolar.|  
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|İlk hız depolar.|  
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|Özel bir ara gösteren bir işaretçi depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Özel geçişler uygulamak geliştiricilerin CCustomTransitions sınıfı sağlar. Oluşturulan ve standart bir geçiş kullanılan, ancak kendi Oluşturucusu özel bir ara gösteren bir işaretçi parametresi olarak kabul eder. Özel geçişler kullanmak için aşağıdaki adımları gerçekleştirin: 1. CCustomInterpolator bir sınıf türetin ve en az uygulamak InterpolateValue yöntemi. 2. Özel bir ara nesnesinin ömrü kullanıldığı animasyon süreden daha uzun olması gerektiğini emin olun. 3. Bir CCustomTransition nesne örneği (new işlecini kullanarak) ve özel bir ara oluşturucuda için bir işaretçi geçirin. 4. Bu parametreler için özel ilişkilendirme gerekli olduğunda CCustomTransition::SetInitialValue ve CCustomTransition::SetInitialVelocity arayın. 5. İşaretçi değeri özel algoritmayla animasyonlu animasyon nesnesinin özel geçiş AddTransition yöntemi için geçirin. 6. Animasyon nesnenin değerini değiştirdiğinizde Windows animasyon API içinde CCustomInterpolator InterpolateValue (ve ilgili diğer yöntemler) çağırın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CCustomTransition`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="ccustomtransition"></a>  CCustomTransition::CCustomTransition  
 Bir özel geçiş nesnesi oluşturur.  
  
```  
CCustomTransition(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>Parametreler  
 *pInterpolator*  
 Özel bir ara gösteren bir işaretçi.  
  
##  <a name="create"></a>  CCustomTransition::Create  
 Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,  
    IUIAnimationTransitionFactory* pFactory);
```  
  
### <a name="parameters"></a>Parametreler  
 *pFactory*  
 Özel geçişler oluşturulmasında sorumludur geçiş üreteci için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, ilk değer ve bu geçiş ile ilişkili bir animasyon değişkeni uygulanacak ilk hız de ayarlayabilirsiniz. Bu amaçla framework (CAnimationController::AnimateGroup çağırdığınızda gerçekleşir) kapsüllenmiş geçiş COM nesnesi oluşturmadan önce SetInitialValue ve SetInitialVelocity çağırması gerekir.  
  
##  <a name="m_binitialvaluespecified"></a>  CCustomTransition::m_bInitialValueSpecified  
 İlk değer SetInitialValue ile belirtilen olup olmadığını belirtir.  
  
```  
BOOL m_bInitialValueSpecified;  
```  
  
##  <a name="m_binitialvelocityspecified"></a>  CCustomTransition::m_bInitialVelocitySpecified  
 İlk hız SetInitialVelocity ile belirtilmiş olup olmadığını belirtir.  
  
```  
BOOL m_bInitialVelocitySpecified;  
```  
  
##  <a name="m_initialvalue"></a>  CCustomTransition::m_initialValue  
 İlk değerini depolar.  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="m_initialvelocity"></a>  CCustomTransition::m_initialVelocity  
 İlk hız depolar.  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="m_pinterpolator"></a>  CCustomTransition::m_pInterpolator  
 Özel bir ara gösteren bir işaretçi depolar.  
  
```  
CCustomInterpolator* m_pInterpolator;  
```  
  
##  <a name="setinitialvalue"></a>  CCustomTransition::SetInitialValue  
 Bu geçiş ile ilişkili bir animasyon değişkeni uygulanacak bir başlangıç değeri ayarlar.  
  
```  
void SetInitialValue(DOUBLE initialValue);
```  
  
### <a name="parameters"></a>Parametreler  
 *initialValue*  
  
##  <a name="setinitialvelocity"></a>  CCustomTransition::SetInitialVelocity  
 Bu geçiş ile ilişkili bir animasyon değişkeni uygulanacak bir ilk hız ayarlar.  
  
```  
void SetInitialVelocity(DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Parametreler  
 *initialVelocity*  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
