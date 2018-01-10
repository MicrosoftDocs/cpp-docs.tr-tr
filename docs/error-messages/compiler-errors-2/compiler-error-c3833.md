---
title: "Derleyici Hatası C3833 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3833
dev_langs: C++
helpviewer_keywords: C3833
ms.assetid: 8152be53-e01e-48cd-9eef-9de38723664c
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db12fcd34841a6d69fab0b27efd01841127bb92e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3833"></a>Derleyici Hatası C3833
'type': pointer_type için geçersiz hedef türü  
  
 Bir [interior_ptr](../../windows/interior-ptr-cpp-cli.md) veya [pin_ptr](../../windows/pin-ptr-cpp-cli.md) yanlış bildirildi.  
  
 Aşağıdaki örnek C3833 oluşturur:  
  
```  
// C3833.cpp  
// compile with: /clr  
  
ref class MyClass {  
public:  
   int data;  
   MyClass() : data(35) {}  
};  
  
int main() {  
   interior_ptr<MyClass> p;   // C3833  
  
   // OK  
   MyClass ^ h_MyClass = gcnew MyClass;  
   interior_ptr<int> i = &(h_MyClass->data);  
   System::Console::WriteLine(*i);  
}  
```  
  
 Aşağıdaki örnek C3833 oluşturur:  
  
```  
// C3833b.cpp  
// compile with: /clr /c  
ref class G {  
public:  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   pin_ptr<G> ppG = &pG;   // C3833 can't pin a whole object  
  
   // OK  
   pin_ptr<int> ppG2 = &pG->i;  
   *ppG2 = 54;  
   int * pi = ppG2;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(*ppG2);  
  
   *pi = 55;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(*ppG2);  
  
   *ppG2 = 56;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(*ppG2);  
}  
```