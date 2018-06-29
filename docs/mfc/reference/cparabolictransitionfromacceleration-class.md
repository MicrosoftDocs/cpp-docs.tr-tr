---
title: CParabolicTransitionFromAcceleration sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
dev_langs:
- C++
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f54f600e9a98304f1113c6e9e22389f6c974a80
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078901"
---
# <a name="cparabolictransitionfromacceleration-class"></a>CParabolicTransitionFromAcceleration sınıfı
Hızlandırma parabolic geçiş yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CParabolicTransitionFromAcceleration : public CBaseTransition;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|Hızlandırma parabolic geçiş oluşturur ve belirtilen parametrelerle başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::m_dblAcceleration](#m_dblacceleration)|Animasyon değişkeni hızlandırma geçiş sırasında.|  
|[CParabolicTransitionFromAcceleration::m_dblFinalValue](#m_dblfinalvalue)|Geçiş işleminin sonunda animasyon değişkeninin değeri.|  
|[CParabolicTransitionFromAcceleration::m_dblFinalVelocity](#m_dblfinalvelocity)|Geçiş işleminin sonunda animasyon değişken hız.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hızlandırma parabolic geçişi sırasında belirtilen hızlarda bitiş son değeri başlangıç değerinden animasyon değişkenin değerini değiştirir. Hızlandırma oranını belirterek değişkeni son değer ne kadar hızlı ulaştığında kontrol edebilirsiniz. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işlecini kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Bu COM nesnesinin oluşturulmasını etkisizdir sonra üye değişkenleri değiştirme.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="cparabolictransitionfromacceleration"></a>  CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration  
 Hızlandırma parabolic geçiş oluşturur ve belirtilen parametrelerle başlatır.  
  
```  
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,  
    DOUBLE dblFinalVelocity,  
    DOUBLE dblAcceleration);
```  
  
### <a name="parameters"></a>Parametreler  
 *dblFinalValue*  
 Geçiş işleminin sonunda animasyon değişkeninin değeri.  
  
 *dblFinalVelocity*  
 Geçiş işleminin sonunda animasyon değişken hız.  
  
 *dblAcceleration*  
 Animasyon değişkeni hızlandırma geçiş sırasında.  
  
##  <a name="create"></a>  CParabolicTransitionFromAcceleration::Create  
 Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* /* not used */);
```  
  
### <a name="parameters"></a>Parametreler  
 *pLibrary*  
 Standart geçişleri oluşturulmasında sorumludur geçiş kitaplığı için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçiş başarılı bir şekilde oluşturulursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_dblacceleration"></a>  CParabolicTransitionFromAcceleration::m_dblAcceleration  
 Animasyon değişkeni hızlandırma geçiş sırasında.  
  
```  
DOUBLE m_dblAcceleration;  
```  
  
##  <a name="m_dblfinalvalue"></a>  CParabolicTransitionFromAcceleration::m_dblFinalValue  
 Geçiş işleminin sonunda animasyon değişkeninin değeri.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_dblfinalvelocity"></a>  CParabolicTransitionFromAcceleration::m_dblFinalVelocity  
 Geçiş işleminin sonunda animasyon değişken hız.  
  
```  
DOUBLE m_dblFinalVelocity;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
