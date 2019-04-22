---
title: Derleyici Hatası C3106
ms.date: 11/04/2016
f1_keywords:
- C3106
helpviewer_keywords:
- C3106
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
ms.openlocfilehash: c5ed544549aecd9811279e065d7c252fe085e545
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775995"
---
# <a name="compiler-error-c3106"></a>Derleyici Hatası C3106

'attribute': Adsız bağımsız değişkenler adlandırılmış bağımsız değişkenler gelmelidir

Adsız bağımsız değişkenleri, bir öznitelik adlandırılmış bağımsız değişkenler önce geçirilmelidir.

Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3106 oluşturur.

```
// C3106.cpp
// compile with: /c
[module(name="MyLib", dll)];   // C3106
[module(dll, name="MyLib")];   // OK
```