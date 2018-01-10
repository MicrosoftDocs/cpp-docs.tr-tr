---
title: raw_native_types | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_native_types
dev_langs: C++
helpviewer_keywords: raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cdd40f219115adf43f0681d8719aceb9ed9d9fd2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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