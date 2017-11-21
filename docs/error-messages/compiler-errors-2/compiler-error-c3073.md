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
ms.openlocfilehash: 860cc8fccb545a8c66a8a5724b9854e9547deb10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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