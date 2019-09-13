---
title: Derleyici Uyarısı (düzey 4) C4295
ms.date: 01/09/2018
f1_keywords:
- C4295
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
ms.openlocfilehash: 5e8b546e4eb4b60197db504382b3230e779b1dec
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70924844"
---
# <a name="compiler-warning-level-4-c4295"></a>Derleyici Uyarısı (düzey 4) C4295

> '*Array*': dizi Sonlandırıcı null karakterini içeremeyecek kadar küçük

Dizi başlatıldı, ancak dizideki son karakter null değil; diziye dize olarak erişmek beklenmeyen sonuçlara neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4295 oluşturur. Bu sorunu düzeltebilmeniz için, dizi boyutunun daha büyük olduğunu, başlatıcı dizesinden bir Sonlandırıcı null değerini tutacak şekilde bildirebilir veya bir dizi başlatıcısı listesi kullanarak `char`, null sonlandırılmış bir dize değil, bunun bir dizisi olduğunu net hale getirebilirsiniz.

```C
// C4295.c
// compile with: /W4

int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
