---
title: Derleyici Uyarısı (düzey 1) C4042
ms.date: 11/04/2016
f1_keywords:
- C4042
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
ms.openlocfilehash: 0ffc4c4aeb7d37ffa45f503a34fd369d36c00ce4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164215"
---
# <a name="compiler-warning-level-1-c4042"></a>Derleyici Uyarısı (düzey 1) C4042

' Identifier ': Hatalı depolama sınıfına sahip

Belirtilen depolama sınıfı bu bağlamda bu tanımlayıcıyla kullanılamaz. Derleyici bunun yerine varsayılan depolama sınıfını kullanır:

- *tanımlayıcı* bir fonksiyonda ise `extern`.

- *tanımlayıcı* , bir biçimsel parametre veya yerel değişken ise **Auto**.

- *Tanımlayıcı* genel bir değişkense, depolama sınıfı yok.

Bu uyarı, bir parametre bildiriminde **yazmaç** dışında bir depolama sınıfı belirtilerek oluşabilir.

Aşağıdaki örnek C4042 oluşturur

```cpp
// C4042.cpp
// compile with: /W1 /LD
int func2( __declspec( thread ) int tls_i )    // C4042
// try the following line instead
// int func2( int tls_i )
{
   return tls_i;
}
```
