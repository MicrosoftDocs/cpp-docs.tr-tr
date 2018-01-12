---
title: "CAnimationVariableChangeHandler sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
dev_langs: C++
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f70e8d59e291362496ec2555cf2838bf2df41d3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler sınıfı
Bir animasyon değişkeninin değeri değiştiğinde animasyon API tarafından çağrılan bir geri çağırma uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Oluşturan bir `CAnimationVariableChangeHandler` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CreateInstance`|Bir örneğini oluşturur `CAnimationVariableChangeHandler` nesnesi.|  
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|Bir animasyon değişkenin değerini değiştirildiğinde çağrılır. (Geçersiz kılmaları `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.)|  
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|Animasyon denetleyicisi rota olayları gösteren bir işaretçi depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu olay işleyicisi oluşturulur ve geçirilen `IUIAnimationVariable::SetVariableChangeHandler` yöntemi çağırdığınızda, `CAnimationVariable::EnableValueChangedEvent` veya `CAnimationBaseObject::EnableValueChangedEvent` (sağlayan bir animasyon nesnesinde kapsüllenmiş tüm animasyon değişkenler için bu olay).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="onvaluechanged"></a>CAnimationVariableChangeHandler::OnValueChanged  
 Bir animasyon değişkenin değerini değiştirildiğinde çağrılır.  
  
```  
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `storyboard`  
 Değişkeni animasyonu Film şeridi.  
  
 `variable`  
 Güncelleştirildi animasyon değişkeni.  
  
 `newValue`  
 Yeni değer.  
  
 `previousValue`  
 Önceki değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="setanimationcontroller"></a>CAnimationVariableChangeHandler::SetAnimationController  
 Animasyon denetleyicisi rota olayları gösteren bir işaretçi depolar.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Parametreler  
 `pAnimationController`  
 Olayları alacak animasyon denetleyici için bir işaretçi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
