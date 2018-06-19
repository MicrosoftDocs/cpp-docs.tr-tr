---
title: Önemli hata C1382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07c6af1209faface96585224cbd08b4e35101478
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229261"
---
# <a name="fatal-error-c1382"></a>Önemli hata C1382
'obj' oluşturulmasının üzerinden PCH dosya 'dosyası yeniden oluşturuldu. Lütfen bu nesneyi yeniden oluşturma  
  
 Kullanırken [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), derleyici gösteren bir CIL .obj daha yeni bir .pch dosyası algılandı. CIL .obj dosyasında güncel bilgilerdir. Nesne yeniden oluşturun.  
  
 C1382 da gerçekleşebilir ile derleme **/Yc**, ancak aynı zamanda birden fazla kaynak kodu dosyaları derleyicisi.  Çözmek için kullanmayın **/Yc** birden çok kaynak kodu dosyaları derleyiciye geçirilirken.  Daha fazla bilgi için bkz: [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md).