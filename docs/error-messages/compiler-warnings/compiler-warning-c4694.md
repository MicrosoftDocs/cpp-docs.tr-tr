---
title: "Derleyici Uyarısı C4694 | Microsoft Docs"
ms.date: 10/25/2017
ms.technology: cpp-tools
ms.topic: article
f1_keywords: C4694
dev_langs: C++
helpviewer_keywords: C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1af20859e394fe62403358107b74f9d1df5facb1
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="compiler-warning-c4694"></a>Derleyici Uyarısı C4694

> '*sınıfı*': korumalı bir Özet sınıf bir taban sınıfı olamaz*base_class*'

Soyut ve korumalı bir sınıf bir başvuru türünden devralan olamaz; korumalı ve soyut bir sınıf temel sınıf işlevlerini ne temel sınıf olarak kullanılan kendisine izin.

Daha fazla bilgi için bkz: [soyut](../../windows/abstract-cpp-component-extensions.md), [korumalı](../../windows/sealed-cpp-component-extensions.md), ve [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md).

Bu uyarı için bir hata otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, kullanmak [#pragma Uyarısı](../../preprocessor/warning.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4694 oluşturur.

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```