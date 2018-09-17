---
title: LIB'e genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 223f5284ed25b5a13fddef879e63ec2e480f3314
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703773"
---
# <a name="overview-of-lib"></a>LIB'e Genel Bakış

LIB standart kitaplıkları oluşturur, kitaplıkları içeri aktarma ve dosyaları ile birlikte kullanabileceğiniz dışarı [bağlantı](../../build/reference/linker-options.md) bir program oluşturma sırasında. LIB, bir komut istemi'nden çalıştırır.

LIB şu modlarında kullanabilirsiniz:

- [Oluşturma veya değiştirme COFF kitaplığı](../../build/reference/managing-a-library.md)

- [Bir dosyaya bir üye nesnesi ayıklanıyor](../../build/reference/extracting-a-library-member.md)

- [Bir dışarı aktarma dosyası ve içeri aktarma kitaplığı oluşturma](../../build/reference/working-with-import-libraries-and-export-files.md)

Bu mod, karşılıklı olarak birbirini dışlar; bir kerede yalnızca bir modda LIB kullanabilirsiniz.

## <a name="lib-options"></a>LIB seçenekleri

Daha fazla bilgi bağlantısını içeren bir lib.exe seçenekleri aşağıdaki tabloda listelenmektedir.

|Seçenek|Açıklama|
|-|-|
|**/ DEF**|Bir içeri aktarma kitaplığını ve dışarı aktarma dosyası oluşturun.<br/><br/>Daha fazla bilgi için [bir içeri aktarma kitaplığını ve dışarı aktarma dosyası derleme](../../build/reference/building-an-import-library-and-export-file.md).|
|**/ ERRORREPORT**|   Lib.exe iç hatalarla ilgili bilgi göndermek.<br/><br/>Daha fazla bilgi için [çalıştıran LIB](../../build/reference/running-lib.md).|
|**/ DIŞARI AKTARMA**|   İşlevi, programınızı dışarı aktarır.<br/><br/>Daha fazla bilgi için [bir içeri aktarma kitaplığını ve dışarı aktarma dosyası derleme](../../build/reference/building-an-import-library-and-export-file.md).|
|**/ EXTRACT**|   Var olan bir kitaplık üyesi bir kopyasını içeren bir nesne (.obj) dosyası oluşturun.<br/><br/>Daha fazla bilgi için [kitaplık üyesini ayıklama](../../build/reference/extracting-a-library-member.md).|
|**/ INCLUDE**|   Bir sembolü sembol tablosuna ekler.<br/><br/>Daha fazla bilgi için [bir içeri aktarma kitaplığını ve dışarı aktarma dosyası derleme](../../build/reference/building-an-import-library-and-export-file.md).|
|**/ LIBPATH**|   Kullanıcının ortam kitaplık yolunu geçersiz kılar.<br/><br/>Daha fazla bilgi için [kitaplığı yönetme](../../build/reference/managing-a-library.md).|
|**/ LİSTELEME**|   Standart çıktıya çıkış Kitaplığı hakkında bilgileri görüntüler.<br/><br/>Daha fazla bilgi için [kitaplığı yönetme](../../build/reference/managing-a-library.md).|
|**/LTCG**|   Bağlama zamanı kod oluşturmayı kullanarak oluşturulacak kitaplığı neden olur.<br/><br/>Daha fazla bilgi için [çalıştıran LIB](../../build/reference/running-lib.md).|
|**/ MACHINE**|   Program için hedef platformu belirtir.<br/><br/>Daha fazla bilgi için [çalıştıran LIB](../../build/reference/running-lib.md).|
|**/ AD**|   İçeri aktarma kitaplığı derlerken, içeri aktarma kitaplığını oluşturulmakta olan DLL'in adını belirtir.<br/><br/>Daha fazla bilgi için [kitaplığı yönetme](../../build/reference/managing-a-library.md).|
|**/ NODEFAULTLIB**|   Bir veya daha fazla varsayılan kitaplığı dış başvuruların çözümlenmesi sırasında aradığı kitaplık listesinden kaldırır.<br/><br/>Daha fazla bilgi için [kitaplığı yönetme](../../build/reference/managing-a-library.md).|
|**/ NOLOGO**|   LIB telif hakkı iletisi ve sürüm numarasını görüntülenmesini engeller ve komut dosyaları Yankı önler.<br/><br/>Daha fazla bilgi için [çalıştıran LIB](../../build/reference/running-lib.md).|
|**/ OUT**|   Varsayılan çıktı dosyası adını geçersiz kılar.<br/><br/>Daha fazla bilgi için [kitaplığı yönetme](../../build/reference/managing-a-library.md).|
|**/ KALDIR**|   Nesneyi çıkış kitaplığında atlar.<br/><br/>Daha fazla bilgi için [kitaplığı yönetme](../../build/reference/managing-a-library.md).|
|**/SUBSYSTEM**|   İşletim sistemi, çıkış Kitaplığı'na bağlama tarafından oluşturulan bir programı çalıştırmak üzere anlatır.<br/><br/>Daha fazla bilgi için [kitaplığı yönetme](../../build/reference/managing-a-library.md).|
|**/ VERBOSE**|   Eklenen .obj dosya adlarını dahil olmak üzere, oturumunun ilerleme durumu hakkında ayrıntıları görüntüler.<br/><br/>Daha fazla bilgi için [çalıştıran LIB](../../build/reference/running-lib.md).|
|**/WX**|   Uyarıları hata olarak değerlendir.<br/><br/>Daha fazla bilgi için [çalıştıran LIB](../../build/reference/running-lib.md).|

## <a name="see-also"></a>Ayrıca Bkz.

[LIB Başvurusu](../../build/reference/lib-reference.md)<br/>
[LIB Giriş Dosyaları](../../build/reference/lib-input-files.md)<br/>
[LIB Çıktı Dosyaları](../../build/reference/lib-output-files.md)<br/>
[Diğer LIB Çıktısı](../../build/reference/other-lib-output.md)<br/>
[Kitaplık Yapısı](../../build/reference/structure-of-a-library.md)