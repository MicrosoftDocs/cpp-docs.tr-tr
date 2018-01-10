---
title: no_auto_exclude | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_auto_exclude
dev_langs: C++
helpviewer_keywords: no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 981b67a27533f5015435965e831f7d2a86aa9948
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="noautoexclude"></a>no_auto_exclude
**C++ özel**  
  
 Otomatik dışlama devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
no_auto_exclude  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. `#import`otomatik olarak gibi öğeler hariç tutarak birden çok tanım hataları önlemek için çalışır. Bu yapıldığında, [Derleyici Uyarısı (Düzey 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) çıkarılacak her öğe için verilir. Bu öznitelik kullanarak bu otomatik dışlama devre dışı bırakabilirsiniz.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)