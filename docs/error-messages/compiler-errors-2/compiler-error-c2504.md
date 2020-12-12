---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2504'
title: Derleyici hatası C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 2a2269d750673a912096b497c10a9b112c23207c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213032"
---
# <a name="compiler-error-c2504"></a>Derleyici hatası C2504

' class ': taban sınıf tanımsız

Temel sınıf tanımlanmış, ancak hiç tanımlanmadı.  Olası nedenler:

1. Eksik içerme dosyası.

1. Dış temel sınıf [extern](../../cpp/extern-cpp.md)ile bildirilmemiş.

Aşağıdaki örnek C2504 oluşturur:

```cpp
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

Tamam

```
class C{};
class D : public C {};
```
