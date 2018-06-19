---
title: CInstantaneousTransition sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::Create
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::m_dblFinalValue
dev_langs:
- C++
helpviewer_keywords:
- CInstantaneousTransition [MFC], CInstantaneousTransition
- CInstantaneousTransition [MFC], Create
- CInstantaneousTransition [MFC], m_dblFinalValue
ms.assetid: c3d5121f-2c6b-4221-9e57-10e082a31120
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 894d782f0f896837474c24255703a60e228737ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366742"
---
# <a name="cinstantaneoustransition-class"></a>CInstantaneousTransition sınıfı
Anlık geçişe yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CInstantaneousTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInstantaneousTransition::CInstantaneousTransition](#cinstantaneoustransition)|Bir geçiş nesnesi oluşturur ve son değerini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInstantaneousTransition::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInstantaneousTransition::m_dblFinalValue](#m_dblfinalvalue)|Geçiş işleminin sonunda animasyon değişkeninin değeri.|  
  
## <a name="remarks"></a>Açıklamalar  
 Anlık bir geçiş sırasında animasyon değişkeninin değeri, geçerli değerinden anında belirtilen son değer olarak değiştirir. Bu geçiş süresini daima sıfır olur. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işlecini kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Bu COM nesnesinin oluşturulmasını etkisizdir sonra üye değişkenleri değiştirme.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CInstantaneousTransition](../../mfc/reference/cinstantaneoustransition-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="cinstantaneoustransition"></a>  CInstantaneousTransition::CInstantaneousTransition  
 Bir geçiş nesnesi oluşturur ve son değerini başlatır.  
  
```  
CInstantaneousTransition(DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `dblFinalValue`  
 Geçiş işleminin sonunda animasyon değişkeninin değeri.  
  
##  <a name="create"></a>  CInstantaneousTransition::Create  
 Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parametreler  
`pLibrary`  
 Bir işaretçi bir [IUIAnimationTransitionLibrary arabirimi](https://msdn.microsoft.com/library/windows/desktop/dd371897), standart geçişleri kitaplığı tanımlar.  

  
### <a name="return-value"></a>Dönüş Değeri  
 Geçiş başarılı bir şekilde oluşturulursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_dblfinalvalue"></a>  CInstantaneousTransition::m_dblFinalValue  
 Geçiş işleminin sonunda animasyon değişkeninin değeri.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
