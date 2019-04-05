---
title: raw_method_prefix
ms.date: 03/27/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: 963e04752dcb797343550d9b89f778bfe0e8a593
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59021417"
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

## <a name="see-also"></a>Ayrıca bkz.

[#import Öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Yönergesi](../preprocessor/hash-import-directive-cpp.md)