---
title: Derleyici Hatası C3894 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3894
dev_langs:
- C++
helpviewer_keywords:
- C3894
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc94b207f3e9df607a7599bc960f2423f7acd029
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3894"></a>Derleyici Hatası C3894
'var': l-değeri kullanım initonly statik veri üyesi sınıfı 'sınıfı' sınıf oluşturucu yalnızca izin  
  
 Statik [initonly](../../dotnet/initonly-cpp-cli.md) veri üyeleri yalnızca olarak kullanılabilir l değerleri kendi bir noktada bildirim veya statik Oluşturucu.  
  
 Örnek (statik olmayan) initonly veri üyeleri yalnızca kendi bir noktada bildirim veya örnek (statik olmayan) oluşturucuları l değerleri olarak kullanılabilir.  
  
 Aşağıdaki örnek C3894 oluşturur:  
  
```  
// C3894.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly static int data_var = 0;  
  
public:  
   // class constructor  
   static Y1() {  
      data_var = 99;   // OK  
      System::Console::WriteLine("in static constructor");  
   }  
  
   // not the class constructor  
   Y1(int i) {  
      data_var = i;   // C3894  
   }  
  
   static void Test() {}  
  
};  
  
int main() {  
   Y1::data_var = 88;   // C3894  
   int i = Y1::data_var;  
   Y1 ^ MyY1 = gcnew Y1(99);  
   Y1::Test();  
}  
```