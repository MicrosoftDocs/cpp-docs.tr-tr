---
title: Derleyici Uyarısı (Düzey 2) C4099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4099
dev_langs:
- C++
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d7ffee02e8e5414a0e06cc4ba0da77a50c75f53
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110178"
---
# <a name="compiler-warning-level-2-c4099"></a>Derleyici Uyarısı (düzey 2) C4099

'identifier': tür adı 'objecttype1' artık 'objecttype2' kullanarak görülen kullanarak ilk görülme

Bir yapı bildirilen bir nesne sınıfı olarak tanımlanır ve bir sınıf olarak bildirilen bir nesne bir yapı tanımlanır. Derleme tanımında belirtilen türü kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4099 oluşturur.

```
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```