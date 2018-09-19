---
title: Derleyici Hatası C2361 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2361
dev_langs:
- C++
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d91ee8b004e2f485326378eb2e1611f217f745c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029799"
---
# <a name="compiler-error-c2361"></a>Derleyici Hatası C2361

'identifier' öğesinin başlatılması 'default' etiketiyle atlandı

Başlatma `identifier` içinde atlandı bir `switch` deyimi. Bildirimi bir bloğu içinde alınmış sürece bir bildirimi bir başlatıcıya sahip son atlama olamaz. (Bir blok içinde bildirildiği sürece, kapsam içinde sonuna kadar değişkendir `switch` deyimi.)

Aşağıdaki örnek, C2361 oluşturur:

```
// C2361.cpp
void func( void ) {
   int x;
   switch (x) {
   case 0 :
      int i = 1;
      { int j = 1; }
   default :   // C2361 error
      int k = 1;
   }
}
```

Olası çözüm:

```
// C2361b.cpp
// compile with: /c
void func( void ) {
   int x = 0;
   switch (x) {
   case 0 :
      { int j = 1; int i = 1;}
   default :
      int k = 1;
   }
}
```