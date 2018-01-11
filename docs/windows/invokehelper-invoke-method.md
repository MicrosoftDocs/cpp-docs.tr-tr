---
title: "Invokehelper::Invoke yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::InvokeHelper::Invoke
dev_langs: C++
helpviewer_keywords: Invoke method
ms.assetid: 98618815-c30e-4699-b3dd-203c91b1bf3b
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8707ac96c0417eddb015d7e802433bf071dda80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="invokehelperinvoke-method"></a>InvokeHelper::Invoke Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   Invoke  
)();  
STDMETHOD(  
   Invoke  
)(typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `arg1`  
 Bağımsız değişkeni 1.  
  
 `arg2`  
 2. bağımsız.  
  
 `arg3`  
 Bağımsız değişken 3.  
  
 `arg4`  
 Bağımsız değişken 4.  
  
 `arg5`  
 Bağımsız değişken 5.  
  
 `arg6`  
 Bağımsız değişken 6.  
  
 `arg7`  
 Bağımsız değişken 7.  
  
 `arg8`  
 Bağımsız değişken 8.  
  
 `arg9`  
 Bağımsız değişken 9.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen bağımsız değişken sayısı, imzası içeren olay işleyicisini çağırır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Invokehelper yapısı](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)