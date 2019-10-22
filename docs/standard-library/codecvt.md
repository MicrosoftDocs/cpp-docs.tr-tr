---
title: '&lt;codecvt &gt;'
ms.date: 11/04/2016
f1_keywords:
- codecvt
- <codecvt>
helpviewer_keywords:
- codecvt header
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
ms.openlocfilehash: 972672e80ce4f82402296317c75e35dcd10c9e93
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688278"
---
# <a name="ltcodecvtgt"></a>&lt;codecvt &gt;

[Codecvt](../standard-library/codecvt-class.md)sınıf şablonunu temel alan nesneleri tanımlayan çeşitli sınıf şablonları tanımlar. Bu nesneler, `Elem` türünde bir değer dizisi ve **char**türünde bir değer dizisi arasındaki dönüştürmeleri denetleyen [yerel ayar modelleri](../standard-library/locale-class.md#facet_class) olarak işlev görebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <codecvt>
```

## <a name="remarks"></a>Açıklamalar

Bu üst bilgide belirtilen yerel ayar modelleri çeşitli karakter kodlamaları arasında dönüştürülür. Geniş karakterler için (sabit boyutlu tamsayılarla program içinde depolanır):

- UCS-4, program içinde 32 bit tam sayı olarak kodlanmış Unicode 'dur (ISO 10646).

- UCS-2, program içinde 16 bit tam sayı olarak kodlanmış Unicode 'dur.

- UTF-16, program içinde bir veya 2 16 bitlik tamsayılar olarak kodlanmış Unicode 'dur. (Bu, standart C veya standart C++için geçerli bir geniş karakter kodlamasının tüm gereksinimlerini karşılamaz. Yine de bu şekilde yaygın olarak kullanılır.)

Bayt akışları için (bir dosyada depolanır, bir bayt dizisi olarak iletilir veya bir **char**dizisinde program içinde depolanır):

- UTF-8, bir bayt akışı içinde, belirleyici bayt düzeninde bir veya daha fazla sekiz bitlik bayt olarak kodlanmış Unicode 'dur.

- UTF-16LE, her 16 bit tam sayı olarak 2 8 bit bayt olarak sunulan ve ilk olarak daha az önemli bayt olarak bir bayt akışı içinde UTF-16 olarak kodlanmış Unicode olarak kodlanır.

- UTF-16, bir bayt akışı içinde Unicode, her 16 bit tamsayıyla 2 8 bit bayt olarak sunulan UTF-16 olarak kodlanır ve öncelikle daha önemli bir bayt olur.

### <a name="enumerations"></a>Numaralandırmalar

|||
|-|-|
|[codecvt_mode](../standard-library/codecvt-enums.md#codecvt_mode)|Yerel ayar modelleri için yapılandırma bilgilerini belirtir.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[codecvt_utf8](codecvt-utf8-class.md)|UCS-2 veya UCS-4 olarak kodlanan geniş karakterler arasında dönüştürme yapan bir yerel ayar modeli ve UTF-8 olarak kodlanmış bir bayt akışı temsil eder.|
|[codecvt_utf8_utf16](codecvt-utf8-utf16-class.md)|UTF-16 olarak kodlanmış geniş karakterler ve UTF-8 olarak kodlanmış bir bayt akışı arasında dönüştüren bir yerel ayar modeli temsil eder.|
|[codecvt_utf16](codecvt-utf16-class.md)|UCS-2 veya UCS-4 olarak kodlanmış geniş karakterler ve UTF-16LE veya UTF-16AS olarak kodlanmış bir bayt akışı arasında dönüştürme yapan bir yerel ayar modeli temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<codecvt >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
