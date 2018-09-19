---
title: Derleyici Uyarısı (düzey 1) C4129 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e02f38044180c45e221099d2874b7f8ff48d62f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098452"
---
# <a name="compiler-warning-level-1-c4129"></a>Derleyici Uyarısı (düzey 1) C4129

'character': Tanınmayan karakter kaçış sırası

`character` Bir ters eğik çizgiden (\\) bir karakter veya dize sabiti geçerli kaçış dizisi olarak tanınmıyor. Ters eğik çizgi yok sayıldı ve yazdırılmaz. Ters eğik çizgiyi takip eden karakterden yazdırılır.

Tek bir ters eğik çizgi yazdırmak için bir çift ters eğik çizgi belirtin (\\\\).

Bölümünde 2.13.2 C++ standardı, kaçış dizileri açıklar.

Aşağıdaki örnek, C4129 oluşturur:

```
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```