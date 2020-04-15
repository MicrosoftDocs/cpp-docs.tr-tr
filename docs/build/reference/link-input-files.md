---
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
ms.openlocfilehash: aec71d4622821618f377953d36a9676e2233eefc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328200"
---
# <a name="link-input-files"></a>LINK Giriş Dosyaları

Bağlayıcıya nesneler, alma ve standart kitaplıklar, kaynaklar, modül tanımları ve komut girişi içeren dosyalar sağlarsınız. LINK, dosyanın içeriği hakkında varsayımlarda bulunmak için dosya uzantılarını kullanmaz. Bunun yerine, LINK ne tür bir dosya olduğunu belirlemek için her giriş dosyasını inceler.

Komut satırındaki nesne dosyaları, komut satırında göründükleri sırada işlenir. Kitaplıklar komut satırı sırasına göre de aranır: Kitaplıktan bir nesne dosyası getirilirken çözülmemiş semboller önce o kitaplıkta, ardından komut satırıve [/DEFAULTLIB (Varsayılan Kitaplık Belirt)](defaultlib-specify-default-library.md) yönergelerinden ve ardından komut satırının başındaki kitaplıklardan aşağıdaki kitaplıklar aranır.

> [!NOTE]
> LINK artık yanıt dosyalarındaki ve sipariş dosyalarındaki bir yorumun başlangıcı olarak bir yarı nokta nokta sını (veya başka bir karakteri) kabul etmez. Yarı kolonlar yalnızca modül tanımlı dosyalardaki (.def) yorumların başlangıcı olarak kabul edilir.

LINK aşağıdaki giriş dosyalarını kullanır:

- [.obj dosyaları](dot-obj-files-as-linker-input.md)

- [.netmodule dosyaları](netmodule-files-as-linker-input.md)

- [.lib dosyaları](dot-lib-files-as-linker-input.md)

- [.exp dosyaları](dot-exp-files-as-linker-input.md)

- [.def dosyaları](dot-def-files-as-linker-input.md)

- [.pdb dosyaları](dot-pdb-files-as-linker-input.md)

- [.res dosyaları](dot-res-files-as-linker-input.md)

- [.exe dosyaları](dot-exe-files-as-linker-input.md)

- [.txt dosyaları](dot-txt-files-as-linker-input.md)

- [.ilk dosyalar](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
