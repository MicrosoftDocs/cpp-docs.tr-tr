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
ms.openlocfilehash: 815a669bc359121b13b1d636009cad81dc332304
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4295"></a>Derleyici Uyarısı (düzey 4) C4295
  
> '*dizi*': dizidir sonlandırma bir null karakter dahil etmek için çok küçük  
  
Bir dizi başlatıldı, ancak dizi son karakter bir null değil; dizi bir dize olarak erişme beklenmeyen sonuçlara neden olabilir.  
  
## <a name="example"></a>Örnek  
  
Aşağıdaki örnek C4295 oluşturur. Bu sorunu gidermek için dizi büyüklüğü tutabilecek kadar büyük bildirebilirsiniz sonlandırma null Başlatıcı dize veya bir dizi budur hedefi Temizle yapmak için bir dizi başlatıcı listesi kullanabilirsiniz `char`, bir null ile sonlandırılmış dize değil.  
  
```C  
// C4295.c
// compile with: /W4


int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
