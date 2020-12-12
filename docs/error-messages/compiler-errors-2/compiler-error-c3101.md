---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3101'
title: Derleyici hatası C3101
ms.date: 11/04/2016
f1_keywords:
- C3101
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
ms.openlocfilehash: e0c52eadd2af4b090b34f851d561535f360a7e59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116177"
---
# <a name="compiler-error-c3101"></a>Derleyici hatası C3101

' Field ' adlandırılmış öznitelik bağımsız değişkeni için geçersiz ifade

Adlandırılmış bir öznitelik bağımsız değişkeni başlatılırken, değer bir derleme zamanı sabiti olmalıdır.

Öznitelikler hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3101 oluşturur.

```cpp
// C3101.cpp
// compile with: /clr /c
ref class AAttribute : System::Attribute {
public:
   int Field;
};

extern int i;

[assembly:A(Field = i)];   // C3101
[assembly:A(Field = 0)];   // OK
```
