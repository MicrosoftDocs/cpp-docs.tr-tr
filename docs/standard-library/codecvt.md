---
title: '&lt;codecvt&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- codecvt
- <codecvt>
dev_langs:
- C++
helpviewer_keywords:
- codecvt header
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 97a8ef1f8ba49da54e106886f1e3cf488049f92d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltcodecvtgt"></a>&lt;Codecvt&gt;

Şablon sınıfına dayalı nesneler tanımlar birkaç şablon sınıfları tanımlar [codecvt](../standard-library/codecvt-class.md). Bu nesneler olarak hizmet verebilir [yerel ayar modelleri](../standard-library/locale-class.md#facet_class) kontrol eden bir dizi türü değerleri arasında dönüştürme `Elem` ve bir dizi türü değerleri `char`.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <codecvt>

```

## <a name="remarks"></a>Açıklamalar

Bu başlığında bildirilen yerel modelleri arasında birkaç karakter kodlamaları dönüştürün. Geniş karakterler (sabit boyutlu tamsayı programa içinde depolanan) için:

- UCS-4 bir 32 bit tamsayı olarak programından kodlanmış Unicode (ISO 10646) olur.

- UCS-2 bir 16 bit tamsayı olarak programından kodlanmış Unicode gösterilir.

- UTF-16 programın içinde bir veya iki 16 bit tamsayı olarak kodlanmış Unicode ' dir. (Bu geçerli bir joker karakter standart C ya da standart C++ için kodlamada tüm gereksinimleri karşılamıyor unutmayın. Yine de bu yaygın şekilde kullanılır.)

Bayt akışları için (bir dosyada depolanan, bir bayt dizisi aktarılan veya bir dizi programa içinde depolanan `char`):

- UTF-8 bayt akışı içinde belirleyici bayt sırasına sahip bir veya daha fazla sekiz bit bayt olarak kodlanmış Unicode ' dir.

- UTF-16LE Unicode bayt akış UTF-16 olarak içinde kodlanmış olan ilk daha az önemli bayt iki sekiz bit bayt olarak sunulan her 16 bit tamsayı değerine sahip.

- UTF-16BE Unicode bayt akış UTF-16 olarak içinde kodlanmış olan ilk daha önemli bayt iki sekiz bit bayt sunulan her 16 bit tamsayı değerine sahip.

### <a name="enumerations"></a>Numaralandırmalar

|||
|-|-|
|[codecvt_mode](../standard-library/codecvt-enums.md#codecvt_mode)|Yerel ayar modelleri için yapılandırma bilgilerini belirtir.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[codecvt_utf8](codecvt-utf8-class.md)|Geniş karakterler UCS-2 veya 4 UCS olarak kodlanmış UTF-8 olarak kodlanmış bir bayt akışı arasındaki dönüştürür bir yerel ayar modeli temsil eder.|
|[codecvt_utf8_utf16](codecvt-utf8-utf16-class.md)|Geniş karakterler UTF-16 kodlanmış UTF-8 olarak kodlanmış bir bayt akışı arasındaki dönüştürür bir yerel ayar modeli temsil eder.|
|[codecvt_utf16](codecvt-utf16-class.md)|Geniş karakterler UCS-2 veya 4 UCS olarak kodlanmış UTF-16LE veya UTF-16BE olarak kodlanmış bir bayt akışı arasındaki dönüştürür bir yerel ayar modeli temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<codecvt >

**Namespace:** stdt

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
