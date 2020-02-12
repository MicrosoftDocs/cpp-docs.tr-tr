---
title: Karma&lt;string_view&gt; özelleştirmesi
ms.date: 04/19/2019
f1_keywords:
- xstring/basic_string_view::hash
helpviewer_keywords:
- std::basic_string_view::hash
ms.openlocfilehash: 7a69473b6fe39655e7cf3154671017c39c453e29
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126181"
---
# <a name="hashltstring_viewgt-specialization"></a>Karma&lt;string_view&gt; özelleştirmesi

String_view verilen bir karma değer üreten şablon özelleştirmesi.

```cpp
template <class CharType, class Traits>
struct hash<basic_string_view<CharType, Traits>>
{
    typedef basic_string_view<CharType, Traits> argument_type;
    typedef size_t result_type;

    size_t operator()(const basic_string_view<CharType, Traits>) const
        noexcept;
};
```
### <a name="remarks"></a>Açıklamalar

Bir string_view karması, temeldeki dize nesnesinin karmasından eşittir.

### <a name="example"></a>Örnek

```cpp
//compile with: /std:c++17
#include <string>
#include <string_view>
#include <iostream>

using namespace std;

int main()
{
    string_view sv{ "Hello world" };
    string s{ "Hello world" };
    cout << boolalpha << (hash<string_view>{}(sv)
        == hash<string>{}(s)); // true
}
```