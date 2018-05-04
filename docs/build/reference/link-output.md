---
title: LINK çıktısı | Microsoft Docs
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae68de707ece35825a32a404ce14032d4bbd3141
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="link-output"></a>LINK Çıktısı
LINK çıktısı .exe dosyaları, DLL'ler, eşlem dosyaları ve iletileri içerir.  
  
##  <a name="_core_output_files"></a> Çıkış dosyaları  
 Varsayılan çıkış dosyası bağlantısından bir .exe dosyasıdır. Varsa [/dll](../../build/reference/dll-build-a-dll.md) seçeneği belirtildiğinde, bağlantı bir .dll dosyası oluşturur. Çıkış dosya adıyla denetleyebilirsiniz [çıktı dosyası adını (/ OUT)](../../build/reference/out-output-file-name.md) seçeneği.  
  
 Artımlı modunda bağlantı programı daha sonra artımlı derlemeler için durum bilgilerini tutmak için bir .ilk dosyası oluşturur. .İlk dosyaları hakkında daha fazla ayrıntı için bkz: [.ilk dosyaları](../../build/reference/dot-ilk-files-as-linker-input.md). Artımlı bağlama hakkında daha fazla bilgi için bkz: [artımlı bağlantı (/ ARTIMLI)](../../build/reference/incremental-link-incrementally.md) seçeneği.  
  
 BAĞLANTI oluşturduğunda (genellikle bir DLL) içeren bir program aktarır, .exp dosyası derleme kullanılmadığı sürece, ayrıca .lib dosyası oluşturur. İçeri aktarma kitaplığı dosya adıyla denetleyebilirsiniz [/IMPLIB](../../build/reference/implib-name-import-library.md) seçeneği.  
  
 Varsa [eşlem dosyası oluştur (/ eşleme)](../../build/reference/map-generate-mapfile.md) seçeneği belirtildiğinde, bağlantı bir eşlem dosyası oluşturur.  
  
 Varsa [hata ayıklama bilgisi üret (/ DEBUG)](../../build/reference/debug-generate-debug-info.md) seçeneği belirtildiğinde, program için hata ayıklama bilgileri içerecek şekilde PDB bağlantı oluşturur.  
  
##  <a name="_core_other_output"></a> Başka bir çıktı  
 Yazdığınızda `link` herhangi diğer komut satırı girişi olmadan, bağlantı seçeneklerini özetler kullanım deyimini görüntüler.  
  
 BAĞLANTI telif hakkı ve sürüm iletisi görüntüler ve komut dosyası girişi, sürece görüntülemektedir [Başlangıç başlığını gösterme (/ NOLOGO)](../../build/reference/nologo-suppress-startup-banner-linker.md) seçenek kullanılır.  
  
 Kullanabileceğiniz [yazdırma ilerleme durumu iletileri (/ VERBOSE)](../../build/reference/verbose-print-progress-messages.md) derleme hakkında ek ayrıntıları görüntülemek için seçeneği.  
  
 BAĞLANTI sorunları LNK formunda hata ve uyarı iletileri*nnnn*. Ayrıca bu hata öneki ve dizi numarası LIB, DUMPBIN ve EDITBIN tarafından kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)