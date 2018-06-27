---
title: 'TN048: MFC veritabanı uygulamaları için ODBC Kurulum ve yönetim programları yazma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.odbc
dev_langs:
- C++
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7d89b6c6e05a5baf973abace2c64de3b52754f5
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954563"
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048: MFC Veritabanı Uygulamaları için ODBC Kurulum ve Yönetim Programları Yazma
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 MFC veritabanı sınıfları kullanan uygulamalar ODBC bileşenlerini yükler bir Kurulum programı gerekir. Bunlar ayrıca varsayılan sürücüleri belirtmek ve veri kaynaklarını yapılandırmak için kullanılabilir sürücüler hakkında bilgi alacak bir ODBC yönetim programı gerekebilir. Bu Not Bu programları yazmak için ODBC Yükleyici API kullanımını açıklar.  
  
##  <a name="_mfcnotes_writing_an_odbc_setup_program"></a> Bir ODBC Kurulum programı yazma  
 ODBC Sürücü Yöneticisi'ni (ODBC. bir MFC veritabanı uygulaması gerektirir DLL) ve veri kaynaklarına elde edebilmek için ODBC sürücüleri. Birçok ODBC sürücüsü için ek ağ ve iletişim DLL'leri de gerekir. Çoğu ODBC sürücüleri gerekli ODBC bileşenlerini yükleyecek bir Kurulum programı ile birlikte. MFC veritabanı sınıfları kullanan uygulama geliştiriciler şunları yapabilir:  
  
-   ODBC bileşenleri yüklemek için sürücü özgü kurulum programları kullanır. Bu Geliştirici Bölümü çalışmayı başka gerektirir — yalnızca sürücünün Kurulum programını yeniden dağıtabilirsiniz.  
  
-   Alternatif olarak, sürücü yöneticisi ve sürücüsü yükleyecek kendi kurulum programını yazabilirsiniz.  
  
 ODBC Installer API'sı, uygulamaya özgü kurulum programları yazmak için kullanılabilir. Yükleyici API işlevlerinde DLL ODBC Yükleyici tarafından uygulanan — ODBCINST. 16 bit Windows ve ODBCCP32 DLL. Win32 DLL. Bir uygulamanın çağırabileceği `SQLInstallODBC` yükleyicisinde ODBC Sürücü Yöneticisi, ODBC sürücüleri ve herhangi bir yükleyecek DLL çevirmenler gerekli. Bunu daha sonra yüklenen sürücüleri ve çevirmenler ODBCINST kaydeder. INI dosyası (veya kayıt defteri NT üzerinde). `SQLInstallODBC` ODBC tam yolunu gerektirir. Yüklenecek sürücülerin listesini içeren ve her bir sürücü oluşturan dosyaların açıklar INF dosyası. Sürücü Yöneticisi ve çevirmenler hakkındaki benzer bilgileri de içerir. ODBC. INF dosyaları genellikle sürücü geliştiriciler tarafından sağlanır.  
  
 Bir program ODBC bileşenleri tek tek de yükleyebilirsiniz. Sürücü Yöneticisi'ni yüklemek için bir program çağırdığı `SQLInstallDriverManager` hedef dizin için Sürücü Yöneticisi almak için DLL yükleyicisinde. Bu genellikle Windows DLL'leri bulunduğu dizindir. Program, daha sonra ODBC [ODBC Sürücü Yöneticisi] bölümünde bilgileri kullanır. INF dosyası ilgili dosyaları ve sürücü yöneticisini yükleme diskinden bu dizine kopyalayın. Tek bir sürücü yüklemek için bir programı çağırır `SQLInstallDriver` sürücüsü belirtimi ODBCINST eklemek için DLL yükleyicisinde. INI dosyası (veya kayıt defteri NT üzerinde). `SQLInstallDriver` sürücünün hedef dizinini döndürür — genellikle Windows DLL'leri bulunduğu dizin. Program, daha sonra ODBC sürücünün bölümünde bilgileri kullanır. INF dosyası sürücüsü DLL ve ilişkili dosyaları yükleme diskinden bu dizine kopyalayın.  
  
 ODBC hakkında daha fazla bilgi için. INF, ODBCINST. INI ve API, Yükleyicisi'ni kullanarak bkz ODBC SDK *Programcının Başvurusu* Bölüm 19, ODBC yazılım yükleme.  
  
##  <a name="_mfcnotes_writing_an_odbc_administrator"></a> ODBC Yöneticisi yazma  
 MFC veritabanı uygulaması ayarlayabilir ve ODBC veri kaynakları gibi iki yoldan birini yapılandırın:  
  
-   ODBC Yöneticisi (bir programı veya Denetim Masası öğesi olarak kullanılabilir) kullanın.  
  
-   Veri kaynaklarını yapılandırmak için kendi program oluşturun.  
  
 Veri kaynakları yapılandırır bir program yükleyici DLL işlev çağrılarını yapar. DLL Installer kurulum bir veri kaynağını yapılandırmak için DLL çağırır. Her sürücü için bir kurulum DLL yoktur; DLL kendisini sürücünün veya ayrı bir DLL olabilir. DLL Kurulum, sürücü veri kaynağı ve varsayılan çeviricisi destekleniyorsa bağlanmak için gereken bilgileri kullanıcıya sorar. Daha sonra yükleyici DLL ve Windows API'ları ODBC bu bilgileri kaydetmek için çağırır. INI dosyası (veya kayıt defteri).  
  
 Bir iletişim kutusu ile bir kullanıcı ekleyebilir, değiştirebilir ve veri kaynaklarını silme görüntülemek için bir program çağırır `SQLManageDataSources` DLL yükleyicisinde. Bu işlev, yükleyici Denetim Masası'ndan DLL çağrıldığında çağrılır. Ekleme, değiştirme ve bir veri kaynağını silmek için `SQLManageDataSources` çağrıları `ConfigDSN` o veri kaynağıyla ilişkili sürücüsünü Kurulum DLL. Doğrudan eklemek, değiştirmek veya veri silmek için kaynakları, bir program `SQLConfigDataSource` DLL yükleyicisinde. Program veri kaynağı ve gerçekleştirilecek eylemi belirtir. bir seçenek adını geçirir. `SQLConfigDataSource` çağrıları `ConfigDSN` DLL kurulumunda ve bağımsız değişkenlerden geçirir `SQLConfigDataSource`.  
  
 Daha fazla bilgi için bkz: ODBC SDK *Programcının Başvurusu* Bölüm 23, Kurulum DLL işlev başvurusu ve Bölüm 24, yükleyici DLL işlev başvurusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

