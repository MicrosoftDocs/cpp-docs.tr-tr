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
ms.openlocfilehash: 5baa3204b14da53f6a6a3232874e0ac7de0fd91b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849801"
---
# <a name="rawnativetypes"></a>raw_native_types
**C++ özel**  
  
 COM desteği sınıfları üst düzey sarmalayıcı işlevlerinde kullanımını devre dışı bırakır ve bunun yerine alt düzey veri türlerinin zorlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
raw_native_types  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, üst düzey hata işleme yöntemlerini COM desteği sınıfları kullanır [_bstr_t](../cpp/bstr-t-class.md) ve [_variant_t](../cpp/variant-t-class.md) yerine `BSTR` ve **değişken** veri türleri ve Ham COM arabirimi işaretçisi. Bu sınıfların ayırma ve bu veri türleri için bellek depolama serbest bırakma ayrıntılarını şifreleyebilir ve tür atama ve dönüştürme işlemlerini büyük ölçüde basitleştirebilir.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)