---
title: Derleyici Uyarısı (düzey 4) C4295
ms.date: 1/09/2018
f1_keywords:
- C4295
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
ms.openlocfilehash: ed31ea19f9c36a9c6fab7452a4bfc3843a151059
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472196"
---
# <a name="compiler-warning-level-4-c4295"></a>Derleyici Uyarısı (düzey 4) C4295

> '*dizi*': dizi Sonlandırıcı null karakterini içeremeyecek kadar küçük

Bir dizi başlatıldı ancak dizideki son karakter bir null değil. dize olarak dizi erişme beklenmeyen sonuçlara neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4295 oluşturur. Bu sorunu gidermek için dizi boyutu daha büyük tutacak bildirebilirsiniz Başlatıcı dize veya bir sonlandırıcı null bir dizi başlatıcı listesi bir dizi olan hedefi açıkça kullanabilir `char`, bir null ile sonlandırılmış dize değil.

```C
// C4295.c
// compile with: /W4

int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
