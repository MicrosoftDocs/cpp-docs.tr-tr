---
title: 'TN048: MFC Veritabanı Uygulamaları için ODBC Kurulum ve Yönetim Programları Yazma'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.odbc
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
ms.openlocfilehash: b31ceb8bfc48decb5387d386ee8e8b64822f72ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584141"
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048: MFC Veritabanı Uygulamaları için ODBC Kurulum ve Yönetim Programları Yazma

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

MFC veritabanı sınıfları kullanan uygulamalar, ODBC bileşenleri yükleyen bir Kurulum programı gerekir. Bunlar varsayılan sürücüleri belirtmek ve veri kaynaklarını yapılandırmak için kullanılabilir sürücüler hakkında bilgi alacak bir ODBC yönetim program oluşturmanız da gerekebilir. Bu Not, bu programları yazmak için ODBC Yükleyici API kullanımını açıklar.

##  <a name="_mfcnotes_writing_an_odbc_setup_program"></a> Bir ODBC Kurulum programı yazma

ODBC Sürücü Yöneticisi'ni (ODBC. veritabanı DllMain'den gerektirir DLL) ve veri kaynaklarını almak için ODBC sürücüleri. Birçok ODBC sürücüsü, ayrıca ek ağ ve iletişimi DLL'leri gerektirir. Çoğu ODBC sürücüleri gerekli ODBC bileşenleri yükleyen bir Kurulum programı ile gönderin. MFC veritabanı sınıfları kullanarak uygulama geliştiriciler şunları yapabilir:

- ODBC bileşenleri yüklemek için sürücü özgü kurulum programları dayanır. Bu iş Geliştirici bölümünde başka gerektirir — yalnızca sürücünün Kurulum programını yeniden dağıtabilirsiniz.

- Alternatif olarak, Sürücü Yöneticisi'ni ve sürücü yüklenir kendi kurulum programı yazabilirsiniz.

Installer ODBC API'sı, uygulamaya özgü kurulum programları yazmak için kullanılabilir. Yükleyici API işlevlerinde ODBC Yükleyici DLL tarafından uygulanan — ODBCINST. 16-bit Windows ve ODBCCP32 DLL. Win32 DLL. Bir uygulama çağırabilirsiniz `SQLInstallODBC` yükleyicide ODBC Sürücü Yöneticisi, ODBC sürücüleri ve yükleyecek DLL, çevirmenler gerekli. Bunu ardından yüklenen sürücülerin ve çevirmenler ODBCINST kaydeder. INI dosyası (veya NT üzerinde kayıt defterini). `SQLInstallODBC` ODBC tam yolu gerektirir. Yüklenecek sürücülerin listesini içeren ve her bir sürücü oluşturan dosyaların açıklar INF dosyası. Sürücü Yöneticisi ve çevirmenler hakkında benzer bilgileri de içerir. ODBC. INF dosyaları genellikle sürücü geliştiriciler tarafından sağlanır.

Bir program, ODBC bileşenleri tek tek de yükleyebilirsiniz. Sürücü Yöneticisi'ni yüklemek için bir program çağırır `SQLInstallDriverManager` Sürücü Yöneticisi için hedef dizine alınacak DLL yükleyicisi. Bu genellikle Windows DLL'leri bulunduğu dizindir. Program bilgileri ODBC [ODBC Sürücü Yöneticisi] bölümünü kullanır. INF dosyası Sürücü Yöneticisi'ni ve ilişkili dosyaları yükleme diskinden bu dizine kopyalayın. Tek bir sürücü yüklemek için bir program çağırır `SQLInstallDriver` sürücü belirtimi için ODBCINST eklemek için DLL yükleyicisi. INI dosyası (veya NT üzerinde kayıt defterini). `SQLInstallDriver` sürücünün hedef dizin döndürür; genellikle Windows DLL'leri bulunduğu dizin. Program bilgileri ODBC sürücüsünün bölümünde kullanır. INF dosyası sürücü DLL ile ilgili dosyaları yükleme diskinden bu dizine kopyalayın.

ODBC hakkında daha fazla bilgi için. INF, ODBCINST. INI ve API Yükleyicisi'ni kullanarak bkz ODBC SDK *Programcının Başvurusu* Bölüm 19, ODBC yazılımını yükleme.

##  <a name="_mfcnotes_writing_an_odbc_administrator"></a> ODBC Yöneticisi yazma

MFC veritabanı uygulaması ayarlayabilmeniz ve ODBC veri kaynakları iki yoldan biriyle şu şekilde yapılandırın:

- (Bir programı veya Denetim Masası öğesi olarak kullanılabilir) ODBC Yöneticisi'ni kullanın.

- Veri kaynakları yapılandırmak üzere kendi programını oluşturun.

Veri kaynakları yapılandırır bir program, yükleyici DLL işlev çağrıları yapar. Bir veri kaynağını yapılandırmak için DLL Kurulum Yükleyici DLL çağırır. Her sürücü için bir kurulum DLL yoktur; DLL kendisini sürücü veya ayrı bir DLL olabilir. DLL kurulum sürücü destekleniyorsa, veri kaynağı ve varsayılan translator bağlanmak için gereken bilgileri kullanıcıya sorar. Daha sonra yükleyici DLL ve Windows API'leri ODBC bu bilgileri kaydetmek için çağırır. INI dosyası (veya kayıt defteri).

Bir iletişim kutusu ile bir kullanıcı ekleyebilir, değiştirebilir ve veri kaynakları silmek için bir program çağırır `SQLManageDataSources` DLL yükleyicisi. Yükleyici, Denetim Masası'ndan DLL çağrıldığında, bu işlev çağrılır. Ekleme, değiştirme veya bir veri kaynağını silmek için `SQLManageDataSources` çağrıları `ConfigDSN` o veri kaynağıyla ilişkili sürücü için Kurulum'daki DLL. Doğrudan ekleme, değiştirme veya veri silme için kaynakları, bir program `SQLConfigDataSource` DLL yükleyicisi. Programın adını veri kaynağı ve gerçekleştirilecek eylemi belirten bir seçenek geçirir. `SQLConfigDataSource` çağrıları `ConfigDSN` kurulumunda DLL ve bağımsız değişkenlerden geçirir `SQLConfigDataSource`.

Daha fazla bilgi için bkz: ODBC SDK *Programcının Başvurusu* Bölüm 23, Kurulum DLL işlev başvurusu ve Bölüm 24, yükleyici DLL işlev başvurusu.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

