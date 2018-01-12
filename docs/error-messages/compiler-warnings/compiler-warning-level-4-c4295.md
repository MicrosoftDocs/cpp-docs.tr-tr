---
title: "Derleyici Uyarısı (düzey 4) C4295 | Microsoft Docs"
ms.custom: 
ms.date: 1/09/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4295
dev_langs: C++
helpviewer_keywords: C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 56ffdce8c2790a3944a8f79753177bc80e249778
ms.sourcegitcommit: bc086a7acbe2d9fd77d115f269cc2a0dbeeb5b88
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
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
