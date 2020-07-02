---
title: '&lt;kapsamı&gt;'
ms.date: 05/28/2020
f1_keywords:
- <span>
helpviewer_keywords:
- span header
ms.openlocfilehash: 27f27acfa84a3ccc42586593747e4657146cbe39
ms.sourcegitcommit: 83ea5df40917885e261089b103d5de3660314104
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85813541"
---
# <a name="ltspangt"></a>&lt;kapsamı&gt;

`span`, Bitişik nesne dizisi üzerinde bir görünümdedir. Hızlı ve sınırlara güvenli erişim sağlar. Ya da aksine `vector` `array` , erişimi sağladığı öğeleri "sahip" değildir.

Ayrıntılı bilgi için bkz. [Span sınıfı](span-class.md) . Bu, bir yayılma alanının nasıl kullanılacağına ilişkin bir örnek aşağıda verilmiştir:

```cpp
#include <span>
#include <iostream>

void Show(std::span<int> someValues)
{
    // show values in reverse
    for (auto rIt = someValues.rbegin(); rIt != someValues.rend(); ++rIt)
    {
        std::cout << *rIt;
    }

    // show a subspan
    for (auto& i : someValues.subspan(1, 2))
    {
        std::cout << i;
    }
}

int main()
{
    int numbers[]{ 0,1,2,3,4 };
    Show(numbers); // note conversion from array to span
}
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<span>

**Ad alanı:** std

**Derleyici seçeneği:** /std: c + + en son

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|:-|
|[kapsamı](span-class.md)| Bitişik nesne dizisi üzerinde bir görünüm sağlar. |

### <a name="operators"></a>İşleçler

|||
|-|:-|
|[işleç =](span-class.md#op_eq)| Span ataması |
|[işlecinde\[\]](span-class.md#op_at)| Öğe erişimi |

### <a name="functions"></a>İşlevler

|||
|-|:-|
| [as_bytes](span-functions.md#as_bytes)| Yayılma alanının temeldeki salt okunan baytlarını alın. |
| [as_writable_bytes](span-functions.md#as_writable_bytes) | Yayılma alanının temelindeki baytları alın. |

### <a name="constants"></a>Sabitler

|||
|-|:-|
| **dynamic_extent** | Yayılma boyutunun derleme zamanı yerine çalışma zamanında belirlendiğini gösterir. Yayılma alanındaki öğe sayısı derleme zamanında bilindiğinde, `Extent` şablon parametresi olarak belirtilir. Sayı, çalışma zamanına kadar bilinmiyorsa, `dynamic_extent` bunun yerine belirtin. |

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
