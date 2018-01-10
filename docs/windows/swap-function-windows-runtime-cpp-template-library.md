---
title: "Swap işlevi (Windows çalışma zamanı C++ Şablon kitaplığı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::Swap
dev_langs: C++
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e3278b21d57de0aa23e8b371ae286df4f64327b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="swap-function-windows-runtime-c-template-library"></a>Swap İşlevi (Windows Çalışma Zamanı C++ Şablon Kitaplığı)
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW inline void Swap(  
   _Inout_ T& left,  
   _Inout_ T& right  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `left`  
 İlk bağımsız değişken.  
  
 `right`  
 İkinci bağımsız değişken.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
## <a name="remarks"></a>Açıklamalar  
 İki belirtilen bağımsız değişken değerlerini değiş tokuş eder.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)