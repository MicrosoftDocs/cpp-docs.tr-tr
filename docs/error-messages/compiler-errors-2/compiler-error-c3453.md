---
title: "Derleyici Hatası C3453 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3453
dev_langs:
- C++
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59ae13c68ce3d013afd21b1de7ae9571966052dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3453"></a>Derleyici Hatası C3453
'öznitelik': 'assembly' niteleyicisi eşleşmediği için uygulanmamış özniteliği  
  
 Derleme veya modülü düzeyindeki öznitelikler yalnızca tek başına yönergeleri belirtilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3453 oluşturur.  
  
```  
// C3453.cpp  
// compile with: /clr /c  
[assembly:System::CLSCompliant(true)]   // C3453  
// try the following line instead  
// [assembly:System::CLSCompliant(true)];  
ref class X {};  
```