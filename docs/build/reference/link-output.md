---
title: LINK Çıktısı
ms.date: 11/04/2016
f1_keywords:
- link
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
ms.openlocfilehash: 183f83501d930188032ec4209623ef7cf1a30efa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269182"
---
# <a name="link-output"></a>LINK Çıktısı

LINK çıktısı .exe dosyaları, DLL'ler, eşlem ve iletileri içerir.

##  <a name="_core_output_files"></a> Çıktı dosyaları

Varsayılan çıkış dosyası bağlantısından bir .exe dosyasıdır. Varsa [/dll](dll-build-a-dll.md) seçeneği belirtilmemişse, bağlantısını bir .dll dosyası oluşturur. Çıkış dosya adından denetleyebilirsiniz [çıkış dosyası adı (/ OUT)](out-output-file-name.md) seçeneği.

Artımlı modda bağlantısı programının daha sonra artımlı derlemeleri için durum bilgileri tutmak için bir .ilk dosyası oluşturur. .İlk dosyaları hakkında daha fazla ayrıntı için bkz: [.ilk dosyaları](dot-ilk-files-as-linker-input.md). Artımlı bağlama hakkında daha fazla bilgi için bkz. [artımlı bağlantı (/ INCREMENTAL)](incremental-link-incrementally.md) seçeneği.

BAĞLANTISINI oluşturur (genellikle bir DLL) içeren bir program aktarır, .exp dosyasının yapı kullanılmadığı sürece bir .lib dosyasına da alır. İçeri aktarma kitaplığı dosya adıyla denetleyebilirsiniz [/IMPLIB](implib-name-import-library.md) seçeneği.

Varsa [eşlem dosyası oluştur (/ MAP)](map-generate-mapfile.md) seçeneği belirtildiğinde, bağlantı, bir eşlem dosyası oluşturur.

Varsa [hata ayıklama bilgisi oluştur (/ DEBUG)](debug-generate-debug-info.md) seçeneği belirtilmemişse, programın hata ayıklama bilgilerini içeren bir PDB bağlantısını oluşturur.

##  <a name="_core_other_output"></a> Diğer çıktısı

Yazdığınızda `link` herhangi diğer komut satırı girişi olmadan, bağlantı seçeneklerini özetleyen bir kullanım deyimi görüntüler.

BAĞLANTI telif hakkı ve sürüm bir ileti görüntüler ve komut dosyası girişi, sürece yankılayan [Başlangıç başlığını gösterme (/ NOLOGO)](nologo-suppress-startup-banner-linker.md) seçeneği kullanılır.

Kullanabileceğiniz [ilerleme iletilerini Yazdır (/ VERBOSE)](verbose-print-progress-messages.md) yapı hakkındaki ek ayrıntıları görüntülemek için seçeneği.

BAĞLANTI sorunları hata ve uyarı iletileri LNK biçiminde*nnnn*. Bu hata öneki ve dizi numarası ayrıca LIB, DUMPBIN ve EDITBIN tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
