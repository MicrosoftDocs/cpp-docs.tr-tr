---
title: CAnimationVariableChangeHandler sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e35fc33b26fa6bead73458a46d7c4edee1cf136
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350998"
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
  
##  <a name="onvaluechanged"></a>  CAnimationVariableChangeHandler::OnValueChanged  
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
  
##  <a name="setanimationcontroller"></a>  CAnimationVariableChangeHandler::SetAnimationController  
 Animasyon denetleyicisi rota olayları gösteren bir işaretçi depolar.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Parametreler  
 `pAnimationController`  
 Olayları alacak animasyon denetleyici için bir işaretçi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
