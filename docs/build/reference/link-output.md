---
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
ms.openlocfilehash: 253f88ed50b9f064edf976277a4618e4f101ec7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331787"
---
# <a name="link-output"></a>LINK Çıktısı

Bağlantı çıktısı .exe dosyaları, DL'ler, mapfiles ve iletileri içerir.

## <a name="output-files"></a><a name="_core_output_files"></a>Çıktı Dosyaları

LINK'in varsayılan çıktı dosyası bir .exe dosyasıdır. [/DLL](dll-build-a-dll.md) seçeneği belirtilirse, LINK bir .dll dosyası oluşturur. Çıktı dosya adını [Çıktı Dosya Adı (/OUT)](out-output-file-name.md) seçeneğiyle denetleyebilirsiniz.

Artımlı modda, LINK, programın daha sonraki artımlı yapılarının durum bilgilerini tutmak için bir .ilk dosya oluşturur. .ilk dosyalar hakkında ayrıntılı bilgi için [.ilk Dosyalar'](dot-ilk-files-as-linker-input.md)a bakın. Artımlı bağlantı hakkında daha fazla bilgi için [Bağlantı'yı Aşamalı (/ARTıMLı)](incremental-link-incrementally.md) seçeneğine bakın.

LINK dışa aktarım (genellikle DLL) içeren bir program oluşturduğunda, yapıda bir .exp dosyası kullanılmadığı sürece bir .lib dosyası da oluşturur. [/IMPLIB](implib-name-import-library.md) seçeneği ile alma kitaplığı dosya adını denetleyebilirsiniz.

[Mapfile (/MAP) oluştur](map-generate-mapfile.md) seçeneği belirtilirse, LINK bir mapfile oluşturur.

Hata [Ayıklama Bilgisini Oluştur (/Hata Ayıklama)](debug-generate-debug-info.md) seçeneği belirtilirse, LINK program için hata ayıklama bilgilerini içerecek bir PDB oluşturur.

## <a name="other-output"></a><a name="_core_other_output"></a>Diğer Çıktı

Başka bir `link` komut satırı girişi olmadan yazdığınızda, LINK seçeneklerini özetleyen bir kullanım deyimi görüntüler.

Link, [Bastırma Başlangıç Başlığı (/NOLOGO)](nologo-suppress-startup-banner-linker.md) seçeneği kullanılmadığı sürece bir telif hakkı ve sürüm iletisi görüntüler ve komut dosyası girişine yankı sağlar.

Yapı yla ilgili ek ayrıntıları görüntülemek için [Yazdırma İlerleme İletileri (/VERBOSE)](verbose-print-progress-messages.md) seçeneğini kullanabilirsiniz.

LNK*nnnn*şeklinde LINK sorunları hata ve uyarı iletileri . Bu hata öneki ve sayı aralığı LIB, DUMPBIN ve EDITBIN tarafından da kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
