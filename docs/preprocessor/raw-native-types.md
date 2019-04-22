---
title: raw_native_types
ms.date: 11/04/2016
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: 32b77905ef7025334e5101e76864da9a15c50cf6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024974"
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

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)