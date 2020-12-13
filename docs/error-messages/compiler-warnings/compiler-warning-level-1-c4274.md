---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4274'
title: Derleyici Uyarısı (düzey 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: aa1f6d3b07c7d788d9e47955c4bb51930522b7a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340105"
---
# <a name="compiler-warning-level-1-c4274"></a>Derleyici Uyarısı (düzey 1) C4274

\#Ida yoksayıldı; #pragma yorumu için belgelere bakın (exestr, ' dize ')

`#ident`Nesne veya yürütülebilir dosyaya Kullanıcı tarafından belirtilen bir dize ekleyen yönerge kullanım dışıdır. Sonuç olarak, derleyici yönergesini yoksayar.

> [!CAUTION]
> Uyarı C4274, [#pragma yorumu (exestr, ' String ')](../../preprocessor/comment-c-cpp.md) yönergesini kullanmanızı önerir. Ancak, bu öneri kullanım dışıdır ve derleyicinin gelecek bir sürümünde düzeltilecektir. `#pragma`Yönergesini kullanırsanız, bağlayıcı aracı (LINK.exe), yönerge ve sorunlar Uyarı [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)tarafından üretilen yorum kaydını yoksayar. `#ident`Yönergesi yerine, uygulamanızda bir dosya sürümü kaynak dizesi kullanmanızı öneririz.

## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- `#ident "` *String* `"` yönergesini kaldırın.

## <a name="see-also"></a>Ayrıca bkz.

[comment (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Bağlayıcı Araçları uyarısı LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../../windows/working-with-resource-files.md)
