---
description: 'Daha fazla bilgi edinin: giriş dosyalarını bağlama'
title: LINK Giriş Dosyaları
ms.date: 11/04/2016
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
ms.openlocfilehash: 3bf25d36ab61b35dfe3d1551e9f85e8c2f26862b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199512"
---
# <a name="link-input-files"></a>LINK Giriş Dosyaları

Bağlayıcıyı nesneler, içeri aktarma ve standart kitaplıklar, kaynaklar, modül tanımları ve komut girişi içeren dosyalarla sağlarsınız. BAĞLANTı, dosya uzantılarını bir dosyanın içeriğiyle ilgili varsayımlar yapmak için kullanmaz. Bunun yerine, bağlantı, ne tür dosya olduğunu belirlemek için her giriş dosyasını inceler.

Komut satırındaki nesne dosyaları, komut satırında göründükleri sırada işlenir. Kitaplıklar komut satırı sırasında da aranır ve aşağıdaki desteklenmediği uyarısıyla: bir kitaplıktan bir nesne dosyasına getirilirken çözümlenmemiş semboller önce Bu kitaplıkta aranır, ardından komut satırı ve [/defaultlib (varsayılan kitaplık)](defaultlib-specify-default-library.md) yönergelerinden ve ardından komut satırının başındaki tüm kitaplıklara ve sonra aşağıdaki kitaplıklara.

> [!NOTE]
> BAĞLANTı, yanıt dosyalarında ve sıralama dosyalarında yorum başlangıcı olarak noktalı virgül (veya başka bir karakter) kabul etmez. Noktalı virgül yalnızca modül tanım dosyalarındaki (. def) yorumların başlangıcı olarak tanınır.

BAĞLANTı aşağıdaki giriş dosyası türlerini kullanır:

- [. obj dosyaları](dot-obj-files-as-linker-input.md)

- [. netmodule dosyaları](netmodule-files-as-linker-input.md)

- [. lib dosyaları](dot-lib-files-as-linker-input.md)

- [. exp dosyaları](dot-exp-files-as-linker-input.md)

- [. def dosyaları](dot-def-files-as-linker-input.md)

- [. pdb dosyaları](dot-pdb-files-as-linker-input.md)

- [. res dosyaları](dot-res-files-as-linker-input.md)

- [. exe dosyaları](dot-exe-files-as-linker-input.md)

- [. txt dosyaları](dot-txt-files-as-linker-input.md)

- [. Ilk dosyaları](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
