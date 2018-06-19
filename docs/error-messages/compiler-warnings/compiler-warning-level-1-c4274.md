---
title: Derleyici Uyarısı (düzey 1) C4274 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b941fc0cb32e268e33d3b0e1ae66079e8decaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286152"
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
 [Kaynak Dosyalarıyla Çalışma](../../windows/working-with-resource-files.md)