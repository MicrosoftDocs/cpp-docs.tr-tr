---
title: Make işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
dev_langs:
- C++
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f381a00b5ac1f105080355f1d3e3cd15efa5abf8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878079"
---
# <a name="make-function"></a>Make İşlevi
Belirtilen Windows çalışma zamanı sınıf başlatır. Aynı modülde tanımlanmış bir bileşen örneği oluşturmak için bu işlevi kullanın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8,  
   TArg9 &&arg9  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2  
);  
template <  
   typename T,  
   typename TArg1  
>  
ComPtr<T> Make(  
   TArg1 &&arg1  
);  
template <  
   typename T  
>  
ComPtr<T> Make();  
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
 A `ComPtr<T>` nesne başarılı; Aksi takdirde `nullptr`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz [nasıl yapılır: doğrudan WRL bileşenlerinin örneğini](../windows/how-to-instantiate-wrl-components-directly.md) bu işlev arasındaki farkları öğrenin ve [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)ve bir örnek.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)