---
title: varsayılan ad alanı
ms.date: 12/30/2016
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
ms.openlocfilehash: b67aedc791ed41e93268d9e9f44492781940d55e
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740509"
---
# <a name="default-namespace"></a>varsayılan ad alanı

Ad `default` alanı,/cxtarafından C++desteklenen yerleşik türleri kapsamlar.

## <a name="syntax"></a>Sözdizimi

```
namespace default;
```

### <a name="members"></a>Üyeler

Tüm yerleşik türler aşağıdaki üyeleri devralınır.

|||
|-|-|
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|Bu örneğin karma kodunu döndürür.|
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|Geçerli türü temsil eden bir dize döndürür.|
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|Geçerli türü temsil eden bir dize döndürür.|

### <a name="built-in-types"></a>Yerleşik türler

|Ad|Açıklama|
|----------|-----------------|
|`char16`|Unicode (UTF-16) kod noktasını temsil eden 16 bit sayısal sayısal bir değer.|
|`float32`|32 bitlik bir IEEE 754 kayan noktalı sayı.|
|`float64`|64 bitlik bir IEEE 754 kayan noktalı sayı.|
|`int16`|16 bit işaretli tamsayı.|
|`int32`|32 bitlik işaretli tamsayı.|
|`int64`|64 bitlik işaretli tamsayı.|
|`int8`|8 bit işaretli sayısal değer.|
|`uint16`|16 bitlik işaretsiz tamsayı.|
|`uint32`|32 bitlik işaretsiz tamsayı.|
|`uint64`|64 bitlik işaretsiz tamsayı.|
|`uint8`|8 bit işaretsiz sayısal değer.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** vccorlib. h

## <a name="see-also"></a>Ayrıca bkz.

[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)
