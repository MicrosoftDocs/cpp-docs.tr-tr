---
title: RaiseException işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
dev_langs:
- C++
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2af97ac13386db450318f4d1f384517a8dd77baf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882189"
---
# <a name="raiseexception-function"></a>RaiseException İşlevi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline void __declspec(noreturn)   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hr`  
 Özel durum kodu gerçekleştirilen özel durum; diğer bir deyişle, başarısız işleminizi HRESULT.  
  
 `dwExceptionFlags`  
 Devam ettirilebilir özel durumu (bayrak değeri sıfırdır) ya da noncontinuable özel durumu (bayrak değeri sıfır olmayan) belirten bir bayrak. Varsayılan olarak, özel durum noncontinuable ' dir.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağıran iş parçacığı bir özel durumla başlatır.  
  
 Daha fazla bilgi için bkz: Windows **RaiseException** işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)