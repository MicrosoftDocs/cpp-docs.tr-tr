---
title: raw_method_prefix | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fb9178bc315385bab97cea473430745ad66d973
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465597"
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**C++ özgü**  
  
Ad çakışmalarını önlemek için farklı bir ön ekini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
raw_method_prefix("Prefix")  
```  
  
### <a name="parameters"></a>Parametreler  
*Ön eki*  
Kullanılacak önek.  
  
## <a name="remarks"></a>Açıklamalar  
 
Varsayılan öneki ile adlandırılan üye işlevleri tarafından düşük düzeydeki özellikleri ve yöntemleri sunulur **raw_** üst düzey hata işleme üye işlevleri ile ad çakışmalarını önlemek için.  
  
> [!NOTE]
> Etkilerini **raw_method_prefix** özniteliği varlığını tarafından değiştirilmeyecek [raw_interfaces_only](#_predir_raw_interfaces_only) özniteliği. **Raw_method_prefix** her zaman önceliklidir `raw_interfaces_only` belirtilirken bir önek. Her iki öznitelik aynı kullanılıyorsa `#import` ifade, sonra tarafından belirtilen önek **raw_method_prefix** özniteliği kullanılır.  
  
**END C++ özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)