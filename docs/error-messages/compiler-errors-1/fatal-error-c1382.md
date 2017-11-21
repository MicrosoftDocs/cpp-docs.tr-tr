---
title: "Önemli hata C1382 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1382
dev_langs: C++
helpviewer_keywords: C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ddb016e14b01b3bc1dfd45c7d5a8ad1aa489ac3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1382"></a>Önemli hata C1382
'obj' oluşturulmasının üzerinden PCH dosya 'dosyası yeniden oluşturuldu. Lütfen bu nesneyi yeniden oluşturma  
  
 Kullanırken [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), derleyici gösteren bir CIL .obj daha yeni bir .pch dosyası algılandı. CIL .obj dosyasında güncel bilgilerdir. Nesne yeniden oluşturun.  
  
 C1382 da gerçekleşebilir ile derleme **/Yc**, ancak aynı zamanda birden fazla kaynak kodu dosyaları derleyicisi.  Çözmek için kullanmayın **/Yc** birden çok kaynak kodu dosyaları derleyiciye geçirilirken.  Daha fazla bilgi için bkz: [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md).