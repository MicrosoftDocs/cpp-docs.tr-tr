---
title: Derleyici Hatası C2360 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2360
dev_langs:
- C++
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f443c27c496d5d05c17bde854181b0fdde58f545
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089209"
---
# <a name="compiler-error-c2360"></a>Derleyici Hatası C2360

'identifier' öğesinin başlatılması 'case' etiketiyle atlandı

Başlatma `identifier` içinde atlandı bir `switch` deyimi. Bildirimi bir bloğu içinde alınmış sürece bir bildirimi bir başlatıcıya sahip son atlama olamaz. (Bir blok içinde bildirildiği sürece, kapsam içinde sonuna kadar değişkendir `switch` deyimi.)

Aşağıdaki örnek, C2360 oluşturur:

```
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

Olası çözüm:

```
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```