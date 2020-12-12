---
description: 'Hakkında daha fazla bilgi edinin: TN048: MFC veritabanı uygulamaları için ODBC kurulum ve yönetim programları yazma'
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
ms.openlocfilehash: bca8616bae8f7243b9e66b2eccc980afa3865842
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215111"
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048: MFC Veritabanı Uygulamaları için ODBC Kurulum ve Yönetim Programları Yazma

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

MFC veritabanı sınıflarını kullanan uygulamalar, ODBC bileşenlerini yükleyen bir kurulum programına gerek duyar. Ayrıca, varsayılan sürücüleri belirtmek ve veri kaynaklarını yapılandırmak için kullanılabilir sürücüler hakkında bilgi alacak bir ODBC yönetim programı da gerekebilir. Bu notta, bu programları yazmak için ODBC Yükleyici API 'sinin kullanımı açıklanmaktadır.

## <a name="writing-an-odbc-setup-program"></a><a name="_mfcnotes_writing_an_odbc_setup_program"></a> ODBC Kurulum programı yazma

MFC veritabanı uygulaması, veri kaynaklarına ulaşmak için ODBC Sürücü Yöneticisi (ODBC.DLL) ve ODBC sürücülerinin kullanılmasını gerektirir. Birçok ODBC sürücüsü ek ağ ve iletişim dll 'Leri de gerektirir. Çoğu ODBC sürücüsü, gerekli ODBC bileşenlerini yükleyecek bir kurulum programıyla birlikte gönderilir. MFC veritabanı sınıflarını kullanan uygulama geliştiricileri şunları yapabilir:

- ODBC bileşenlerini yüklemek için sürücüye özgü kurulum programlarını kullanır. Bu işlem, geliştirici bölümünde başka iş gerektirmez. sürücünün Kurulum programını yeniden dağıtabilirsiniz.

- Alternatif olarak, kendi kurulum programınızı yazabilirsiniz, bu da sürücü yöneticisini ve sürücüyü yükler.

ODBC yükleyicisi API 'SI uygulamaya özgü kurulum programlarını yazmak için kullanılabilir. Yükleyici API 'sindeki işlevler, 16 bit Windows üzerinde ODBCINST.DLL ve Win32 üzerinde ODBCCP32.DLL ODBC yükleyici DLL 'SI tarafından uygulanır. Bir uygulama, `SQLInstallODBC` ODBC Sürücü Yöneticisi, ODBC sürücüleri ve gerekli çevirmenleri yükleyen YÜKLEYICI dll 'de çağırabilir. Daha sonra, yüklü sürücüleri ve çeviricileri ODBCINST.INI dosyasına (veya sunucudaki kayıt defteri) kaydeder. `SQLInstallODBC` ODBC için tam yolu gerektirir. Yüklenecek sürücülerin listesini içeren INF dosyası ve her bir sürücüyü oluşturan dosyaları açıklar. Ayrıca sürücü yöneticisi ve Çeviricileri hakkında benzer bilgiler içerir. İsti. INF dosyaları genellikle sürücü geliştiricileri tarafından sağlanır.

Bir program, tek tek ODBC bileşenlerini de yükleyebilir. Sürücü Yöneticisi 'ni yüklemek için, bir program ilk olarak `SQLInstallDriverManager` sürücü yöneticisinin hedef dizinini almak üzere YÜKLEYICI dll 'de çağırır. Bu genellikle Windows dll 'Lerinin bulunduğu dizindir. Daha sonra program, ODBC 'nin [ODBC Sürücü Yöneticisi] bölümündeki bilgileri kullanır. INF dosyası yükleme diskinden sürücü yöneticisini ve ilgili dosyaları bu dizine kopyalamak için. Tek bir sürücü yüklemek için, bir program, `SQLInstallDriver` sürücü belirtimini ODBCINST.INI dosyasına (veya NT 'de kayıt defteri) eklemek için ilk olarak YÜKLEYICI dll 'de çağırır. `SQLInstallDriver` sürücünün hedef dizinini (genellikle Windows dll 'Lerinin bulunduğu dizin) döndürür. Daha sonra program, ODBC 'nin sürücü bölümündeki bilgileri kullanır. Dosya DLL 'sini ve ilgili dosyaları yükleme diskinden bu dizine kopyalamak için INF dosyası.

ODBC hakkında daha fazla bilgi için. INF, ODBCINST.INI ve Yükleyici API 'sini kullanarak, ODBC yazılım yükleme adlı bkz. ODBC SDK *Programcı başvurusu,* Bölüm 19.

## <a name="writing-an-odbc-administrator"></a><a name="_mfcnotes_writing_an_odbc_administrator"></a> ODBC Yöneticisi yazma

MFC veritabanı uygulaması, ODBC veri kaynaklarını aşağıdaki şekilde iki şekilde ayarlayabilir ve yapılandırabilir:

- ODBC Yöneticisi 'ni (bir program veya Denetim Masası öğesi olarak kullanılabilir) kullanın.

- Veri kaynaklarını yapılandırmak için kendi programınızı oluşturun.

Veri kaynaklarını yapılandıran bir program, yükleyici DLL 'ye işlev çağrıları yapar. Yükleyici DLL 'si bir veri kaynağını yapılandırmak için bir kurulum DLL 'si çağırır. Her sürücü için bir kurulum DLL 'SI vardır; Bu, sürücü DLL 'inin kendisi veya ayrı bir DLL olabilir. Kurulum DLL 'SI, kullanıcıdan sürücünün veri kaynağına bağlanması için gereken bilgileri ve destekleniyorsa varsayılan çeviriciyi ister. Daha sonra bu bilgileri ODBC.INI dosyasına (veya kayıt defteri) kaydetmek için yükleyici DLL ve Windows API 'Lerini çağırır.

Bir kullanıcının veri kaynaklarını ekleyebileceği, değiştirebileceği ve silebileceği bir iletişim kutusu göstermek için, `SQLManageDataSources` YÜKLEYICI dll 'de bir program çağırır. Bu işlev, yükleyici DLL 'SI denetim masasından çağrıldığında çağrılır. Veri kaynağı eklemek, değiştirmek veya silmek için, `SQLManageDataSources` `ConfigDSN` Bu veri kaynağıyla ilişkili sürücü IÇIN kurulum dll 'de çağrılar yapın. Veri kaynaklarını doğrudan eklemek, değiştirmek veya silmek için, `SQLConfigDataSource` YÜKLEYICI dll 'de bir program çağırır. Program, veri kaynağının adını ve yapılacak eylemi belirten bir seçeneği geçirir. `SQLConfigDataSource``ConfigDSN`Kurulum dll 'de çağırır ve içindeki bağımsız değişkenleri geçirir `SQLConfigDataSource` .

Daha fazla bilgi için bkz. ODBC SDK *Programcı başvurusu,* Bölüm 23, kurulum dll işlev başvurusu ve Bölüm 24, yükleyici dll işlev başvurusu.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
