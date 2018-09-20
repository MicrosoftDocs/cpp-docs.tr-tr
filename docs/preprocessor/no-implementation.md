---
title: no_implementation | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_implementation
dev_langs:
- C++
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c882a8d4eb2510969401b4280eb66116ad220c77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440842"
---
# <a name="noimplementation"></a>no_implementation
**C++ özgü**  
  
Kapsayıcı üye işlevleri uygulamalarını içeren .tli başlık oluşturulmasını bastırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
no_implementation  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Bu öznitelik belirtilmezse, .tlh üstbilgiyle türü kitaplık öğelerini göstermek için bildirimleri olmadan oluşturulan bir `#include` deyimini .tli üstbilgi dosyasını dahil edin.  
  
Bu öznitelik ile birlikte kullanılan [implementation_only](../preprocessor/implementation-only.md).  
  
**END C++ özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)