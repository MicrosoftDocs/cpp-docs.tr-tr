---
title: BAĞLANTI giriş dosyalarını | Microsoft Docs
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
ms.openlocfilehash: 5974914e736278ebb336b6814661845740855fe6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710248"
---
# <a name="link-input-files"></a>LINK Giriş Dosyaları

Bağlayıcı nesneleri, içeri aktarma ve standart kitaplıkları, kaynaklar, modül tanımları ve giriş komut içeren dosyaları ile sağladığınız. BAĞLANTI dosyasının içeriği hakkında varsayımlar yapmak için dosya uzantılarını kullanmaz. Bunun yerine, bağlantı olduğu dosya türünü belirlemek için her bir giriş dosyasını inceler.

Komut satırında nesne dosyaları, komut satırında göründükleri sırayla işlenir. Aşağıdaki uyarı ile kitaplıkları da komut satırı sırada aranır: olan semboller çözümlenmemiş ne zaman bir nesne dosyası kitaplığından alanında bir araya getirdiğini aranır için bu kitaplıkta önce ve sonra vekomutsatırıaşağıdakikitaplıklarından[/DEFAULTLIB (varsayılan kitaplığı belirtin)](../../build/reference/defaultlib-specify-default-library.md) yönergeleri ve sonra komut satırının başında tüm kitaplıkları.

> [!NOTE]
>  BAĞLANTI artık noktalı virgül (veya başka bir karakter) yanıt dosyaları ve sipariş dosyaları bir açıklama başlangıcı olarak kabul eder. Noktalı virgül, yalnızca modül tanım (.def) dosyalarındaki açıklamaları yolunun başı olarak kabul edilir.

Bağlantıyı aşağıdaki giriş dosya türlerini kullanır:

- [.obj dosyaları](../../build/reference/dot-obj-files-as-linker-input.md)

- [.netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md)

- [.lib dosyaları](../../build/reference/dot-lib-files-as-linker-input.md)

- [.exp dosyaları](../../build/reference/dot-exp-files-as-linker-input.md)

- [.def dosyaları](../../build/reference/dot-def-files-as-linker-input.md)

- [.pdb dosyaları](../../build/reference/dot-pdb-files-as-linker-input.md)

- [.res dosyaları](../../build/reference/dot-res-files-as-linker-input.md)

- [.exe dosyaları](../../build/reference/dot-exe-files-as-linker-input.md)

- [.txt dosyaları](../../build/reference/dot-txt-files-as-linker-input.md)

- [.ilk dosyaları](../../build/reference/dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)