---
title: Derleyici Hatası C3106
ms.date: 11/04/2016
f1_keywords:
- C3106
helpviewer_keywords:
- C3106
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
ms.openlocfilehash: 072c87c0264afd585326e5207a494dfb45961b24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434508"
---
# <a name="compiler-error-c3106"></a>Derleyici Hatası C3106

'attribute': Adsız bağımsız değişkenler adlandırılmış bağımsız değişkenler gelmelidir

Adsız bağımsız değişkenleri, bir öznitelik adlandırılmış bağımsız değişkenler önce geçirilmelidir.

Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3106 oluşturur.

```
// C3106.cpp
// compile with: /c
[module(name="MyLib", dll)];   // C3106
[module(dll, name="MyLib")];   // OK
```