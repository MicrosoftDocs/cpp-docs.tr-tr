---
title: Derleyici Uyarısı (düzey 4) C4295 | Microsoft Docs
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36c6ac4d8c3e2899b744d1c456ae3079ec031698
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053589"
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
