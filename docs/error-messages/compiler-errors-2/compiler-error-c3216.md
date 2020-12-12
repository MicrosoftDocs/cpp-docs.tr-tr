---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3216'
title: Derleyici hatası C3216
ms.date: 11/04/2016
f1_keywords:
- C3216
helpviewer_keywords:
- C3216
ms.assetid: bbab1efe-8779-4489-8bb0-b11e45f5cbe5
ms.openlocfilehash: 0f7ea3950b4fb832bdb349e788fbd73309918dd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173733"
---
# <a name="compiler-error-c3216"></a>Derleyici hatası C3216

kısıtlama, ' Type ' değil bir genel parametre olmalıdır

Kısıtlama hatalı oluşturulmuş.

Aşağıdaki örnek C3216 oluşturur:

```cpp
// C3216.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where F : A   // C3216
// Try the following line instead:
// where T : A    // C3216
ref class C {};
```

Aşağıdaki örnekte olası bir çözüm gösterilmektedir:

```cpp
// C3216b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```
