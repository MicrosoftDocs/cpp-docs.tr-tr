---
description: 'Daha fazla bilgi edinin: kullanım dışı pragma'
title: kullanım dışı pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.deprecated
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: b3f7e8bf17e98f6e6f57511f3c0c9a94a9388bf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300781"
---
# <a name="deprecated-pragma"></a>kullanım dışı pragma

**`deprecated`** Pragma, bir işlevin, türün ya da başka herhangi bir tanımlayıcının daha sonra gelecek bir sürümde desteklenmeyeceğini veya artık kullanılmadığından emin olmanızı sağlar.

> [!NOTE]
> C++ 14 `[[deprecated]]` özniteliği ve Microsoft değiştirici ya da pragma yerine bu özniteliğin ne zaman kullanılacağı hakkında bilgi için `__declspec(deprecated)` **`deprecated`** bkz. [C++ içindeki öznitelikler](../cpp/attributes.md).

## <a name="syntax"></a>Syntax

> **#pragma kullanım dışı (** *Identifier1* [ **,** *identifier2* ...] **)**

## <a name="remarks"></a>Açıklamalar

Derleyici bir pragma tarafından belirtilen tanımlayıcıyla karşılaştığında **`deprecated`** , derleyici uyarısı [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)' ı yayınlar.

Makro adlarını kullanımdan kaldırmayı seçebilirsiniz. Makro adını tırnak içine koyun veya makro genişletmesi oluşur.

**`deprecated`** Pragma tüm eşleşen tanımlayıcılarda çalıştığından ve hesaba imza almaz, aşırı yüklenmiş işlevlerin belirli sürümlerini kullanımdan kaldırabilmeniz için en iyi seçenek değildir. Kapsama getirilen herhangi bir eşleşen işlev adı, uyarıyı tetikler.

`[[deprecated]]`Mümkün olduğunda, pragma yerine c++ 14 özniteliğini kullanmanızı öneririz **`deprecated`** . Microsoft 'a özgü [__declspec (kullanım dışı)](../cpp/deprecated-cpp.md) bildirim değiştiricisi, pragma 'un birçok durumunda da daha iyi bir seçenektir **`deprecated`** . `[[deprecated]]`Öznitelik ve `__declspec(deprecated)` değiştirici, aşırı yüklenmiş işlevlerin belirli biçimleri için kullanım dışı durumu belirtmenize izin verir. Tanılama uyarısı yalnızca öznitelik veya değiştiricinin uygulandığı belirli aşırı yüklenmiş işleve yapılan başvurular üzerinde görüntülenir.

## <a name="example"></a>Örnek

```cpp
// pragma_directive_deprecated.cpp
// compile with: /W3
#include <stdio.h>
void func1(void) {
}

void func2(void) {
}

int main() {
   func1();
   func2();
   #pragma deprecated(func1, func2)
   func1();   // C4995
   func2();   // C4995
}
```

Aşağıdaki örnek, bir sınıfın kullanımdan kaldırılması gösterilmektedir:

```cpp
// pragma_directive_deprecated2.cpp
// compile with: /W3
#pragma deprecated(X)
class X {  // C4995
public:
   void f(){}
};

int main() {
   X x;   // C4995
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
