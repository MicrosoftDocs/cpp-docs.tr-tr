---
title: "Makeandınitialize işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::MakeAndInitialize
dev_langs: C++
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a97796fa9b13e95cc446f04d7338dd91350c1c26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="makeandinitialize-function"></a>MakeAndInitialize İşlevi
Belirtilen Windows çalışma zamanı sınıf başlatır. Aynı modülde tanımlanmış bir bileşen örneği oluşturmak için bu işlevi kullanın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <typename T, typename I,   
typename TArg1,   
typename TArg2,   
typename TArg3,   
typename TArg4,   
typename TArg5,   
typename TArg6,   
typename TArg7,   
typename TArg8,   
typename TArg9> HRESULT MakeAndInitialize(_Outptr_result_nullonfailure_ I** ppvObject, TArg1 &&arg1, TArg2 &&arg2, TArg3 &&arg3, TArg4 &&arg4, TArg5 &&arg5, TArg6 &&arg6, TArg7 &&arg7, TArg8 &&arg8, TArg9 &&arg9) throw()  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğesinden devralınan kullanıcı tanımlı bir sınıf `WRL::RuntimeClass`.  
  
 `TArg1`  
 1'için belirtilen çalışma zamanı sınıf geçirilen bağımsız değişken türü.  
  
 `TArg2`  
 2'için belirtilen çalışma zamanı sınıf geçirilen bağımsız değişken türü.  
  
 `TArg3`  
 3'için belirtilen çalışma zamanı sınıf geçirilen bağımsız değişken türü.  
  
 `TArg4`  
 4'için belirtilen çalışma zamanı sınıf geçirilen bağımsız değişken türü.  
  
 `TArg5`  
 5'için belirtilen çalışma zamanı sınıf geçirilen bağımsız değişken türü.  
  
 `TArg6`  
 6'için belirtilen çalışma zamanı sınıf geçirilen bağımsız değişken türü.  
  
 `TArg7`  
 7'için belirtilen çalışma zamanı sınıf geçirilen bağımsız değişken türü.  
  
 `TArg8`  
 8'için belirtilen çalışma zamanı sınıf geçirilen bağımsız değişken türü.  
  
 `TArg9`  
 9'için belirtilen çalışma zamanı sınıf geçirilen bağımsız değişken türü.  
  
 `arg1`  
 Belirtilen çalışma zamanı sınıf için geçirilen bağımsız değişkeni 1.  
  
 `arg2`  
 Belirtilen çalışma zamanı sınıf için geçirilen bağımsız değişken 2.  
  
 `arg3`  
 Belirtilen çalışma zamanı sınıf için geçirilen bağımsız değişken 3.  
  
 `arg4`  
 Belirtilen çalışma zamanı sınıf için geçirilen bağımsız değişken 4.  
  
 `arg5`  
 Belirtilen çalışma zamanı sınıf için geçirilen bağımsız değişken 5.  
  
 `arg6`  
 Belirtilen çalışma zamanı sınıf için geçirilen bağımsız değişken 6.  
  
 `arg7`  
 Belirtilen çalışma zamanı sınıf için geçirilen bağımsız değişken 7.  
  
 `arg8`  
 Belirtilen çalışma zamanı sınıf için geçirilen bağımsız değişken 8.  
  
 `arg9`  
 Belirtilen çalışma zamanı sınıf için geçirilen bağımsız değişken 9.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir `HRESULT` değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz [nasıl yapılır: doğrudan WRL bileşenlerinin örneğini](../windows/how-to-instantiate-wrl-components-directly.md) bu işlev arasındaki farkları öğrenin ve [Microsoft::WRL::Make](../windows/make-function.md)ve bir örnek.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)