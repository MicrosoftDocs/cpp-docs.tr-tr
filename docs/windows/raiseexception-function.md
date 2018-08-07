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
ms.openlocfilehash: e93b7281b079918641bf36ebcd72968a98eb95ec
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602672"
---
# <a name="raiseexception-function"></a>RaiseException İşlevi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline void __declspec(noreturn)   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
### <a name="parameters"></a>Parametreler  
 *İK*  
 Özel durum kodu gerçekleştirilen özel durum; diğer bir deyişle, başarısız bir işlemin HRESULT.  
  
 *dwExceptionFlags*  
 (Bayrak değeri sıfırdır) devam ettirilebilir özel durum ya da (bayrak değeri sıfır dışında) noncontinuable özel durumu gösteren bir bayrak. Varsayılan olarak, özel durum oluştuktan ' dir.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağıran iş parçacığında bir özel durum oluşturur.  
  
 Daha fazla bilgi için bkz. Windows `RaiseException` işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)