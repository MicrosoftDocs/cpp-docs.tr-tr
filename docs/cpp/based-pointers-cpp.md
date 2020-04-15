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
ms.openlocfilehash: 24c3a7f85c4ea05c38f3ab1d3f637ea0ab24d4c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363754"
---
# <a name="based-pointers-c"></a>Tabanlı İşaretçiler (C++)

**__based** anahtar kelimesi işaretçileri (varolan işaretçilerden uzaklıkolan işaretçiler) temel alından işaretçileri beyan etmenizi sağlar. __based **__based** anahtar kelimesi Microsoft'a özgüdür.

## <a name="syntax"></a>Sözdizimi

```
type __based( base ) declarator
```

## <a name="remarks"></a>Açıklamalar

İşaretçi adreslerine dayalı işaretçiler, 32 bit veya 64 bit derlemelerde geçerli olan **__based** anahtar kelimenin tek biçimidir. Microsoft 32 bit C/C++ derleyicisi için temel alınan bir işaretçi, 32 bit işaretçi temeline göre 32 bit uzaklıktadır. Benzer bir kısıtlama, temel alınan bir işaretçinin 64 bit temelden 64 bit uzaklıkta olduğu 64 bit ortamlar için de geçerlidir.

İşaretçilere göre işaretçilerin bir kullanımı da, işaretçiler içeren kalıcı tanımlayıcılara yöneliktir. İşaretçiye göre işaretçilerden oluşan bağlantılı bir liste diske kaydedilebilir ve daha sonra işaretçiler geçerli kalacak şekilde bellekte başka bir yere yeniden yüklenebilir. Örneğin:

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
> İşaretçiler içeren kalıcı tanımlayıcılar da [bellek eşlenen dosyaları](/windows/win32/Memory/file-mapping)kullanılarak gerçekleştirilebilir.

Temel alınan işaretçinin başvurusu kaldırılırken, temel açıkça belirtilmeli veya bildirim aracılığıyla örtük olarak bilinmelidir.

Önceki sürümlerle uyumluluk için **_based,** derleyici seçeneği [/Za \(Dil uzantıları)](../build/reference/za-ze-disable-language-extensions.md) belirtilmedikçe **__based** eşanlamlıdır.

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
