---
title: Önemli hata C1382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 923cc957dd136147a6c749f5ebf9508ca7e2052d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1382"></a>Önemli hata C1382
'obj' oluşturulmasının üzerinden PCH dosya 'dosyası yeniden oluşturuldu. Lütfen bu nesneyi yeniden oluşturma  
  
 Kullanırken [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), derleyici gösteren bir CIL .obj daha yeni bir .pch dosyası algılandı. CIL .obj dosyasında güncel bilgilerdir. Nesne yeniden oluşturun.  
  
 C1382 da gerçekleşebilir ile derleme **/Yc**, ancak aynı zamanda birden fazla kaynak kodu dosyaları derleyicisi.  Çözmek için kullanmayın **/Yc** birden çok kaynak kodu dosyaları derleyiciye geçirilirken.  Daha fazla bilgi için bkz: [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md).