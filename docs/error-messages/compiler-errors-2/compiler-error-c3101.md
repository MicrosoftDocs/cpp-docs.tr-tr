---
title: Derleyici Hatası C3101
ms.date: 11/04/2016
f1_keywords:
- C3101
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
ms.openlocfilehash: d39afc548010df95bdf31b2c7708bc4fa0310bcd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404201"
---
# <a name="compiler-error-c3101"></a>Derleyici Hatası C3101

adlandırılmış öznitelik bağımsız değişkeni 'field' için geçersiz ifade

Bir adlandırılmış öznitelik bağımsız değişkeni başlatılırken değeri bir derleme zamanı sabiti olmalıdır.

Öznitelikler hakkında daha fazla bilgi için bkz. [kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

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