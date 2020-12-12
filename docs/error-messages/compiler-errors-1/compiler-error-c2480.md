---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2480'
title: Derleyici hatası C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 0c7f73b7e1aa205d38577602b93907309935b216
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316550"
---
# <a name="compiler-error-c2480"></a>Derleyici hatası C2480

' tanımlayıcı ': ' Thread ' yalnızca statik kapsamın veri öğeleri için geçerlidir

`thread`Özniteliği bir otomatik değişken, statik olmayan veri üyesi, işlev parametresi veya işlev bildirimleri veya tanımlarında kullanamazsınız.

`thread`Yalnızca genel değişkenler, statik veri üyeleri ve yerel statik değişkenler için özniteliğini kullanın.

Aşağıdaki örnek C2480 oluşturur:

```cpp
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```
