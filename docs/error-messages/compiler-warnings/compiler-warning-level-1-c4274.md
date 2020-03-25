---
title: Derleyici Uyarısı (düzey 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: 5f2350f275f883e7bf18aa1621d08b34132e8dfb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175852"
---
# <a name="compiler-warning-level-1-c4274"></a>Derleyici Uyarısı (düzey 1) C4274

\#Ida yoksayıldı; #pragma yorumu için belgelere bakın (exestr, ' dize ')

Nesne veya yürütülebilir dosyaya Kullanıcı tarafından belirtilen bir dize ekleyen `#ident` yönergesi kullanım dışıdır. Sonuç olarak, derleyici yönergesini yoksayar.

> [!CAUTION]
>  Uyarı C4274, [#pragma yorumu (exestr, ' String ')](../../preprocessor/comment-c-cpp.md) yönergesini kullanmanızı önerir. Ancak, bu öneri kullanım dışıdır ve derleyicinin gelecek bir sürümünde düzeltilecektir. `#pragma` yönergesini kullanırsanız, bağlayıcı aracı (LINK. exe), yönerge ve sorunlar Uyarı [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)tarafından üretilen yorum kaydını yoksayar. `#ident` yönergesi yerine, uygulamanızda bir dosya sürümü kaynak dizesi kullanmanızı öneririz.

## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- `#ident "`*dize*`"` yönergesini kaldırın.

## <a name="see-also"></a>Ayrıca bkz.

[comment (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Bağlayıcı Araçları Uyarısı LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../../windows/working-with-resource-files.md)
