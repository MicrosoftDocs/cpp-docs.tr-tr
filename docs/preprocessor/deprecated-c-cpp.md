---
title: kullanım dışı pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.deprecated
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 5694c5175ff23952c601884243b428a842278b7d
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446479"
---
# <a name="deprecated-pragma"></a>kullanım dışı pragma

**Kullanım dışı bırakılan** pragma, bir işlevin, türün ya da başka herhangi bir tanımlayıcının daha sonra gelecek bir sürümde desteklenmeyeceğini veya artık kullanılmadığından emin olmanızı sağlar.

> [!NOTE]
> C++ 14 `[[deprecated]]` özniteliği ve Microsoft `__declspec(deprecated)` değiştiricisi veya **kullanım dışı** pragma yerine bu özniteliğin ne zaman kullanılacağı hakkında daha fazla bilgi için bkz. [içindeki C++öznitelikler ](../cpp/attributes.md).

## <a name="syntax"></a>Sözdizimi

> **#pragma kullanım dışı (** *Identifier1* [ **,** *identifier2* ...] **)**

## <a name="remarks"></a>Açıklamalar

Derleyici **kullanım dışı** bir pragma tarafından belirtilen bir tanımlayıcıyla karşılaştığında, derleyici uyarısı [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)' ı yayınlar.

Makro adlarını kullanımdan kaldırmayı seçebilirsiniz. Makro adını tırnak içine koyun veya makro genişletmesi oluşur.

**Kullanım dışı bırakılan** pragma tüm eşleşen tanımlayıcılarda çalıştığından ve hesaba imza almaz, aşırı yüklenmiş işlevlerin belirli sürümlerini kullanımdan kaldırmaya yönelik en iyi seçenek değildir. Kapsama getirilen herhangi bir eşleşen işlev adı, uyarıyı tetikler.

Mümkün olduğunda, **kullanım dışı** pragma yerine c++ 14 `[[deprecated]]` özniteliğini kullanmanızı öneririz. Microsoft 'a özgü [__declspec (kullanım dışı)](../cpp/deprecated-cpp.md) bildirim değiştiricisi, **kullanım dışı** pragma değerinden birçok durumda daha iyi bir seçenektir. `[[deprecated]]` özniteliği ve `__declspec(deprecated)` değiştiricisi, aşırı yüklenmiş işlevlerin belirli biçimleri için kullanım dışı durumu belirtmenize olanak tanır. Tanılama uyarısı yalnızca öznitelik veya değiştiricinin uygulandığı belirli aşırı yüklenmiş işleve yapılan başvurular üzerinde görüntülenir.

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