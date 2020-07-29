---
title: Tabanlı İşaretçiler (C++)
ms.date: 10/09/2018
f1_keywords:
- __based
- _based
- __based_cpp
helpviewer_keywords:
- __based keyword [C++]
- based pointers
- pointers, based
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
ms.openlocfilehash: a76fe56e0e6bd0501bbc3e23e138cb2e75055c73
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229148"
---
# <a name="based-pointers-c"></a>Tabanlı İşaretçiler (C++)

**`__based`** Anahtar sözcüğü işaretçiler (varolan işaretçilerden uzaklık olan işaretçiler) temelinde işaretçiler bildirmenize olanak tanır. **`__based`** Anahtar sözcüğü, Microsoft 'a özgüdür.

## <a name="syntax"></a>Sözdizimi

```
type __based( base ) declarator
```

## <a name="remarks"></a>Açıklamalar

İşaretçi adreslerini temel alan işaretçiler, **`__based`** 32-bit veya 64 bit derlemelerde geçerli olan anahtar sözcüğünün tek biçimidir. Microsoft 32 bit C/C++ derleyicisi için temel alınan bir işaretçi, 32 bit işaretçi temeline göre 32 bit uzaklıktadır. Benzer bir kısıtlama, temel alınan bir işaretçinin 64 bit temelden 64 bit uzaklıkta olduğu 64 bit ortamlar için de geçerlidir.

İşaretçilere göre işaretçilerin bir kullanımı da, işaretçiler içeren kalıcı tanımlayıcılara yöneliktir. İşaretçiye göre işaretçilerden oluşan bağlantılı bir liste diske kaydedilebilir ve daha sonra işaretçiler geçerli kalacak şekilde bellekte başka bir yere yeniden yüklenebilir. Örnek:

```cpp
// based_pointers1.cpp
// compile with: /c
void *vpBuffer;
struct llist_t {
   void __based( vpBuffer ) *vpData;
   struct llist_t __based( vpBuffer ) *llNext;
};
```

`vpBuffer` işaretçisine, programda daha sonra ayrılan belleğin adresi atanır. Bağlantılı liste, `vpBuffer` değerine göre yeniden konumlandırılır.

> [!NOTE]
> İşaretçiler içeren kalıcı tanımlayıcılar, [bellek eşlemeli dosyalar](/windows/win32/Memory/file-mapping)kullanılarak da gerçekleştirilebilir.

Temel alınan işaretçinin başvurusu kaldırılırken, temel açıkça belirtilmeli veya bildirim aracılığıyla örtük olarak bilinmelidir.

Önceki sürümlerle uyumluluk için, **_based** **`__based`** [/za \( Disable dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde _based için bir eş anlamlı.

## <a name="example"></a>Örnek

Aşağıdaki kodda, temel alınan bir işaretçinin temeli değiştirilerek değiştirilmesi gösterilmektedir.

```cpp
// based_pointers2.cpp
// compile with: /EHsc
#include <iostream>

int a1[] = { 1,2,3 };
int a2[] = { 10,11,12 };
int *pBased;

typedef int __based(pBased) * pBasedPtr;

using namespace std;
int main() {
   pBased = &a1[0];
   pBasedPtr pb = 0;

   cout << *pb << endl;
   cout << *(pb+1) << endl;

   pBased = &a2[0];

   cout << *pb << endl;
   cout << *(pb+1) << endl;
}
```

```Output
1
2
10
11
```

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[alloc_text](../preprocessor/alloc-text.md)
