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
ms.workload: cplusplus
ms.openlocfilehash: 3f635aad0039812b50bd48a36f307ab5f60cba10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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