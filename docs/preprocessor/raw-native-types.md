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
ms.openlocfilehash: b09e36e793608167a4ce64a9124d7dafbaf9ec62
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465966"
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
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)