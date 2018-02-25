---
title: raw_native_types | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- raw_native_types
dev_langs:
- C++
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4908f1f06ef0479121d3ec5ac8fa56a797ed05ca
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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
  
 Son C++ özel  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)