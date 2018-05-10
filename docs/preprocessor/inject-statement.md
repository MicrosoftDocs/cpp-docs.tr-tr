---
title: inject_statement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 115f5b3d7012ae3e9073d81e0c1005dcb513e045
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)