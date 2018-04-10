---
title: LIB'e genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef3d1e57371fdea62bb557830baca633f4165637
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-lib"></a>LIB'e Genel Bakış
LIB standart kitaplıkları oluşturur, kitaplıkları içeri aktarma ve dışarı aktarma dosyaları ile birlikte kullanabileceğiniz [bağlantı](../../build/reference/linker-options.md) bir programı oluştururken. LIB bir komut satırından çalıştırır.  
  
 LIB şu modlarında kullanabilirsiniz:  
  
-   [Oluşturma veya değiştirme COFF kitaplığı](../../build/reference/managing-a-library.md)  
  
-   [Üye nesnesi bir dosyaya ayıklanıyor](../../build/reference/extracting-a-library-member.md)  
  
-   [Dışa aktarma dosyası ve içeri aktarma kitaplığı oluşturma](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 Bu modların karşılıklı olarak birbirini dışlar; aynı anda yalnızca bir modda LIB kullanabilir.  
  
## <a name="lib-options"></a>LIB seçenekleri  
 Daha fazla bilgi için bir bağlantı içeren lib.exe seçenekleri aşağıdaki tabloda listelenmektedir.  
  
 **/ DEF**  
 İçeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturun.  
  
 Daha fazla bilgi için bkz: [bir içeri aktarma kitaplığı ve dışarı aktarma dosyası derleme](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ ERRORREPORT**  
 Lib.exe ile iç hatalar hakkında bilgi göndermek.  
  
 Daha fazla bilgi için bkz: [çalıştıran LIB](../../build/reference/running-lib.md).  
  
 **/ DIŞARI AKTARMA**  
 Programınızdan işlevi dışarı aktarır.  
  
 Daha fazla bilgi için bkz: [bir içeri aktarma kitaplığı ve dışarı aktarma dosyası derleme](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ EXTRACT**  
 Var olan bir kitaplık üyesi bir kopyasını içeren bir nesne (.obj) dosyası oluşturun.  
  
 Daha fazla bilgi için bkz: [kitaplık üyesini ayıklama](../../build/reference/extracting-a-library-member.md).  
  
 **/ INCLUDE**  
 Bir simge sembol tablosuna ekler.  
  
 Daha fazla bilgi için bkz: [bir içeri aktarma kitaplığı ve dışarı aktarma dosyası derleme](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ LIBPATH**  
 Ortam Kitaplığı yol geçersiz kılar.  
  
 Daha fazla bilgi için bkz: [kitaplığı yönetme](../../build/reference/managing-a-library.md).  
  
 **/ LİSTESİ**  
 Standart çıktı çıkış kitaplığına hakkında bilgileri görüntüler.  
  
 Daha fazla bilgi için bkz: [kitaplığı yönetme](../../build/reference/managing-a-library.md).  
  
 **/ LTCG**  
 Bağlama zamanı kodu oluşturma kullanılarak oluşturulması için kitaplık neden olur.  
  
 Daha fazla bilgi için bkz: [çalıştıran LIB](../../build/reference/running-lib.md).  
  
 **/ MACHINE**  
 Programın hedef platformu belirtir.  
  
 Daha fazla bilgi için bkz: [çalıştıran LIB](../../build/reference/running-lib.md).  
  
 **/ ADI**  
 İçeri aktarma kitaplığı oluştururken, içeri aktarma kitaplığını oluşturulmakta olan DLL adını belirtir.  
  
 Daha fazla bilgi için bkz: [kitaplığı yönetme](../../build/reference/managing-a-library.md).  
  
 **/ NODEFAULTLIB**  
 Bir veya daha fazla varsayılan kitaplık dış başvuruları çözülürken arar kitaplıkları listesinden kaldırır.  
  
 Daha fazla bilgi için bkz: [kitaplığı yönetme](../../build/reference/managing-a-library.md).  
  
 **/ NOLOGO**  
 LIB telif hakkı iletisi ve sürüm numarasını görüntülenmesini engeller ve komut dosyaları Yankı önler.  
  
 Daha fazla bilgi için bkz: [çalıştıran LIB](../../build/reference/running-lib.md).  
  
 **/ OUT**  
 Varsayılan çıkış filename geçersiz kılar.  
  
 Daha fazla bilgi için bkz: [kitaplığı yönetme](../../build/reference/managing-a-library.md).  
  
 **/ KALDIR**  
 Bir nesne çıkış kitaplığından atlar.  
  
 Daha fazla bilgi için bkz: [kitaplığı yönetme](../../build/reference/managing-a-library.md).  
  
 **/ SUBSYSTEM**  
 İşletim sistemi, çıkış kitaplığına bağlama tarafından oluşturulan bir programı çalıştırmak anlatır.  
  
 Daha fazla bilgi için bkz: [kitaplığı yönetme](../../build/reference/managing-a-library.md).  
  
 **/ VERBOSE**  
 Eklenmekte olan .obj dosya adlarını dahil olmak üzere oturumu ilerlemesini hakkındaki ayrıntıları görüntüler.  
  
 Daha fazla bilgi için bkz: [çalıştıran LIB](../../build/reference/running-lib.md).  
  
 **/WX**  
 Uyarıları hata olarak kabul eder.  
  
 Daha fazla bilgi için bkz: [çalıştıran LIB](../../build/reference/running-lib.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LIB başvurusu](../../build/reference/lib-reference.md)   
 [LIB giriş dosyaları](../../build/reference/lib-input-files.md)   
 [LIB çıktı dosyaları](../../build/reference/lib-output-files.md)   
 [Diğer LIB çıktısı](../../build/reference/other-lib-output.md)   
 [Kitaplık Yapısı](../../build/reference/structure-of-a-library.md)