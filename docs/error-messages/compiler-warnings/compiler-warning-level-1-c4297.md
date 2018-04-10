---
title: Derleyici Uyarısı (düzey 1) C4297 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C4297
dev_langs:
- C++
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9253ae709109927e69940d5023b542dfb543c6de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4297"></a>Derleyici Uyarısı (düzey 1) C4297
'function': işlevi kabul ancak bir özel durum yok  
  
 Bir işlev bildirimi bir (büyük olasılıkla örtük) içeren `noexcept` Belirleyicisi, boş bir `throw` özel durum belirleyici veya bir [__declspec(nothrow)](../../cpp/nothrow-cpp.md) özniteliği ve tanımını içeren bir veya daha fazla [throw ](../../cpp/try-throw-and-catch-statements-cpp.md) deyimleri. C4297 gidermek için bildirilen işlevlerde özel durumlar oluşturma girişiminde bulunmayın `__declspec(nothrow)`, `noexcept(true)` veya `throw()`. Alternatif olarak, kaldırma `noexcept`, `throw()`, veya `__declspec(nothrow)` belirtimi.  
  
 Varsayılan olarak, derleyici örtük oluşturur `noexcept(true)` kullanıcı tanımlı yok ediciler ve deallocator işlevleri ve derleyicinin ürettiği özel üye işlevleri tanımlayıcıları. C ++ 11 standart ISO için uygundur. Örtük noexcept tanımlayıcıları oluşturulmasını önlemek ve Visual Studio 2013 standart davranışını derleyiciye geri döndürmek için kullanmak **/Zc:implicitNoexcept-** derleyici seçeneği. Daha fazla bilgi için bkz: [/ZC: implicitnoexcept (örtük özel durum tanımlayıcıları)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).  
  
 Özel durum belirtimleri hakkında daha fazla bilgi için bkz: [özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md). Ayrıca bkz [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md) özel durum işleme derleme zamanında değiştirme hakkında bilgi için.  
  
 Bu uyarı için __declspec da oluşturulur ([dllexport](../../cpp/dllexport-dllimport.md)) işlevleri için C++ işlevlerini olsa bile extern "C" olarak işaretlenmiş.  
  
 Aşağıdaki örnek C4297 oluşturur:  
  
```  
// C4297.cpp  
// compile with: /W1 /LD  
void __declspec(nothrow) f1()   // declared nothrow  
// try the following line instead  
// void f1()  
{  
   throw 1;   // C4297  
}  
```