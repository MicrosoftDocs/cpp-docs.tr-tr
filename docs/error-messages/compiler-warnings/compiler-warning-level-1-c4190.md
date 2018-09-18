---
title: Derleyici Uyarısı (düzey 1) C4190 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d398331c159c6fc639160dbe54d6ab5f969d3dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063743"
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