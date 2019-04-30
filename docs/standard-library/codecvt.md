---
title: '&lt;codecvt&gt;'
ms.date: 11/04/2016
f1_keywords:
- codecvt
- <codecvt>
helpviewer_keywords:
- codecvt header
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
ms.openlocfilehash: 56cd4263d3dcddd23246a05466275b8b7d370b95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405215"
---
# <a name="ltcodecvtgt"></a>&lt;codecvt&gt;

Şablon sınıfına göre nesnelerini açıklamaya birkaç şablon sınıfları tanımlar [codecvt](../standard-library/codecvt-class.md). Bu nesneler olarak hizmet verebilen [yerel ayar modelleri](../standard-library/locale-class.md#facet_class) türü değerler dizisi arasındaki dönüştürmeleri denetlemek `Elem` türü değerler dizisi **char**.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <codecvt>
```

## <a name="remarks"></a>Açıklamalar

Bu üstbilgisinde bildirilen yerel ayar modelleri birkaç karakter kodlamaları arasından dönüştürme. Geniş karakterler (sabit boyutlu tamsayı programa içinde depolanan):

- UCS-4 programında bir 32 bit tamsayı olarak kodlanmış Unicode (ISO 10646) ' dir.

- UCS-2 programında bir 16 bit tam sayı olarak kodlanmış bir Unicode gösterilir.

- UTF-16 Unicode program içindeki bir veya iki 16 bit tamsayılar olarak kodlanmış ' dir. (Bu, geçerli bir geniş karakter standart C veya C++ Standart kodlamada tüm gereksinimlerini karşılamıyor unutmayın. Bununla birlikte, yaygın şekilde kullanılır.)

Bayt akışları için (bir dosyada depolanır, bir bayt dizisi aktarılan veya bir dizi program içinde depolanan **char**):

- İçinde bayt akışı belirleyici bayt sırasına sahip bir veya daha fazla sekiz bitlik bayt olarak kodlanmış bir Unicode UTF-8 kodlamasıdır.

- İçinde bayt akışı olarak UTF-16 kodlamalı Unicode UTF-16LE olan ilk az önemli bayt iki sekiz bitlik bayt olarak sunulan her 16-bit tamsayı değerine sahip.

- İçinde bayt akışı olarak UTF-16 kodlamalı Unicode UTF-16BE türlerinden olan ilk iki sekiz bitlik bayt cinsinden daha önemli bayt sunulan her 16-bit tamsayı değerine sahip.

### <a name="enumerations"></a>Numaralandırmalar

|||
|-|-|
|[codecvt_mode](../standard-library/codecvt-enums.md#codecvt_mode)|Yerel ayar modelleri için yapılandırma bilgilerini belirtir.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[codecvt_utf8](codecvt-utf8-class.md)|UTF-8 olarak kodlanmış bir bayt akışı yanı sıra UCS-2 veya UCS-4 olarak kodlanmış geniş karakterler arasında dönüştürür bir yerel ayar modeli temsil eder.|
|[codecvt_utf8_utf16](codecvt-utf8-utf16-class.md)|UTF-16 olarak kodlanmış geniş karakterler ve UTF-8 olarak kodlanmış bir bayt akışı arasında dönüştürür bir yerel ayar modeli temsil eder.|
|[codecvt_utf16](codecvt-utf16-class.md)|Geniş karakterler UCS-2 veya UCS-4 olarak kodlanan ve UTF-16LE veya UTF-16BE türlerinden olarak kodlanmış bir bayt akışı arasında dönüştürür bir yerel ayar modeli temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<codecvt >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
