---
title: include() | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: include()
dev_langs: C++
helpviewer_keywords: include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d9879bbdeed7e511188c334564d101e728003ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. `#import`otomatik olarak gibi öğeler hariç tutarak birden çok tanım hataları önlemek için çalışır. Öğe, belirtilen şekilde tutulan varsa [Derleyici Uyarısı (Düzey 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), ve sahip olmamalıdır olup, bu öznitelik, otomatik dışlama devre dışı bırakmak için kullanılabilir. Bu öznitelik her dahil edilmesi için tür kitaplığı öğesinin adı olan herhangi bir sayıda bağımsız değişken alabilir.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)