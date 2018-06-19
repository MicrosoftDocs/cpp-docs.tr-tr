---
title: high_property_prefixes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7269301fed3892fbf4b7cf6427bacb82d9712ef7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849395"
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