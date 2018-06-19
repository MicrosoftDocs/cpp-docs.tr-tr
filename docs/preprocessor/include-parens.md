---
title: include() | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- include()
dev_langs:
- C++
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 756aea4400d98b2bf061a54955b3df4b4eddd993
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849281"
---
# <a name="include"></a>include()
**C++ özel**  
  
 Otomatik dışlama devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Name1`  
 Zorla dahil edilecek ilk öğe.  
  
 `Name2`  
 (Gerekiyorsa) zorla dahil edilmek üzere ikinci öğe.  
  
## <a name="remarks"></a>Açıklamalar  
 Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. `#import` otomatik olarak gibi öğeler hariç tutarak birden çok tanım hataları önlemek için çalışır. Öğe, belirtilen şekilde tutulan varsa [Derleyici Uyarısı (Düzey 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), ve sahip olmamalıdır olup, bu öznitelik, otomatik dışlama devre dışı bırakmak için kullanılabilir. Bu öznitelik her dahil edilmesi için tür kitaplığı öğesinin adı olan herhangi bir sayıda bağımsız değişken alabilir.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)