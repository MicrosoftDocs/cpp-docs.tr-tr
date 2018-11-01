---
title: Varsayılan ad alanı
ms.date: 12/30/2016
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
ms.openlocfilehash: ffea9e1132b4c66f38661392cbafb94635b318e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558732"
---
# <a name="default-namespace"></a>Varsayılan ad alanı

`default` Ad kapsamları, C + tarafından desteklenen yerleşik türleri +/ CX.

## <a name="syntax"></a>Sözdizimi

```
namespace default;
```

### <a name="members"></a>Üyeler

Tüm yerleşik türler aşağıdaki üyelerini devralır.

|||
|-|-|
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|Bu örneğin karma kodunu döndürür.|
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|Geçerli türünü temsil eden bir dize döndürür.|
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|Geçerli türünü temsil eden bir dize döndürür.|

### <a name="built-in-types"></a>Yerleşik türler

|Ad|Açıklama|
|----------|-----------------|
|`char16`|Bir Unicode (UTF-16) kod noktasını temsil eden bir 16-bit sayısal değer.|
|`float32`|Bir 32-bit IEEE 754 kayan noktalı sayı.|
|`float64`|Bir 64-bit IEEE 754 kayan noktalı sayı.|
|`int16`|Bir 16 bitlik işaretli tamsayı.|
|`int32`|32-bit işaretli tamsayı.|
|`int64`|64-bit imzalı bir tamsayı.|
|`int8`|Bir 8 bit işaretli sayısal değer.|
|`uint16`|Bir 16 bitlik işaretsiz tamsayı.|
|`uint32`|32-bit işaretsiz bir tamsayı.|
|`uint64`|64-bit işaretsiz bir tamsayı.|
|`uint8`|Bir 8 bit işaretsiz sayısal değer.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** vccorlib.h

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)