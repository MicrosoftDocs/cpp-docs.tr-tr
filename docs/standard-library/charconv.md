---
title: '&lt;charconv&gt;'
ms.date: 07/22/2020
f1_keywords:
- <charconv>
helpviewer_keywords:
- charconv header
ms.openlocfilehash: 59807749105512e0eb61acfdf60ef463febbc3a8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87246124"
---
# <a name="ltcharconvgt"></a>&lt;charconv&gt;

Bir karakter dizisini hızlı bir şekilde bir tamsayı veya kayan noktalı değere ve diğer şekilde dönüştürün.
Bu Kitaplığı kullanmanın bir yolu, JSON ve metin dosyalarındaki kayan nokta değerlerini yazmak ve bunların üzerine kaymanız.

Dönüştürme işlevleri performans için ayarlanır ve ayrıca en kısa gidiş dönüş davranışını destekler. En kısa gidiş dönüş davranışı bir sayının karakter olarak dönüştürülmesi durumunda, bu karakterleri bir kayan noktaya dönüştürürken özgün sayının kurtarılmasını sağlamak için yalnızca yeterli duyarlık yazıldığı anlamına gelir. Bu özelliği başka bir CRT veya STL işlevi sağlamaz.

Kitaplığı kullanmanın avantajlarından bazıları `<charconv>` şunlardır:

- Sayısal bir değeri temsil eden karakterlerin sırası null ile sonlandırılmış olması gerekmez. Benzer şekilde, bir sayı karakter olarak dönüştürüldüğünde, sonuç null ile Sonlandırılmamış olur.
- Dönüştürme işlevleri bellek ayırmaz. Her durumda arabelleğe sahip olursunuz.
- Dönüştürme işlevleri oluşturmamalıdır. Bunlar hata bilgilerini içeren bir yapı döndürür.
- Dönüştürmeler çalışma zamanı yuvarlama moduna duyarlı değildir.
- Dönüştürmeler yerel ayara duyarlı değildir. Virgül kullanan yerel ayarlarda her zaman ', ' olarak ondalık noktaları yazdırır ve ayrıştırır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<charconv>

**Ad alanı:** std

/std: c++ 17 veya sonraki bir sürümü gereklidir.

## <a name="members"></a>Üyeler

### <a name="types"></a>Türler

| Tür | Description |
|-|:-|
| [chars_format](chars-format-class.md) | Bilimsel, onaltılı ve benzeri biçimlendirme türlerini belirtir. |
| [from_chars_result](from-chars-result-structure.md) | Dönüştürmenin sonucunu tutar `from_chars` . |
| [to_chars_result](to-chars-result-structure.md) | Dönüştürmenin sonucunu tutar `to_chars` . |

### <a name="functions"></a>İşlevler

| İşlev | Açıklama |
|-|:-|
| [from_chars](charconv-functions.md#from_chars) | Karakterleri bir Integer, float veya Double değerine dönüştürür. |
| [to_chars](charconv-functions.md#to_chars)| Bir tamsayıyı, float veya Double 'ı karakter olarak dönüştürür. |

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)

