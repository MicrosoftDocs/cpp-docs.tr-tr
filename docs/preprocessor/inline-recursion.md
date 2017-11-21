---
title: inline_recursion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs: C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 36d7d65ea6c36c81654feda020fc05d777ac3d33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="inlinerecursion"></a>inline_recursion
Satır içi genişletme doğrudan veya karşılıklı özyinelemeli işlev çağrıları denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu pragma denetim işlevleri için işaretlenen kullanım [satır içi](../cpp/inline-functions-cpp.md) ve [__inline](../cpp/inline-functions-cpp.md) veya derleyici /Ob2 seçeneği altında otomatik olarak genişleyen işlevlerinin. Bu pragma kullanılmasını gerektiren bir [/Ob](../build/reference/ob-inline-function-expansion.md) derleyici seçeneği ayarı olarak 1 veya 2. İçin varsayılan duruma `inline_recursion` kapalıdır. Pragma görülen ve işlevinin tanımı etkilemez sonra bu pragma konumundaki ilk işlev çağrısı etkinleşir.  
  
 `inline_recursion` Pragma denetimleri özyinelemeli işlevler nasıl genişletilir. Varsa `inline_recursion` kapalıdır ve genişletilmiş yalnızca bir kez ise satır içi işlev kendisini (doğrudan veya dolaylı olarak), işlevi çağırır. Varsa `inline_recursion` açıktır, işlevi, birden çok kez genişletildiğinde, kümesiyle değere ulaşana kadar [inline_depth](../preprocessor/inline-depth.md) pragma, tarafından tanımlanan özyinelemeli işlevler için varsayılan değer `inline_depth` pragma ya da bir kapasite sınırla .  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_depth](../preprocessor/inline-depth.md)   
 [/OB (satır içi işlev genişletmesi)](../build/reference/ob-inline-function-expansion.md)