---
title: raw_method_prefix | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_method_prefix
dev_langs: C++
helpviewer_keywords: raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3cc417466308480ba6a10c5e0bfe190d172f366f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**C++ özel**  
  
 Ad çakışmaları önlemek için farklı bir önek belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Prefix`  
 Kullanılacak önek.  
  
## <a name="remarks"></a>Açıklamalar  
 Alt düzey özellikleri ve yöntemleri açığa varsayılan öneki adlı üye işlevleri tarafından **raw_** üst düzey hata işleme üye işlevleri ile ad çakışmaları önlemek için.  
  
> [!NOTE]
>  Etkilerini `raw_method_prefix` özniteliği varlığını tarafından değiştirilmeyecek [raw_interfaces_only](#_predir_raw_interfaces_only) özniteliği. `raw_method_prefix` Her zaman önceliklidir `raw_interfaces_only` içinde bir önek belirtme. Her iki öznitelik aynı kullanılıyorsa `#import` deyimi sonra tarafından belirtilen önek `raw_method_prefix` özniteliği kullanılır.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)