---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4190'
title: Derleyici Uyarısı (düzey 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: ff27d5913e23fa1488816b3e2bb7284440c7577b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266591"
---
# <a name="compiler-warning-level-1-c4190"></a>Derleyici Uyarısı (düzey 1) C4190

' Identifier1 ' için C bağlaması belirtildi, ancak C ile uyumsuz olan UDT ' identifier2 ' döndürüyor

İşlev veya işlev işaretçisi, Return Type ve bağlantı olarak bir UDT (bir sınıf, yapı, Enum veya bileşim) olan bir UDT (Kullanıcı tanımlı tür) içerir `extern "C"` . Bu, şu durumlarda geçerlidir:

- Bu işleve yapılan tüm çağrılar C++ ' dan oluşur.

- İşlevin tanımı C++ ' dır.

## <a name="example"></a>Örnek

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```
