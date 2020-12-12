---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2388'
title: Derleyici hatası C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 63a2758b4e214b38c7d999bdc2a33d328709ea67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123987"
---
# <a name="compiler-error-c2388"></a>Derleyici hatası C2388

' symbol ': bir simge hem __declspec (AppDomain) hem de \_ _declspec (işlem) ile bildirilemez

`appdomain`Ve `process` **`__declspec`** değiştiricileri aynı sembol üzerinde kullanılamaz. Bir değişken için depolama, işlem veya uygulama etki alanı başına mevcuttur.

Daha fazla bilgi için bkz. [AppDomain](../../cpp/appdomain.md) ve [Process](../../cpp/process.md).

Aşağıdaki örnek C2388 oluşturur:

```cpp
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```
