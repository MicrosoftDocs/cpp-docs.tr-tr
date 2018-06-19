---
title: inline_recursion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f81347c8286dfa1f0651af43bd3134565a22aade
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849502"
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
 [/Ob (Satır İçi İşlev Genişletmesi)](../build/reference/ob-inline-function-expansion.md)