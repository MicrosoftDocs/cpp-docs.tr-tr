---
title: Önemli hata C1190 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1190
dev_langs:
- C++
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 831eb782b074ed8ba0eb36d1abef7857321f2483
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227345"
---
# <a name="fatal-error-c1190"></a>Önemli hata C1190
Yönetilen hedeflenen kod gerektiren bir ' / clr' seçeneği  
  
 CLR yapıları kullanıyor, ancak belirtmemek **/CLR**.  
  
 Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Aşağıdaki örnek C1190 oluşturur:  
  
```  
// C1190.cpp  
// compile with: /c  
__gc class A {};   // C1190  
ref class A {};  
```