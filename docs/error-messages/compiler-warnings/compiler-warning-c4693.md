---
title: "Derleyici Uyarısı C4693 | Microsoft Docs"
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4693
dev_langs: C++
helpviewer_keywords: C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6f102fdc83461ba48cb4e03e316076375940a861
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4693"></a>Derleyici Uyarısı C4693

> 'class': korumalı bir Özet sınıf hiçbir örnek üyesinin 'Test' olamaz

Bir tür işaretlenmişse [korumalı](../../windows/sealed-cpp-component-extensions.md) ve [soyut](../../windows/abstract-cpp-component-extensions.md), yalnızca statik üyeleri olabilir.

Bu uyarı için bir hata otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, kullanmak [#pragma Uyarısı](../../preprocessor/warning.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4693 oluşturur.

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```