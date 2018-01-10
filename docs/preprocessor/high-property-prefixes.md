---
title: high_property_prefixes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: high_property_prefixes
dev_langs: C++
helpviewer_keywords: high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed37cdc51c5e08899786ce82a9c3e5e3224f9f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**C++ özel**  
  
 Diğer özellik yöntemi için alternatif önekler belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>Parametreler  
 `GetPrefix`  
 Kullanılacak önek **propget** yöntemleri.  
  
 `PutPrefix`  
 Kullanılacak önek **propput** yöntemleri.  
  
 `PutRefPrefix`  
 Kullanılacak önek **propputref** yöntemleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, üst düzey hata işleme **propget**, **propput**, ve **propputref** yöntemleri öneklerle adlı üye işlevleri tarafından açığa **Al** , `Put`, ve **PutRef**sırasıyla.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)