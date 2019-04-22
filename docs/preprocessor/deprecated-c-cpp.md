---
title: deprecated (C/C++)
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 262b23e6e4813a5e22bc3f4e7c9a18efb9988a7c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023324"
---
# <a name="deprecated-cc"></a>deprecated (C/C++)

**Kullanım dışı** pragma sağlar bir işlev, tür veya başka bir tanımlayıcı artık gelecek sürümlerde desteklenebilir olduğunu belirtmek için yayın veya artık kullanılmalıdır.

> [!NOTE]
> C ++ 14 hakkında bilgi için `[[deprecated]]` özniteliği ve ne zaman kullanan yönergeler vs özniteliği Microsoft declspec ya da pragması, bkz: [C++ Standart öznitelikleri](../cpp/attributes.md) özniteliği.

## <a name="syntax"></a>Sözdizimi

```
#pragma deprecated( identifier1 [,identifier2, ...] )
```

## <a name="remarks"></a>Açıklamalar

Derleyici tarafından belirtilen tanımlayıcı karşılaştığında bir **kullanım dışı** pragması, derleyici uyarısı verdiği [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md).

Makro adları kullanımdan. Makro adı tırnak işaretleri; Aksi takdirde makro genişletme içinde yer meydana gelir.

Çünkü **kullanım dışı** pragması, tüm eşleşen tanımlayıcılarına çalışır ve imzalar dikkate almaz, aşırı yüklenmiş işlevlerin belirli sürümler kullanım dışı bırakıldığında için en iyi seçenek değildir. Kapsama alınır tüm eşleşen işlev adı, bir uyarı tetikler.

C ++ 14 kullanmanızı öneririz `[[deprecated]]` yerine, mümkün olduğunda, öznitelik **kullanım dışı** pragması. Microsoft'a özgü [__declspec(deprecated)](../cpp/deprecated-cpp.md) bildirim değiştirici olan ayrıca birçok durumda daha iyi bir seçenek **kullanım dışı** pragması. `[[deprecated]]` Özniteliği ve `__declspec(deprecated)` değiştiricisi belirli forms aşırı yüklenmiş işlevlerin kullanım dışı durumunun belirtmenize olanak tanır. Tanılama uyarı yalnızca belirli bir aşırı yüklenmiş işlev başvuruları öznitelik görüntülenir veya değiştiricisi geçerlidir.

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

Aşağıdaki örnek, bir sınıf kullanımdan kaldırmaya gösterilmektedir:

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

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)