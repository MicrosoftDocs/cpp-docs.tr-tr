---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2345'
title: Derleyici hatası C2345
ms.date: 11/04/2016
f1_keywords:
- C2345
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
ms.openlocfilehash: 021c792a93fa27712087908ab30e1ddec84d08fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298415"
---
# <a name="compiler-error-c2345"></a>Derleyici hatası C2345

align (değer): geçersiz hizalama değeri

İzin verilen aralığın dışında bir [Hizalama](../../cpp/align-cpp.md) anahtar sözcüğüne bir değer geçirtiniz.

Aşağıdaki kod C2345 oluşturur

```cpp
// C2345.cpp
// compile with: /c
__declspec(align(0)) int a;   // C2345
__declspec(align(1)) int a;   // OK
```
