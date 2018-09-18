---
title: Derleyici Uyarısı (düzey 1) C4047 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4047
dev_langs:
- C++
helpviewer_keywords:
- C4047
ms.assetid: b75ad6fb-5c93-4434-a85f-c4083051a5de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f32cd21bbd6324d4d1b867dcea06bae209c553fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043345"
---
# <a name="compiler-warning-level-1-c4047"></a>Derleyici Uyarısı (düzey 1) C4047

'operator': 'ıdentifier1' farklıdır, 'identifier2' nden yöneltme düzeyi

Bir işaretçi değişkenine (bir düzey yöneltme), bir değişken (iki, yöneltme düzeyi) ve benzeri için işaret eden başka bir işaretçiye işaret edebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4047 oluşturur:

```
// C4047.c
// compile with: /W1

int main() {
   char **p = 0;   // two levels of indirection
   char *q = 0;   // one level of indirection

   char *p2 = 0;   // one level of indirection
   char *q2 = 0;   // one level of indirection

   p = q;   // C4047
   p2 = q2;
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4047 oluşturur:

```
// C4047b.c
// compile with: /W1
#include <stdio.h>

int main() {
   int i;
   FILE *myFile = NULL;
   errno_t  err = 0;
   char file_name[256];
   char *cs = 0;

   err = fopen_s(&myFile, "C4047.txt", "r");
   if ((err != 0) || (myFile)) {
      printf_s("fopen_s failed!\n");
      exit(-1);
    }
   i = fgets(file_name, 256, myFile);   // C4047
   cs = fgets(file_name, 256, myFile);   // OK
}
```