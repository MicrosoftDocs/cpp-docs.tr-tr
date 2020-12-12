---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3106'
title: Derleyici hatası C3106
ms.date: 11/04/2016
f1_keywords:
- C3106
helpviewer_keywords:
- C3106
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
ms.openlocfilehash: 59e0544a05362584836c4cae60d0fc3d3cd920d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116086"
---
# <a name="compiler-error-c3106"></a>Derleyici hatası C3106

' Attribute ': adlandırılmamış bağımsız değişkenler adlandırılmış bağımsız değişkenlerden önce gelmelidir

Adlandırılmamış bağımsız değişkenlerin adlandırılmadan önce bir özniteliğe geçirilmesi gerekir.

Daha fazla bilgi için bkz. [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3106 oluşturur.

```cpp
// C3106.cpp
// compile with: /c
[module(name="MyLib", dll)];   // C3106
[module(dll, name="MyLib")];   // OK
```
