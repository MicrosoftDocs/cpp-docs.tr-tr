---
title: "Derleyici Uyarısı (Düzey 3) C4398 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4398
dev_langs: C++
helpviewer_keywords: C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60d5379d18dd5105de2645b609dc13ad9882ac09
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4398"></a>Derleyici Uyarısı (Düzey 3) C4398
'değişkeni': işlem içi genel nesne ile birden çok appdomains oluşturuyor; düzgün çalışmayabilir __declspec(AppDomain) kullanmayı düşünün  
  
 Sanal işlevle [__clrcall](../../cpp/clrcall.md) yerel tür çağırma oluşturulmasını neden olan bir uygulama etki alanı vtable başına. Bu tür bir değişken doğru birden çok uygulama etki alanlarında kullanıldığında düzeltebilir değil.  
  
 Açıkça değişkeni işaretleyerek bu uyarıyı çözümleyebilirsiniz `__declspec(appdomain)`. Visual Studio 2017 önce Visual Studio sürümlerinde, bu uyarı ile derleme tarafından çözebilirsiniz **/CLR: pure**, varsayılan olarak genel değişkenler appdomain başına yapar.  
  
 Daha fazla bilgi için bkz: [appdomain](../../cpp/appdomain.md) ve [uygulama etki alanları ve Visual C++](../../dotnet/application-domains-and-visual-cpp.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4398 oluşturur.  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```