---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4295'
title: Derleyici Uyarısı (düzey 4) C4295
ms.date: 01/09/2018
f1_keywords:
- C4295
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
ms.openlocfilehash: 77f94d96d7ce5659652296e814777341a310a19f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294593"
---
# <a name="compiler-warning-level-4-c4295"></a>Derleyici Uyarısı (düzey 4) C4295

> '*Array*': dizi Sonlandırıcı null karakterini içeremeyecek kadar küçük

Dizi başlatıldı, ancak dizideki son karakter null değil; diziye dize olarak erişmek beklenmeyen sonuçlara neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4295 oluşturur. Bu sorunu düzeltebilmeniz için, dizi boyutunun daha büyük olduğunu, başlatıcı dizesinden bir Sonlandırıcı null değerini tutacak şekilde bildirebilir veya bir dizi başlatıcısı listesi kullanarak **`char`** , null sonlandırılmış bir dize değil, bunun bir dizisi olduğunu net hale getirebilirsiniz.

```C
// C4295.c
// compile with: /W4

int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
