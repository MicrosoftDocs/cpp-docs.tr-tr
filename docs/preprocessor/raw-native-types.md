---
title: raw_native_types | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_native_types
dev_langs:
- C++
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4739b8664da21a86caa91398a7956eac77e22f3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072895"
---
# <a name="rawnativetypes"></a>raw_native_types
**C++ özgü**

COM desteği sınıfları üst düzey sarmalayıcı işlevlerindeki kullanımını devre dışı bırakır ve bunun yerine alt düzey veri türleri kullanılmasını zorlar.

## <a name="syntax"></a>Sözdizimi

```
raw_native_types
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, üst düzey hata işleme yöntem COM desteği sınıfları kullanın [_bstr_t](../cpp/bstr-t-class.md) ve [_variant_t](../cpp/variant-t-class.md) yerine `BSTR` ve `VARIANT` veri türleri ve ham COM arabirim işaretçisi. Bu sınıflar, ayırma ve bu veri türleri için bellek depolama ayırmayı kaldırma işlemlerinin ayrıntılarını kapsüllemek ve tür atama ve dönüştürme işlemlerini önemli ölçüde basitleştirir.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)