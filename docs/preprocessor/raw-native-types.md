---
title: raw_native_types içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: eb08a8e7cb081bd7a470c3c1ecf1492a7a65f833
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216062"
---
# <a name="raw_native_types-import-attribute"></a>raw_native_types içeri aktarma özniteliği

**C++Belirli**

, Üst düzey sarmalayıcı işlevlerinde COM destek sınıflarının kullanımını devre dışı bırakır ve bunun yerine alt düzey veri türlerinin kullanılmasını zorlar.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **raw_native_types**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, üst düzey hata işleme yöntemleri, `BSTR` ve `VARIANT` veri türleri ve ham com arabirim işaretçileri yerine [_bstr_t](../cpp/bstr-t-class.md) ve [_variant_t](../cpp/variant-t-class.md) com destek sınıflarını kullanır. Bu sınıflar, bu veri türleri için bellek depolamanın ayrılmasına ve ayrılmasına ilişkin ayrıntıları kapsüllemek ve tür atama ve dönüştürme işlemlerini büyük ölçüde basitleştirir.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
