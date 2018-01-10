---
title: "Derleyici Hatası C3073 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3073
dev_langs: C++
helpviewer_keywords: C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 046b1d17ea0264e01a4acd9eb93e5babb826b756
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3073"></a>Derleyici Hatası C3073
'type': ref sınıfı, kullanıcı tanımlı kopya oluşturucu yok  
  
 İçinde bir [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) derleme, derleyici başvurusu türü için kopya Oluşturucu oluşturmaz. Herhangi bir **/CLR** derleme tanımlamalısınız bir başvuru türü için kendi kopya Oluşturucu kopyalanacak türünün bir örneği bekliyorsanız.  
  
 Daha fazla bilgi için bkz: [başvuru türleri için C++ yığın anlamları](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3073 oluşturur.  
  
```  
// C3073.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int) {}  
};  
  
ref class S {  
public:  
   S(int) {}  
   S(const S %rhs) {}   // copy constructor  
};  
  
void f(R) {}  
void f2(S) {}  
void f3(R%){}  
  
int main() {  
   R r(1);  
   f(r);   // C3073  
   f3(r);   // OK  
  
   S s(1);  
   f2(s);   // OK  
}  
```