---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 2) C4099'
title: Derleyici Uyarısı (düzey 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: c35ce10560ca81f9457f6a21c4c55d96996e7645
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326523"
---
# <a name="compiler-warning-level-2-c4099"></a>Derleyici Uyarısı (düzey 2) C4099

' tanımlayıcı ': ' objecttype1 ' kullanılarak ilk görülen tür adı ' objecttype2 ' kullanılarak görüldü

Yapı olarak belirtilen bir nesne, sınıf olarak tanımlanır veya sınıf olarak belirtilen bir nesne yapı olarak tanımlanır. Derleyici, tanımda verilen türü kullanır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4099 oluşturur.

```cpp
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```
