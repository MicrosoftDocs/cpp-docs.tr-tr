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
ms.openlocfilehash: 09348d061fde4cb09eb6eb351f146404f355e184
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187797"
---
# <a name="__uuidof-operator"></a>__uuidof İşleci

**Microsoft 'a özgü**

İfadeye eklenmiş GUID 'YI alır.

## <a name="syntax"></a>Sözdizimi

```
__uuidof (expression)
```

## <a name="remarks"></a>Açıklamalar

*İfade* bir tür adı, işaretçi, başvuru veya bu türün dizisi, bu türlerde özelleştirilmiş bir şablon veya bu türlerin bir değişkeni olabilir. Bağımsız değişken, derleyicinin ekli GUID 'yi bulmak için kullanabileceği sürece geçerli olur.

Bu iç özel durum, bağımsız değişken olarak **0** veya null sağlanmalıdır. Bu durumda **__uuidof** , sıfırlardan oluşan bir GUID döndürür.

Bu anahtar sözcüğü kullanarak iliştirilmiş GUID 'yi ayıklayın:

- [UUID](../cpp/uuid-cpp.md) genişletilmiş özniteliği tarafından bir nesne.

- [Modül](../windows/attributes/module-cpp.md) özniteliğiyle oluşturulmuş bir kitaplık bloğu.

> [!NOTE]
> Bir hata ayıklama derlemesinde **__uuidof** her zaman bir nesneyi dinamik olarak başlatır (çalışma zamanında). Bir yayın derlemesinde, **__uuidof** statik olarak (derleme zamanında) bir nesne başlatabilir.

Önceki sürümlerle uyumluluk için, [/za \(dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, **_uuidof** **__uuidof** için bir eş anlamlı.

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

Kitaplık adının artık kapsamda olmadığı durumlarda, **__uuidof**yerine `__LIBID_` kullanabilirsiniz. Örneğin:

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
