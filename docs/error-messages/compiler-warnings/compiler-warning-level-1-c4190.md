---
title: Derleyici Uyarısı (düzey 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: 05984594a57878aad8037861a15ac9284ff65192
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386505"
---
# <a name="compiler-warning-level-1-c4190"></a>Derleyici Uyarısı (düzey 1) C4190

'ıdentifier1' sahip C bağlaması belirtildi, ancak UDT 'C ile uyumsuz olan identifier2' döndürür

Bir işlev veya işlev işaretçisi bir UDT (bir sınıf, yapı, enum veya birleşim olan kullanıcı tanımlı tür) dönüş türüne sahip ve `extern` "C" bağlantısı. Bu yasal varsa:

- Bu işleve yapılan tüm çağrılar, C++'tan oluşur.

- C++'ta işlevi tanımıdır.

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