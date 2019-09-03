---
title: kullanım dışı pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 2e76d1c53cb900c108e2839a9aad17b330143a5d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222410"
---
# <a name="deprecated-pragma"></a>kullanım dışı pragma

**Kullanım dışı bırakılan** pragma, bir işlevin, türün ya da başka herhangi bir tanımlayıcının daha sonra gelecek bir sürümde desteklenmeyeceğini veya artık kullanılmadığından emin olmanızı sağlar.

> [!NOTE]
> C++ 14 `[[deprecated]]` özniteliği hakkında daha fazla bilgi için, Microsoft `__declspec(deprecated)` değiştirici veya **kullanım dışı** pragma yerine bu özniteliğin ne zaman kullanılacağı üzerine yönergeler için bkz. [içindeki C++öznitelikler ](../cpp/attributes.md).

## <a name="syntax"></a>Sözdizimi

> **#pragma kullanım dışı (** *Identifier1* [ **,** *identifier2* ...] **)**

## <a name="remarks"></a>Açıklamalar

Derleyici **kullanım dışı** bir pragma tarafından belirtilen bir tanımlayıcıyla karşılaştığında, derleyici uyarısı [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)' ı yayınlar.

Makro adlarını kullanımdan kaldırmayı seçebilirsiniz. Makro adını tırnak içine koyun veya makro genişletmesi oluşur.

**Kullanım dışı bırakılan** pragma tüm eşleşen tanımlayıcılarda çalıştığından ve hesaba imza almaz, aşırı yüklenmiş işlevlerin belirli sürümlerini kullanımdan kaldırmaya yönelik en iyi seçenek değildir. Kapsama getirilen herhangi bir eşleşen işlev adı, uyarıyı tetikler.

Mümkün olduğunda, **kullanım dışı** pragma yerine `[[deprecated]]` c++ 14 özniteliğini kullanmanızı öneririz. Microsoft 'a özgü [__declspec (kullanım dışı)](../cpp/deprecated-cpp.md) bildirim değiştiricisi, **kullanım dışı** pragma değerinden birçok durumda daha iyi bir seçenektir. Öznitelik `[[deprecated]]` ve`__declspec(deprecated)` değiştirici, aşırı yüklenmiş işlevlerin belirli biçimleri için kullanım dışı durumu belirtmenize izin verir. Tanılama uyarısı yalnızca öznitelik veya değiştiricinin uygulandığı belirli aşırı yüklenmiş işleve yapılan başvurular üzerinde görüntülenir.

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