---
title: inject_statement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7dacc2867b767495c608789b9efbe23bf7aa7110
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="injectstatement"></a>inject_statement
**C++ özel**  
  
 Bağımsız değişkenini tür kitaplığı üstbilgisine kaynak metin olarak ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inject_statement("source_text")  
```  
  
#### <a name="parameters"></a>Parametreler  
 `source_text`  
 Tür kitaplığı üstbilgi dosyasına eklenecek kaynak metin.  
  
## <a name="remarks"></a>Açıklamalar  
 Metin, üstbilgi dosyasında tür kitaplığı içeriğini saran ad alanı bildiriminin başına yerleştirilir.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)