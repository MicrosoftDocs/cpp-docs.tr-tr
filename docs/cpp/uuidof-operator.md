---
title: __uuidof işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
dev_langs:
- C++
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84fd779d50fb481cffc97b61a65f255c6c8f52a1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056748"
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

- Bir kitaplık bloğu ile oluşturulan [Modülü](../windows/module-cpp.md) özniteliği.

> [!NOTE]
>  Hata ayıklama derlemesinde **__uuidof** her zaman zamanında dinamik olarak () bir nesneyi başlatır. Derleme, **__uuidof** statik (derleme zamanında) nesneyi başlatabilirsiniz.

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