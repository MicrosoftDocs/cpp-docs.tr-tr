---
title: LINK Giriş Dosyaları
ms.date: 11/04/2016
f1_keywords:
- link
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
ms.openlocfilehash: 48ad9423ae35c22a97a873fe6a2a0479c12ab33b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291515"
---
# <a name="link-input-files"></a>LINK Giriş Dosyaları

Bağlayıcı nesneleri, içeri aktarma ve standart kitaplıkları, kaynaklar, modül tanımları ve giriş komut içeren dosyaları ile sağladığınız. BAĞLANTI dosyasının içeriği hakkında varsayımlar yapmak için dosya uzantılarını kullanmaz. Bunun yerine, bağlantı olduğu dosya türünü belirlemek için her bir giriş dosyasını inceler.

Komut satırında nesne dosyaları, komut satırında göründükleri sırayla işlenir. Kitaplıklar şu uyarı ile de komut satırı sırada aranır: Olan semboller çözümlenmemiş ne zaman bir nesne dosyası kitaplığından alanında bir araya getirdiğini aranır için bu kitaplıkta önce ve sonra komut satırından aşağıdaki kitaplıklar ve [/DEFAULTLIB (varsayılan kitaplığı belirtin)](defaultlib-specify-default-library.md) yönergeleri ve ardından komut satırının başında tüm kitaplıkları için.

> [!NOTE]
>  BAĞLANTI artık noktalı virgül (veya başka bir karakter) yanıt dosyaları ve sipariş dosyaları bir açıklama başlangıcı olarak kabul eder. Noktalı virgül, yalnızca modül tanım (.def) dosyalarındaki açıklamaları yolunun başı olarak kabul edilir.

Bağlantıyı aşağıdaki giriş dosya türlerini kullanır:

- [.obj dosyaları](dot-obj-files-as-linker-input.md)

- [.netmodule dosyaları](netmodule-files-as-linker-input.md)

- [.lib dosyaları](dot-lib-files-as-linker-input.md)

- [.exp dosyaları](dot-exp-files-as-linker-input.md)

- [.def dosyaları](dot-def-files-as-linker-input.md)

- [.pdb dosyaları](dot-pdb-files-as-linker-input.md)

- [.res dosyaları](dot-res-files-as-linker-input.md)

- [.exe dosyaları](dot-exe-files-as-linker-input.md)

- [.txt dosyaları](dot-txt-files-as-linker-input.md)

- [.ilk dosyaları](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
