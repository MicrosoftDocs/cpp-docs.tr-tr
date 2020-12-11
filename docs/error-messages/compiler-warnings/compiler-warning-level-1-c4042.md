---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4042'
title: Derleyici Uyarısı (düzey 1) C4042
ms.date: 11/04/2016
f1_keywords:
- C4042
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
ms.openlocfilehash: 458d8460b71ac1b0d002b0127e3637cdfd6766ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160642"
---
# <a name="compiler-warning-level-1-c4042"></a>Derleyici Uyarısı (düzey 1) C4042

' Identifier ': Hatalı depolama sınıfına sahip

Belirtilen depolama sınıfı bu bağlamda bu tanımlayıcıyla kullanılamaz. Derleyici bunun yerine varsayılan depolama sınıfını kullanır:

- **`extern`**, *tanımlayıcı* bir işlevdir.

- **`auto`***tanımlayıcı* , bir biçimsel parametre veya yerel değişken ise.

- *Tanımlayıcı* genel bir değişkense, depolama sınıfı yok.

Bu uyarı, bir parametre bildiriminde dışında bir depolama sınıfı belirtilerek oluşabilir **`register`** .

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
