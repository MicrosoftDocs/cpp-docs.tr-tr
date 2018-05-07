---
title: Derleyici Hatası C3612 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3612
dev_langs:
- C++
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e07c899dbacdc58e9048ffa21d6be1b6abc02632
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3612"></a>Derleyici Hatası C3612
'type': korumalı bir sınıf soyut olamaz  
  
Kullanarak tanımlanmış türleri `value` varsayılan olarak, korumalı ve base tüm yöntemlerini uygular sürece bir sınıf soyuttur. Korumalı bir Özet sınıf, bir taban sınıf olabilir veya bu oluşturulabilir.  
  
Daha fazla bilgi için bkz: [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3612 oluşturur:  
  
```  
// C3612.cpp  
// compile with: /clr /c  
value struct V: public System::ICloneable {};   // C3612  
  
// OK  
value struct V2: public System::ICloneable {  
   Object^ Clone();  
};  
```