---
title: 'TN048: MFC Veritabanı Uygulamaları için ODBC Kurulum ve Yönetim Programları Yazma'
ms.date: 11/04/2016
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
ms.openlocfilehash: d25520c4ffc805701dfe6b51192f8078e2fa300f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365478"
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048: MFC Veritabanı Uygulamaları için ODBC Kurulum ve Yönetim Programları Yazma

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

MFC veritabanı sınıflarını kullanan uygulamaların ODBC bileşenlerini yükleyen bir kurulum programı gerekir. Ayrıca, varsayılan sürücüleri belirtmek ve veri kaynaklarını yapılandırmak için kullanılabilir sürücüler hakkında bilgi alacak bir ODBC Yönetimi programına da ihtiyaç duyabilirler. Bu not, bu programları yazmak için ODBC Installer API kullanımını açıklar.

## <a name="writing-an-odbc-setup-program"></a><a name="_mfcnotes_writing_an_odbc_setup_program"></a>ODBC Kurulum Programı Yazma

Bir MFC veritabanı uygulaması ODBC Sürücü Yöneticisi (ODBC) gerektirir. DLL) ve ODBC sürücüleri veri kaynaklarına ulaşmak mümkün. Birçok ODBC sürücüsü de ek ağ ve iletişim DLLs gerektirir. Çoğu ODBC sürücüsü, gerekli ODBC bileşenlerini yükleyecek bir kurulum programıyla birlikte sevk edilir. MFC veritabanı sınıflarını kullanan uygulama geliştiricileri şunları yapabilir:

- ODBC bileşenlerini yüklemek için sürücüye özel kurulum programlarına güvenin. Bu geliştirici nin parçası üzerinde daha fazla çalışma gerektirmez - sadece sürücünün kurulum programı yeniden dağıtabilirsiniz.

- Alternatif olarak, sürücü yöneticisi ve sürücü yükleyecek kendi kurulum programı yazabilirsiniz.

ODBC yükleyici API uygulamaya özel kurulum programları yazmak için kullanılabilir. Yükleyici API'deki işlevler ODBC yükleyici DLL - ODBCINST tarafından uygulanır. 16 bit Windows ve ODBCCP32 üzerinde DLL. Win32'de DLL. ODBC `SQLInstallODBC` sürücü yöneticisi, ODBC sürücüleri ve gerekli çevirmenler yükler yükleyici DLL, bir uygulama arayabilirsiniz. Daha sonra ODBCINST yüklü sürücüleri ve çevirmenler kaydeder. INI dosyası (veya kayıt defteri, NT üzerinde). `SQLInstallODBC`ODBC için tam yol gerektirir. Yüklenecek sürücülerin listesini içeren ve her sürücüyü oluşturan dosyaları açıklayan INF dosyası. Ayrıca sürücü yöneticisi ve çevirmenler hakkında benzer bilgiler içerir. Odbc. INF dosyaları genellikle sürücü geliştiriciler tarafından sağlanır.

Bir program tek tek ODBC bileşenlerini de yükleyebilir. Sürücü Yöneticisi'ni yüklemek için, `SQLInstallDriverManager` bir program ilk olarak Yükleyici DLL'yi çağırın ve Sürücü Yöneticisi'nin hedef dizinini alır. Bu genellikle Windows DLL'lerin bulunduğu dizindir. Program daha sonra ODBC'nin [ODBC Sürücü Yöneticisi] bölümündeki bilgileri kullanır. Sürücü Yöneticisi ve ilgili dosyaları yükleme diskinden bu dizine kopyalamak için INF dosyası. Tek bir sürücü yüklemek için, `SQLInstallDriver` bir program ilk odbcinst sürücü belirtimi eklemek için yükleyici DLL çağırır. INI dosyası (veya kayıt defteri, NT üzerinde). `SQLInstallDriver`genellikle Windows DLL'lerin bulunduğu dizin olan sürücünün hedef dizinini döndürür. Program daha sonra ODBC'nin sürücü bölümündeki bilgileri kullanır. Sürücü DLL'yi ve ilgili dosyaları yükleme diskinden bu dizine kopyalamak için INF dosyası.

ODBC hakkında daha fazla bilgi için. INF, ODBCINST. INI ve yükleyici API kullanarak, ODBC SDK *Programcı Referans,* Bölüm 19, ODBC Yazılımı yükleme bakın.

## <a name="writing-an-odbc-administrator"></a><a name="_mfcnotes_writing_an_odbc_administrator"></a>ODBC Yöneticisi Yazma

Bir MFC veritabanı uygulaması, ODBC veri kaynaklarını aşağıdaki gibi iki şekilde ayarlayabilir ve yapılandırabilir:

- ODBC Yöneticisi'ni (program olarak veya Denetim Masası öğesi olarak kullanılabilir) kullanın.

- Veri kaynaklarını yapılandırmak için kendi programınızı oluşturun.

Veri kaynaklarını yapılandıran bir program, yükleyici DLL'ye işlev çağrıları yapar. Yükleyici DLL, bir veri kaynağını yapılandırmak için bir kurulum DLL çağırır. Her sürücü için bir kurulum DLL vardır; sürücü DLL kendisi veya ayrı bir DLL olabilir. Kurulum DLL, desteklenirse, sürücünün veri kaynağına ve varsayılan çevirmene bağlanması gereken bilgileri kullanıcıdan ister. Daha sonra yükleyici DLL ve Windows API'ları çağırır ve bu bilgileri ODBC'ye kaydeder. INI dosyası (veya kayıt defteri).

Bir kullanıcının veri kaynaklarını ekleyebileceği, değiştirebileceği ve silebileceği bir `SQLManageDataSources` iletişim kutusu görüntülemek için, bir program yükleyici DLL'de çağırır. Yükleyici DLL Denetim Masası'ndan çağrıldığında bu işlev çağrılır. Bir veri kaynağını eklemek, değiştirmek `SQLManageDataSources` veya `ConfigDSN` silmek için, bu veri kaynağıyla ilişkili sürücü için kurulum DLL'de çağrılar. Veri kaynaklarını doğrudan eklemek, değiştirmek veya silmek için bir program yükleyici DLL'yi çağırır. `SQLConfigDataSource` Program, veri kaynağının adını ve yapılacak eylemi belirten bir seçeneği geçer. `SQLConfigDataSource`kurulum `ConfigDSN` DLL çağırır ve bağımsız değişkenleri `SQLConfigDataSource`geçer .

Daha fazla bilgi için Bkz. ODBC SDK *Programcı Referans,* Bölüm 23, Kurulum DLL İşlev Başvurusu ve Bölüm 24, Installer DLL İşlev Referansı.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
