---
title: Derleyici Hatası C3101
ms.date: 11/04/2016
f1_keywords:
- C3101
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
ms.openlocfilehash: 8db1ba622a0c83a7f2a6421d79ff5853cbc4d9a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555567"
---
# <a name="compiler-error-c3101"></a>Derleyici Hatası C3101

adlandırılmış öznitelik bağımsız değişkeni 'field' için geçersiz ifade

Bir adlandırılmış öznitelik bağımsız değişkeni başlatılırken değeri bir derleme zamanı sabiti olmalıdır.

Öznitelikler hakkında daha fazla bilgi için bkz. [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3101 oluşturur.

```
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