---
title: Bağlayıcı araçları uyarısı LNK4206 | Microsoft Docs
ms.date: 12/05/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4206
dev_langs:
- C++
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0cb74776f307affb0455d972e27e594e6d06294
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4206"></a>Bağlayıcı Araçları Uyarısı LNK4206

> önceden derlenmiş türü bilgileri; bulunamadı '*filename*' bağlantılı ya da üzerine; hiç hata ayıklama bilgileri gibi nesne bağlama

*Filename* kullanarak derlenen nesne dosyası [/Yc](../../build/reference/yc-create-precompiled-header-file.md), ya da bağlantı komutunda belirtilmedi veya yazıldı.

Bu uyarı için yaygın bir senaryo /Yc ile derlenen .obj kitaplığa olduğunda ve bu .obj kodunuzdan hiçbir sembol başvuruları olduğu ' dir.  Bu durumda, bağlayıcı kullanın (veya hatta bakın) .obj dosya değil.  Bu durumda, kodunuzu derleyin ve kullanmalısınız [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) kullanarak derlenmiş nesneler için [/Yu](../../build/reference/yu-use-precompiled-header-file.md).