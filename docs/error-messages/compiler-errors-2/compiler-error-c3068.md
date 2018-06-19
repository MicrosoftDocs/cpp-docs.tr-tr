---
title: Derleyici Hatası C3068 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f378a60c79defed4fb1738515ca5b65b2851056
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256561"
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