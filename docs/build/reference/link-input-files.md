---
title: BAĞLANTI giriş dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d61a24916c3b56cf666a85483414f86753f7f59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374833"
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