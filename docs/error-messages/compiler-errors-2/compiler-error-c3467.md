---
title: "Derleyici Hatası C3467 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3467
dev_langs: C++
helpviewer_keywords: C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e64552b2b576f59f8a05244aafe8bf129fd9b534
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3467"></a>Derleyici Hatası C3467
'type': Bu tür zaten iletildi  
  
 Derleyici aynı türde birden fazla ileriye doğru türü bildirimi bulunamadı. Tür başına yalnızca bir bildirimi izin verilir.  
  
 Daha fazla bilgi için bkz: [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir bileşen oluşturur.  
  
```  
// C3467.cpp  
// compile with: /LD /clr  
public ref class R {};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3467 oluşturur.  
  
```  
// C3467_b.cpp  
// compile with: /clr /c  
#using "C3467.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467  
```