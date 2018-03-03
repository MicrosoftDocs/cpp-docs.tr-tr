---
title: "BAĞLANTI giriş dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d0cae9498d2c9b49e52cf56991d2425de39d7e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="link-input-files"></a>LINK Giriş Dosyaları
Bağlayıcı nesneleri, içeri aktarma ve standart kitaplıkları, kaynaklar, modül tanımları ve giriş komut içeren dosyaları belirtin. BAĞLANTI dosyasının içeriği hakkında varsayımlarda için dosya uzantılarını kullanmaz. Bunun yerine, bağlantı olmasından dosya türlerini belirlemek için her giriş dosyası inceler.  
  
 Nesne dosyaları komut satırında, komut satırında göründükleri sırada işlenir. Kitaplıklar şu uyarısıyla birlikte de komut satırı sırayla aranır: olan simgeleri çözümlenmemiş ne zaman bir kitaplıktan bir nesne dosyasında getiren aranır için bu Kitaplığı'nda önce ve sonra komut satırı ve Aşağıdakikitaplıklarından[/DEFAULTLIB (varsayılan kitaplığı belirtin)](../../build/reference/defaultlib-specify-default-library.md) yönergeleri ve komut satırının başına herhangi bir kitaplıklara sonra.  
  
> [!NOTE]
>  BAĞLANTI artık noktalı virgül (veya başka bir karakter) yanıt dosyaları ve sipariş dosyaları açıklamada start olarak kabul eder. Noktalı virgül, yalnızca modül tanımı dosyaları (.def) açıklamaları başlangıç olarak kabul edilir.  
  
 BAĞLANTI giriş dosyaları aşağıdaki türlerini kullanır:  
  
-   [.obj dosyaları](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [.netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [.lib dosyaları](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [.exp dosyaları](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [.def dosyaları](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [.pdb dosyaları](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [.res dosyaları](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [.exe dosyaları](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [.txt dosyaları](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [.ilk dosyaları](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)