---
title: Derleyici Hatası C3830 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3830
dev_langs:
- C++
helpviewer_keywords:
- C3830
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20b50d394b0701281cf382c6c0226b0b0b3c8180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016851"
---
# <a name="compiler-error-c3830"></a>Derleyici Hatası C3830

'type1': değer türleri yalnızca arabirim sınıflarından Devral 'type2' öğesinden devralamaz

Bir değer türü temel sınıfı devralamaz.  Daha fazla bilgi için [sınıfları ve yapıları](../../windows/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3830 oluşturur:

```
// C3830a.cpp
// compile with: /clr /c
public value struct MyStruct4 {
   int i;
};

public value class MyClass : public MyStruct4 {};   // C3830

// OK
public interface struct MyInterface4 {
   void i();
};

public value class MyClass2 : public MyInterface4 {
public:
   virtual void i(){}
};
```
