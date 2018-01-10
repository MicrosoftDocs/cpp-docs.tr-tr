---
title: "Derleyici Hatası C3391 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3391
dev_langs: C++
helpviewer_keywords: C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c5302939fa8a77a244c039d45c10ea5596897240
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3391"></a>Derleyici Hatası C3391
'type_arg': 'param' genel 'generic_type' ın genel parametresi için geçersiz tür bağımsız değişkeni bir null değer türü olması gerekir  
  
Genel bir tür yanlış örneği. Tür tanımı kontrol edin. Daha fazla bilgi için bkz: <xref:System.Nullable> ve [genel türler](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C# kullanan C + genel türler yazılırken desteklenmez belirli kısıtlamalarına sahip genel bir tür içeren bir bileşen oluşturmak için +/ CLI. Daha fazla bilgi için bkz: [tür parametrelerindeki kısıtlamalar](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
C3391.dll bileşeni kullanılabilir olduğunda, aşağıdaki örnek C3391 oluşturur.  
  
```cpp  
// C3391_b.cpp  
// Compile by using: cl /clr C3391_b.cpp  
#using <C3391.dll>  
using namespace System;  
value class VClass {};  
  
int main() {  
   GR< Nullable<VClass> >^ a =   
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable  
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK  
}  
```