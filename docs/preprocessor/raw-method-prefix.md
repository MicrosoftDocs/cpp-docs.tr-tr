---
title: raw_method_prefix | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78094053c963f5d836646e91857e171625c447c9
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808556"
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