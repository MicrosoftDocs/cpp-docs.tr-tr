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
ms.openlocfilehash: a14ef9043ec2196ff930a37d0eff95e90024d3d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244167"
---
# <a name="uuidof-operator"></a>__uuidof İşleci

**Microsoft'a özgü**

İfade iliştirilen GUID alır.

## <a name="syntax"></a>Sözdizimi

```
__uuidof (expression)
```

## <a name="remarks"></a>Açıklamalar

*İfade* , bu tür veya bu tür bir değişken şablon özel bir tür adı, işaretçi, başvuru veya dizi türünde olabilir. Derleyici iliştirilen GUID bulmak için kullanabileceğiniz sürece bağımsız değişken geçerli değil.

Bu iç özel bir durum olduğunda ya da **0** veya NULL bağımsız değişken olarak sağlanır. Bu durumda, **__uuidof** sıfırlardan oluşan bir GUID değerini döndürür.

Bağlı GUID ayıklamak için bu anahtar sözcük kullanın:

- Bir nesne tarafından [UUID](../cpp/uuid-cpp.md) genişletilmiş öznitelik.

- Bir kitaplık bloğu ile oluşturulan [Modülü](../windows/attributes/module-cpp.md) özniteliği.

> [!NOTE]
> Hata ayıklama derlemesinde **__uuidof** her zaman zamanında dinamik olarak () bir nesneyi başlatır. Derleme, **__uuidof** statik (derleme zamanında) nesneyi başlatabilirsiniz.

Önceki sürümlerle uyumluluk için **_uuidof** eşanlamlıdır **__uuidof** sürece derleyici seçeneği [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) olduğu Belirtilen.

## <a name="example"></a>Örnek

Modül özniteliği ile oluşturulan bir kitaplığı blok UUID'si (ole32.lib ile derlenmiş) aşağıdaki kodu görüntüler:

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

## <a name="comments"></a>Açıklamalar

Kitaplık adı olduğu artık kapsamda durumlarda kullanabilirsiniz `__LIBID_` yerine **__uuidof**. Örneğin:

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)