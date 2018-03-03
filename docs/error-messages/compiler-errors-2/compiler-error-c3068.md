---
title: "Derleyici Hatası C3068 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 448a0b9e9c626523c08a0bd30ab285ef2c29312c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3068"></a>Derleyici Hatası C3068
'function': 'naked' işlevi bir C++ özel durum oluştuysa, geriye doğru izleme gerektirecek nesneleri içeremez  
  
 Derleyici üzerinde yığını geriye doğru izleme gerçekleştiremedi bir [naked](../../cpp/naked-cpp.md) geçici bir nesne işlev ve C++ özel durum işleme oluşturulduğundan, özel durum oluşturdu işlevi ([/EHsc](../../build/reference/eh-exception-handling-model.md)) belirtildi.  
  
 Bu hatayı gidermek için en az aşağıdakilerden birini yapın:  
  
-   /EHsc ile derleme değil.  
  
-   İşlev olarak işaretlemeyin `naked`.  
  
-   Geçici bir nesne işlevinde oluşturmayın.  
  
 Geçici bir nesne yığında işlevi bir özel durum oluşturursa ve C++ özel durum işleme etkinse, bir işlev oluşturur, bir özel durum oluşursa derleyici yığını temizler.  
  
 Bir özel durum, giriş çağrılan kodu derleyici oluşturulan ve bitiş ve hangi çıplak işlev içinde mevcut olmayan bir işlev için yürütülür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3068 oluşturur:  
  
```  
// C3068.cpp  
// compile with: /EHsc  
// processor: x86  
class A {  
public:  
   A(){}  
   ~A(){}  
};  
  
void b(A){}  
  
__declspec(naked) void c() {  
   b(A());   // C3068   
};  
```