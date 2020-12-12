---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2814'
title: Derleyici hatası C2814
ms.date: 11/04/2016
f1_keywords:
- C2814
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
ms.openlocfilehash: 3da888c70356abee8ae18990d521d5589a5c5069
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278395"
---
# <a name="compiler-error-c2814"></a>Derleyici hatası C2814

' üye ': yerel bir tür, yönetilen veya WinRT türü ' Type ' içinde iç içe olamaz

## <a name="example"></a>Örnek

Yerel tür bir CLR veya WinRT türünde iç içe geçirilemez. Aşağıdaki örnek C2814 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C2814.cpp
// compile with: /clr /c
ref class A {
   class B {};   // C2814
   ref class C {};   // OK
};
```
