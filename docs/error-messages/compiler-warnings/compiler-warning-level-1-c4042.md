---
title: Derleyici Uyarısı (düzey 1) C4042
ms.date: 11/04/2016
f1_keywords:
- C4042
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
ms.openlocfilehash: db7f0425c3752c20ca8c5d4b6c95845ff64475c5
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627034"
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