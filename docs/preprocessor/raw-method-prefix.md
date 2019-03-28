---
title: raw_method_prefix
ms.date: 03/27/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: c3015cf8b51646d25fd8f36a7336c63dc8fe492b
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565603"
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
> Etkilerini **raw_method_prefix** özniteliği varlığını tarafından değiştirilmeyecek [raw_interfaces_only](raw-interfaces-only.md) özniteliği. **Raw_method_prefix** her zaman önceliklidir `raw_interfaces_only` belirtilirken bir önek. Her iki öznitelik aynı kullanılıyorsa `#import` ifade, sonra tarafından belirtilen önek **raw_method_prefix** özniteliği kullanılır.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)