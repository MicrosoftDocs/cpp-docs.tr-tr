---
title: Derleyici Uyarısı (düzey 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: 09ea9e2963735c1e011e25b42b04ad6d67d084a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349821"
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