---
description: Microsoft C/C++ kullanım dışı bırakılan yönerge hakkında daha fazla bilgi edinin pragma
title: kullanım dışı pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.deprecated
helpviewer_keywords:
- deprecated pragma
- pragma, deprecated
no-loc:
- pragma
ms.openlocfilehash: 47e049f415b243a4c9959c7adc789f32f91de7ba
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712914"
---
# <a name="deprecated-no-locpragma"></a>`deprecated` pragma

, **`deprecated`** pragma Bir işlevin, türün ya da başka bir tanımlayıcının daha sonraki bir sürümde desteklenmeyeceğini veya artık kullanılmamalıdır.

> [!NOTE]
> C++ 14 `[[deprecated]]` özniteliği ve Microsoft değiştirici veya için bu özniteliğin ne zaman kullanılacağı hakkında daha fazla bilgi için `__declspec(deprecated)` **`deprecated`** pragma bkz. [c++ içindeki öznitelikler](../cpp/attributes.md).

## <a name="syntax"></a>Syntax

> **`#pragma deprecated(`***Identifier1* [ **`,`** *identifier2* ...]**`)`**

## <a name="remarks"></a>Açıklamalar

Derleyici tarafından belirtilen bir tanımlayıcıyla karşılaştığında **`deprecated`** pragma , derleyici uyarısı [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)' ı yayınlar.

Makro adlarını kullanımdan kaldırmayı seçebilirsiniz. Makro adını tırnak içine koyun veya makro genişletmesi oluşur.

**`deprecated`** pragma Tüm eşleşen tanımlayıcılarda çalıştığından ve hesaba imza almaz, aşırı yüklenmiş işlevlerin belirli sürümlerini kullanımdan kaldırmaya yönelik en iyi seçenek değildir. Kapsama getirilen herhangi bir eşleşen işlev adı, uyarıyı tetikler.

`[[deprecated]]`Bunun yerine, mümkün olduğunda c++ 14 özniteliğini kullanmanızı öneririz **`deprecated`** pragma . Microsoft 'a özgü [`__declspec(deprecated)`](../cpp/deprecated-cpp.md) bildirim değiştiricisi, ' den çok sayıda durumda da daha iyi bir seçenektir **`deprecated`** pragma . `[[deprecated]]`Öznitelik ve `__declspec(deprecated)` değiştirici, aşırı yüklenmiş işlevlerin belirli biçimleri için kullanım dışı durumu belirtmenize izin verir. Tanılama uyarısı yalnızca öznitelik veya değiştiricinin uygulandığı belirli aşırı yüklenmiş işleve yapılan başvurular üzerinde görüntülenir.

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

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
