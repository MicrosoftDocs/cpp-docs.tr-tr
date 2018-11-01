---
title: raw_method_prefix
ms.date: 10/18/2018
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: 4169b4e23049bf1cf2c61eaefba619169e0ce377
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467779"
---
# <a name="rawmethodprefix"></a>raw_method_prefix

**C++ özgü**

Ad çakışmalarını önlemek için farklı bir ön ekini belirtir.

## <a name="syntax"></a>Sözdizimi

```
raw_method_prefix("Prefix")
```

### <a name="parameters"></a>Parametreler

*Ön eki*<br/>
Kullanılacak önek.

## <a name="remarks"></a>Açıklamalar

Varsayılan öneki ile adlandırılan üye işlevleri tarafından düşük düzeydeki özellikleri ve yöntemleri sunulur **raw_** üst düzey hata işleme üye işlevleri ile ad çakışmalarını önlemek için.

> [!NOTE]
> Etkilerini **raw_method_prefix** özniteliği varlığını tarafından değiştirilmeyecek [raw_interfaces_only](#_predir_raw_interfaces_only) özniteliği. **Raw_method_prefix** her zaman önceliklidir `raw_interfaces_only` belirtilirken bir önek. Her iki öznitelik aynı kullanılıyorsa `#import` ifade, sonra tarafından belirtilen önek **raw_method_prefix** özniteliği kullanılır.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)