---
title: Derleyici Uyarısı (düzey 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: f73fa8e09baab127e7755ebe3def69c2fb585744
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028473"
---
# <a name="compiler-warning-level-1-c4274"></a>Derleyici Uyarısı (düzey 1) C4274

\#ident; yoksayıldı #pragma comment (exestr, 'string') için belgelere bakın

`#ident` Kullanıcı tanımlı bir dize, nesne veya yürütülebilir dosya ekler, yönergesi, kullanım dışı bırakılmıştır. Sonuç olarak, derleyici yönergesi yok sayar.

> [!CAUTION]
>  Uyarı C4274 kullanmanızı önerir [#pragma comment (exestr, 'string')](../../preprocessor/comment-c-cpp.md) yönergesi. Ancak, bu önerileri kullanım dışıdır ve derleyici gelecek bir sürümünde düzenlendi. Kullanırsanız `#pragma` yönergesi (LINK.exe) bağlayıcı aracı yönergesi tarafından üretilen yorum kaydı yoksayar ve sorunları uyarı [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Yerine `#ident` yönergesi, bir dosya sürümü kaynak dizesi, uygulamanızda kullanmanızı öneririz.

## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Kaldırma `#ident "` *dize* `"` yönergesi.

## <a name="see-also"></a>Ayrıca bkz.

[comment (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Bağlayıcı Araçları Uyarısı LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../../windows/working-with-resource-files.md)