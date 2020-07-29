---
title: __uuidof İşleci
ms.date: 10/10/2018
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
- __uuidof
- _uuidof
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
ms.openlocfilehash: f7564270408d14f58d1528c1f41c0afd2dbe219c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226977"
---
# <a name="__uuidof-operator"></a>`__uuidof` İşleci

**Microsoft'a Özgü**

İfadeye eklenmiş GUID 'YI alır.

## <a name="syntax"></a>Sözdizimi

> **`__uuidof (`***ifade***`)`**

## <a name="remarks"></a>Açıklamalar

*İfade* bir tür adı, işaretçi, başvuru veya bu türün dizisi, bu türlerde özelleştirilmiş bir şablon veya bu türlerin bir değişkeni olabilir. Bağımsız değişken, derleyicinin ekli GUID 'yi bulmak için kullanabileceği sürece geçerli olur.

Bu iç özel durum, bağımsız değişken olarak **0** veya null sağlanmalıdır. Bu durumda, **`__uuidof`** sıfırlardan oluşan BIR GUID döndürülür.

Bu anahtar sözcüğü kullanarak iliştirilmiş GUID 'yi ayıklayın:

- Genişletilmiş özniteliğe göre bir nesne [`uuid`](../cpp/uuid-cpp.md) .

- Özniteliği ile oluşturulmuş bir kitaplık bloğu [`module`](../windows/attributes/module-cpp.md) .

> [!NOTE]
> Bir hata ayıklama derlemesinde, **`__uuidof`** her zaman bir nesneyi dinamik olarak başlatır (çalışma zamanında). Bir yayın derlemesinde, **`__uuidof`** statik olarak (derleme zamanında) bir nesne başlatabilir.

Önceki sürümlerle uyumluluk için, **`_uuidof`** **`__uuidof`** derleyici seçeneği [ `/Za` \( dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) ' ın belirtildiği durumlar için bir eş anlamlı olur.

## <a name="example"></a>Örnek

Aşağıdaki kod (Ole32. lib ile derlenen), Module özniteliğiyle oluşturulan bir kitaplık bloğunun UUID 'sini görüntüler:

```cpp
// expre_uuidof.cpp
// compile with: ole32.lib
#include "stdio.h"
#include "windows.h"

[emitidl];
[module(name="MyLib")];
[export]
struct stuff {
   int i;
};

int main() {
   LPOLESTR lpolestr;
   StringFromCLSID(__uuidof(MyLib), &lpolestr);
   wprintf_s(L"%s", lpolestr);
   CoTaskMemFree(lpolestr);
}
```

## <a name="comments"></a>Yorumlar

Kitaplık adının artık kapsamda olmadığı durumlarda, `__LIBID_` yerine kullanabilirsiniz **`__uuidof`** . Örnek:

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
