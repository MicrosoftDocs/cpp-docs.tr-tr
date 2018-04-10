---
title: -FD (IDE en az yeniden derleme) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /FD
dev_langs:
- C++
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0dfcf34be03204b920e5a4459c6a2d7ea6c506d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (IDE En Az Yeniden Derleme)
**/FD** kullanıcılara gösterilmez [komut satırı](../../ide/command-line-property-pages.md) C++ projenin özellik sayfasındaki **özellik sayfaları** iletişim kutusunda, varsa ve yalnızca [/GM derlemeyi (etkinleştirmek en az yeniden derleme)](../../build/reference/gm-enable-minimal-rebuild.md) de seçilmedi. **/FD** geliştirme ortamından dışında herhangi bir etkisi olmaz. **/FD** çıktısında gösterilmeyen **cl /?**.  
  
 Değil etkinleştirirseniz, **/GM derlemeyi** geliştirme ortamında **/FD** kullanılır. **/FD** .idb dosya yeterli bağımlılık bilgi sahip olmasını sağlar. **/FD** yalnızca geliştirme ortamı tarafından kullanılır ve bu komut satırı veya bir yapı komut dosyasından kullanılmamalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)