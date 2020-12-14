---
description: 'Daha fazla bilgi edinin: bağlantı çıkışı'
title: LINK Çıktısı
ms.date: 11/04/2016
helpviewer_keywords:
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
ms.openlocfilehash: 18d14fda2702e588f69c8a613783087895827826
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190997"
---
# <a name="link-output"></a>LINK Çıktısı

Bağlantı çıkışı. exe dosyaları, dll 'Ler, mapfiles ve mesajlar içerir.

## <a name="output-files"></a><a name="_core_output_files"></a> Çıkış dosyaları

BAĞLANTıDAN varsayılan çıkış dosyası bir. exe dosyasıdır. [/DLL](dll-build-a-dll.md) seçeneği BELIRTILMIŞSE, bağlantı bir. dll dosyası oluşturur. Çıkış dosyası adını [Çıkış dosyası adı (/out)](out-output-file-name.md) seçeneğiyle denetleyebilirsiniz.

Artımlı modda, bağlantı, programın daha sonra artımlı derlemeleri için durum bilgilerini tutmak üzere bir. Ilk dosyası oluşturur. . Ilfiles dosyaları hakkında daha fazla bilgi için bkz. [. ılfiles](dot-ilk-files-as-linker-input.md). Artımlı bağlama hakkında daha fazla bilgi için, artımlı [bağlantı (/artımlı)](incremental-link-incrementally.md) seçeneğine bakın.

BAĞLANTı, dışarı aktarmalar (genellikle bir DLL) içeren bir program oluşturduğunda, derlemede bir. exp dosyası kullanılmadığı takdirde bir. lib dosyası da oluşturur. İçeri aktarma kitaplığı dosya adını [/ımplib](implib-name-import-library.md) seçeneğiyle denetleyebilirsiniz.

[Mapfile oluştur (/MAP)](map-generate-mapfile.md) seçeneği BELIRTILMIŞSE, bağlantı bir mapfile oluşturur.

[Hata ayıklama bilgisi oluştur (/Debug)](debug-generate-debug-info.md) seçeneği BELIRTILMIŞSE, bağlantı, programın hata ayıklama bilgilerini içermesi IÇIN bir pdb oluşturur.

## <a name="other-output"></a><a name="_core_other_output"></a> Diğer çıkış

`link`Başka bir komut satırı girişi olmadan yazdığınızda, bağlantı, seçeneklerini özetleyen bir kullanım ifadesini görüntüler.

BAĞLANTı, [başlangıç başlığını gösterme (/nologo)](nologo-suppress-startup-banner-linker.md) seçeneği kullanılmadığı takdirde bir telif hakkı ve sürüm iletisi ve yankı komut dosyası girişi görüntüler.

Yapı ile ilgili ek ayrıntıları göstermek için [Ilerleme mesajlarını Yazdır (/verbose)](verbose-print-progress-messages.md) seçeneğini kullanabilirsiniz.

BAĞLANTı sorunları hatası ve uyarı iletileri ile LNK *nnnn*. Bu hata ön eki ve sayı aralığı LıB, DUMPBIN ve EDITBIN tarafından da kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
