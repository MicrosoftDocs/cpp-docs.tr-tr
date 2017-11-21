---
title: "Derleyici Hatası C3453 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3453
dev_langs: C++
helpviewer_keywords: C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a9dfd380a55d9233d0b421372e65fc3331c49cc9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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