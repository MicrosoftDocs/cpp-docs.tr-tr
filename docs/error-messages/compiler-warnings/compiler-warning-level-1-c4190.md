---
title: Derleyici Uyarısı (düzey 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: 6d110aa70a470382e274546e95599804fa3bc7d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199881"
---
# <a name="compiler-warning-level-1-c4190"></a>Derleyici Uyarısı (düzey 1) C4190

' Identifier1 ' için C bağlaması belirtildi, ancak C ile uyumsuz olan UDT ' identifier2 ' döndürüyor

İşlev veya işlev işaretçisi, dönüş türü ve `extern` "C" bağlantısı olarak bir UDT (bir sınıf, yapı, Enum veya bileşim) olan bir UDT (Kullanıcı tanımlı tür) içerir. Bu, şu durumlarda geçerlidir:

- Bu işleve yapılan tüm çağrılar öğesinden C++oluşur.

- İşlevin tanımı içinde C++.

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
