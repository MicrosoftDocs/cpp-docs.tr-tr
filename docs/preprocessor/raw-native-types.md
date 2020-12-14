---
description: 'Hakkında daha fazla bilgi edinin: raw_native_types Import özniteliği'
title: raw_native_types içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: 64eaadcbb3d9f07d47dd4a33bc16a222cae50f38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240539"
---
# <a name="raw_native_types-import-attribute"></a>raw_native_types içeri aktarma özniteliği

**C++ özel**

, Üst düzey sarmalayıcı işlevlerinde COM destek sınıflarının kullanımını devre dışı bırakır ve bunun yerine alt düzey veri türlerinin kullanılmasını zorlar.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **raw_native_types**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, üst düzey hata işleme yöntemleri, [](../cpp/bstr-t-class.md) ve [](../cpp/variant-t-class.md) `BSTR` `VARIANT` veri türleri ve ham com ARABIRIM işaretçileri yerine _bstr_t ve _variant_t com destek sınıflarını kullanır. Bu sınıflar, bu veri türleri için bellek depolamanın ayrılmasına ve ayrılmasına ilişkin ayrıntıları kapsüllemek ve tür atama ve dönüştürme işlemlerini büyük ölçüde basitleştirir.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
