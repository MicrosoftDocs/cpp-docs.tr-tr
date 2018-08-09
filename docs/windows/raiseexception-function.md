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
ms.openlocfilehash: 5426d639ffb8655466239232da7672b89564bfae
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020115"
---
# <a name="raiseexception-function"></a>RaiseException İşlevi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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