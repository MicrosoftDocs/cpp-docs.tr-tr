---
title: "RaiseException işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::RaiseException
dev_langs: C++
helpviewer_keywords: RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0f64d0e38bb92f9ebe3954b47ece29184cbf1a73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)