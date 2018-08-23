---
title: no_auto_exclude | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_auto_exclude
dev_langs:
- C++
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5cae3a52c3434317ee26292de13d3e0471d78998
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42464959"
---
# <a name="noautoexclude"></a>no_auto_exclude
**C++ özgü**  
  
Otomatik dışlama devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
no_auto_exclude  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. `#import` otomatik olarak gibi öğeler hariç tutarak birden çok tanım hatalarını önlemek çalışır. Bu yapıldığında, [Derleyici Uyarısı (Düzey 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) çıkarılacak her öğe için verilir. Bu özniteliği kullanarak bu otomatik dışlama devre dışı bırakabilirsiniz.  
  
**END C++ özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)