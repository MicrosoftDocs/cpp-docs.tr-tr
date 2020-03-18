---
title: LIB'e Genel Bakış
description: Lib. exe kitaplık aracının kullanımına ve seçeneklerine genel bakış.
ms.date: 02/09/2020
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
ms.openlocfilehash: 4ed725f383d956adf7abcf1c68002dee51703013
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439005"
---
# <a name="overview-of-lib"></a>LIB'e Genel Bakış

LıB (lib. exe), bir program oluştururken [bağlantı](linker-options.md) ile kullanabileceğiniz standart kitaplıklar, içeri aktarma kitaplıkları ve dışarı aktarma dosyaları oluşturur. LıB bir komut isteminden çalışır.

LıB 'i aşağıdaki modlarda kullanabilirsiniz:

- [COFF kitaplığı oluşturma veya değiştirme](managing-a-library.md)

- [Bir dosyaya üye nesnesini ayıklama](extracting-a-library-member.md)

- [Dışarı aktarma dosyası ve içeri aktarma kitaplığı oluşturma](working-with-import-libraries-and-export-files.md)

Bu modlar birbirini dışlıyor; LıB 'i aynı anda yalnızca bir modda kullanabilirsiniz.

## <a name="lib-options"></a>LıB seçenekleri

Aşağıdaki tabloda, daha fazla bilgi bağlantısı ile lib. exe seçenekleri listelenmektedir.

|Seçenek|Açıklama|
|-|-|
|**/DEF**|İçeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturun.<br/><br/>Daha fazla bilgi için bkz. [Içeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturma](building-an-import-library-and-export-file.md).|
|**/ERRORREPORT**| Kullanım dışı. Daha fazla bilgi için bkz. [LIB çalıştırma](running-lib.md).|
|**/EXPORT**|   Programından bir işlevi dışarı aktarır.<br/><br/>Daha fazla bilgi için bkz. [Içeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturma](building-an-import-library-and-export-file.md).|
|**/EXTRACT**|   Var olan bir kitaplığın bir üyesinin kopyasını içeren bir nesne (. obj) dosyası oluşturun.<br/><br/>Daha fazla bilgi için bkz. [bir kitaplık üyesini ayıklama](extracting-a-library-member.md).|
|**/INCLUDE**|   Sembol tablosuna bir sembol ekler.<br/><br/>Daha fazla bilgi için bkz. [Içeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturma](building-an-import-library-and-export-file.md).|
|**/LıBPATH**|   Ortam kitaplığı yolunu geçersiz kılar.<br/><br/>Daha fazla bilgi için bkz. [bir kitaplığı yönetme](managing-a-library.md).|
|**/LINKREPRO**|   LIB. exe kilitlenmesinin veya iç hatanın yeniden oluşturulması için gereken yapıtları oluşturur.<br/><br/>Daha fazla bilgi için bkz. [LIB çalıştırma](running-lib.md).|
|**/LINKREPROTARGET**|   Yalnızca lib. exe belirtilen bir dosyayla kullanıldığında **/LINKREPRO** yapılarını oluşturur.<br/><br/>Daha fazla bilgi için bkz. [LIB çalıştırma](running-lib.md).|
|**/LIST**|   Standart çıktıya çıkış kitaplığıyla ilgili bilgileri görüntüler.<br/><br/>Daha fazla bilgi için bkz. [bir kitaplığı yönetme](managing-a-library.md).|
|**/LTCG**|   , Kitaplığın bağlantı zamanı kodu oluşturma kullanılarak oluşturulmasına neden olur.<br/><br/>Daha fazla bilgi için bkz. [LIB çalıştırma](running-lib.md).|
|**/MACHıNE**|   Program için hedef platformu belirtir.<br/><br/>Daha fazla bilgi için bkz. [LIB çalıştırma](running-lib.md).|
|**No**|   İçeri aktarma kitaplığı oluştururken, içeri aktarma kitaplığının oluşturulduğu DLL 'in adını belirtir.<br/><br/>Daha fazla bilgi için bkz. [bir kitaplığı yönetme](managing-a-library.md).|
|**/NODEFAULTLıB**|   Dış başvuruları çözümlerken aradığı kitaplık listesinden bir veya daha fazla varsayılan kitaplığı kaldırır.<br/><br/>Daha fazla bilgi için bkz. [bir kitaplığı yönetme](managing-a-library.md).|
|**/NOLOGO**|   LıB telif hakkı iletisi ve sürüm numarasını görüntülemeyi engeller ve komut dosyalarının yankısını önler.<br/><br/>Daha fazla bilgi için bkz. [LIB çalıştırma](running-lib.md).|
|**/OUT**|   Varsayılan çıkış dosya adını geçersiz kılar.<br/><br/>Daha fazla bilgi için bkz. [bir kitaplığı yönetme](managing-a-library.md).|
|**/REMOVE**|   Çıkış kitaplığından bir nesneyi atlar.<br/><br/>Daha fazla bilgi için bkz. [bir kitaplığı yönetme](managing-a-library.md).|
|**/SUBSYSTEM**|   İşletim sistemine, çıkış kitaplığına bağlanarak oluşturulan bir programın nasıl çalıştırılacağını söyler.<br/><br/>Daha fazla bilgi için bkz. [bir kitaplığı yönetme](managing-a-library.md).|
|**/VERBOSE**|   Eklenmekte olan. obj dosyalarının adları da dahil olmak üzere, oturumun ilerleme durumu hakkındaki ayrıntıları görüntüler.<br/><br/>Daha fazla bilgi için bkz. [LIB çalıştırma](running-lib.md).|
|**/WX**|   Uyarıları hata olarak değerlendirin.<br/><br/>Daha fazla bilgi için bkz. [LIB çalıştırma](running-lib.md).|

## <a name="see-also"></a>Ayrıca bkz.

[LIB başvurusu](lib-reference.md)\
[LIB giriş dosyaları](lib-input-files.md)\
[LIB çıktı dosyaları](lib-output-files.md)\
[DIĞER LIB çıktısı](other-lib-output.md)\
[Kitaplık Yapısı](structure-of-a-library.md)
