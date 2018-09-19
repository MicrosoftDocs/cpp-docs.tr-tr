---
title: Derleyici Hatası C2480 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b5d8f80293c05b651ad01e725ae501288005dfe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102594"
---
# <a name="compiler-error-c2480"></a>Derleyici Hatası C2480

'identifier': 'thread' geçerlidir yalnızca statik kapsamı olan veri öğeleri için

Kullanamazsınız `thread` otomatik değişken, statik olmayan veri üyesi, işlev parametresi veya işlev bildirimlerinde veya tanımlarında özniteliği.

Kullanım `thread` genel değişkenler ve statik veri üyeleri yalnızca yerel statik değişkenler için özniteliği.

Aşağıdaki örnek, C2480 oluşturur:

```
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```