---
title: Derleyici Uyarısı (düzey 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: 5d005fccc5920aea61698a65edf9284d56366a1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377072"
---
# <a name="compiler-warning-level-1-c4274"></a>Derleyici Uyarısı (düzey 1) C4274

\#ident göz ardı; #pragma yorum için belgelere bakın (exestr, 'string')

Nesne `#ident` veya çalıştırılabilir dosyaya kullanıcı tarafından belirtilen bir dize ekleyen yönerge amortismana tabi dir. Sonuç olarak, derleyici yönergeyi yoksayılsa.

> [!CAUTION]
> Uyarı C4274 [yorum (exestr, 'string')](../../preprocessor/comment-c-cpp.md) yönergesi #pragma kullanmanızı önerir. Ancak, bu tavsiye amortismana katif ve derleyicinin gelecekteki sürümünde revize edilecektir. Yönergeyi `#pragma` kullanırsanız, bağlayıcı aracı (LINK.exe) yönerge tarafından üretilen yorum kaydını yoksa ve [LNK4229'u](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)uyarır. `#ident` Yönerge yerine, uygulamanızda bir dosya sürümü kaynak dizesi kullanmanızı öneririz.

## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- `#ident "` *Dize* `"` yönergesini kaldırın.

## <a name="see-also"></a>Ayrıca bkz.

[comment (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Bağlayıcı Araçları Uyarısı LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../../windows/working-with-resource-files.md)
