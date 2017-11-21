---
title: "Derleyici Uyarısı (düzey 1) C4274 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4274
dev_langs: C++
helpviewer_keywords: C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0c6bb31350af030879f23d9c0a9ac105e7293480
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4274"></a>Derleyici Uyarısı (düzey 1) C4274
\#göz ardı plainname; #pragma Açıklama (exestr, 'string') belgelerine bakın  
  
 `#ident` Nesne veya yürütülebilir dosyayı kullanıcı tarafından belirtilen bir dize ekler, yönergesi kullanım dışıdır. Sonuç olarak, derleyici yönergesi yok sayar.  
  
> [!CAUTION]
>  Uyarı C4274 kullanmanızı önerir [#pragma Açıklama (exestr, 'string')](../../preprocessor/comment-c-cpp.md) yönergesi. Ancak, bu önerileri kullanım dışıdır ve derleyici gelecekteki bir sürümde düzenlendi. Kullanırsanız `#pragma` yönergesi (LINK.exe) bağlayıcı aracı yönergesi tarafından üretilen yorum kaydı yoksayar ve sorunları uyarı [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Yerine `#ident` yönergesi, bir dosya sürümü kaynak dizesi uygulamanızda kullanmanızı öneririz.  
  
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Kaldırma `#ident "` *dize* `"` yönergesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yorum (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [Bağlayıcı araçları uyarısı LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [Kaynak dosyaları ile çalışma](../../windows/working-with-resource-files.md)