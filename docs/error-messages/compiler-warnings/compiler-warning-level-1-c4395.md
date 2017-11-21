---
title: "Derleyici Uyarısı (düzey 1) C4395 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4395
dev_langs: C++
helpviewer_keywords: C4395
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b45c77951e64f3ce0182f756ba2077ce49b5bd50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4395"></a>Derleyici Uyarısı (düzey 1) C4395
'function': üye işlevi initonly veri üyesi 'member' bir kopyası üzerinde çağrılan  
  
 Üye işlevi çağrıldı bir [initonly (C + +/ CLI)](../../dotnet/initonly-cpp-cli.md) veri üyesi.  C4395 uyarır **initonly** veri üyesi işlevi tarafından değiştirilemez.  
  
 Aşağıdaki örnek C4395 oluşturur:  
  
```  
// C4395.cpp  
// compile with: /W1 /clr  
public value class V {  
public:  
   V(int data) : m_data(data) {}  
  
   void Mutate() {  
      System::Console::WriteLine("Enter Mutate: m_data = {0}", m_data);  
      m_data *= 2;  
      System::Console::WriteLine("Leave Mutate: m_data = {0}", m_data);  
   }  
  
   int m_data;  
};  
  
public ref class R {  
public:  
   static void f() {  
      System::Console::WriteLine("v.m_data = {0}", v.m_data);  
      v.Mutate();   // C4395  
      System::Console::WriteLine("v.m_data = {0}", v.m_data);  
   }  
  
private:  
   initonly static V v = V(4);  
};  
  
int main() {  
   R::f();  
}  
```