---
title: 'Veri Kaynağı: Bağlantıları Yönetme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], multiuser environments
- generalizing connection strings
- ODBC [C++], disconnecting from data sources
- connection strings [C++], generalizing
- database connections [C++], creating
- GetDefaultConnect method
- connections [C++], data source
- ODBC connections [C++], configuring
- disconnecting from data sources
- databases [C++], connecting to
- ODBC connections [C++], disconnecting
- data sources [C++], connecting to
- ODBC connections [C++], connecting to data source
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
ms.openlocfilehash: 107a5e20b70f67be74b6e6f861bd539446e9d4ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374525"
---
# <a name="data-source-managing-connections-odbc"></a>Veri Kaynağı: Bağlantıları Yönetme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu açıklar:

- [Nasıl bir veri kaynağı yapılandırmak için](#_core_configuring_a_data_source).

- [Çok kullanıcılı ortamın veri kaynağını ve kayıt kümelerini nasıl etkilediği.](#_core_working_in_a_multiuser_environment)

- [Bir bağlantı dizesini neden bir veri kaynağına genelleştirirsiniz.](#_core_generalizing_the_connection_string)

- [Nasıl bir veri kaynağına bağlanmak için](#_core_connecting_to_a_specific_data_source).

- [Nasıl bir veri kaynağından kesmek için](#_core_disconnecting_from_a_data_source).

- [CDatabase nesnesi nasıl yeniden kullanılır?](#_core_reusing_a_cdatabase_object)

Bir veri kaynağına bağlanmak, verilere erişmek için bir DBMS ile iletişim kurmak anlamına gelir. Bir uygulamadan bir veri kaynağına ODBC sürücüsü aracılığıyla bağlandığınızda, sürücü bağlantıyı yerel olarak veya ağ üzerinden yapar.

ODBC sürücüsüne sahip olduğunuz herhangi bir veri kaynağına bağlanabilirsiniz. Uygulamanızın kullanıcıları da veri kaynağı için aynı ODBC sürücüsüne sahip olmalıdır. ODBC sürücülerinin yeniden dağıtılması hakkında daha fazla bilgi için Bkz. [ODBC Bileşenlerini Müşterilerinize Yeniden Dağıtma.](../../data/odbc/redistributing-odbc-components-to-your-customers.md)

## <a name="configuring-a-data-source"></a><a name="_core_configuring_a_data_source"></a>Veri Kaynağını Yapılandırma

ODBC Administrator, veri kaynaklarınızı yapılandırmak için kullanılır. Yüklemeden sonra veri kaynakları eklemek veya kaldırmak için ODBC Administrator'ı da kullanabilirsiniz. Uygulamalar oluşturduğunuzda, kullanıcılarınızı veri kaynakları eklemelerine izin vermeleri için ODBC Yöneticisi'ne yönlendirebilir veya doğrudan ODBC yükleme çağrıları yaparak bu işlevi uygulamanız haline getirebilirsiniz. Daha fazla bilgi için Bkz. [ODBC Yöneticisi.](../../data/odbc/odbc-administrator.md)

Bir Excel dosyasını veri kaynağı olarak kullanabilirsiniz ve dosyayı kayıtlı olacak ve Veri **Kaynağı Seç** iletişim kutusunda görünecek şekilde yapılandırmanız gerekir.

#### <a name="to-use-an-excel-file-as-a-data-source"></a>Excel dosyasını veri kaynağı olarak kullanmak için

1. Dosyayı ODBC Veri Kaynak Yöneticisi ile yapılandırın.

1. Dosya **DSN** sekmesinde **Ekle'yi**tıklatın.

1. Yeni **Veri Kaynağı Oluştur** iletişim kutusunda bir Excel sürücüsü seçin ve sonra **İleri'yi**tıklatın.

1. **Gözat'ı**tıklatın ve tarih kaynağı olarak kullanılacak dosyanın adını seçin.

> [!NOTE]
> .xls dosyalarını görüntülemek için açılan menüdeki **Tüm Dosyalar'ı** seçmeniz gerekebilir.

1. **İleri**’ye ve ardından **Son**’a tıklayın.

1. **ODBC Microsoft Excel Kurulumu** iletişim kutusunda veritabanı Sürümü ve Çalışma Kitabı'nı seçin.

## <a name="working-in-a-multiuser-environment"></a><a name="_core_working_in_a_multiuser_environment"></a>Çok Kullanıcılı Ortamda Çalışma

Birden çok kullanıcı bir veri kaynağına bağlıysa, siz kayıt kümelerinizde verileri manipüle ederken verileri değiştirebilirler. Benzer şekilde, değişiklikleriniz diğer kullanıcıların kayıt ayarlarını etkileyebilir. Daha fazla bilgi için [bkz: Recordset: Recordssets Update Records (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) ve [Transaction (ODBC)](../../data/odbc/transaction-odbc.md).

## <a name="generalizing-the-connection-string"></a><a name="_core_generalizing_the_connection_string"></a>Bağlantı Dizesini Genelleme

Sihirbazlar, bir veri kaynağına bağlantı kurmak için varsayılan bağlantı dizesini kullanır. Uygulamanızı geliştirirken tabloları ve sütunları görüntülemek için bu bağlantıyı kullanırsınız. Ancak, bu varsayılan bağlantı dizesi, kullanıcılarınızın uygulamanız aracılığıyla veri kaynağına olan bağlantıları için uygun olmayabilir. Örneğin, veri kaynakları ve konumuna giden yol, uygulamanızı geliştirirken kullanılandan farklı olabilir. Bu durumda, [CRecordset yeniden uygulamak gerekir::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) üye işlevi daha genel bir şekilde ve sihirbaz ı uygulama atın. Örneğin, aşağıdaki yaklaşımlardan birini kullanın:

- ODBC Administrator'ı kullanarak bağlantı dizelerini kaydedin ve yönetin.

- Bağlantı dizesini edin ve veri kaynağı adını kaldırın. Çerçeve veri kaynağı olarak ODBC sağlar; çalışma zamanında, ODBC veri kaynağı adını ve gerekli diğer bağlantı bilgilerini soran bir iletişim kutusu görüntüler.

- Yalnızca veri kaynağı adını verin. ODBC gerekirse kullanıcı kimliği ve şifresini sorar. Örneğin, genellemeden önce bağlantı dizesi aşağıdaki gibi görünür:

    ```cpp
    CString CApp1Set::GetDefaultConnect()
    {
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";
    }
    ```

   Bu bağlantı dizesi, Windows NT tümleşik güvenliğini kullanan güvenilir bir bağlantı belirtir. Bunu yapmak büyük bir güvenlik zayıflığı oluşturduğundan, parolayı zorla kodlamaktan veya boş bir parola belirtmekten kaçınmalısınız. Bunun yerine, `GetDefaultConnect` yeni bir bağlantı dizesi böylece bir kullanıcı kimliği ve parola için sorgular verebilirsiniz.

    ```cpp
    // User must select data source and supply user ID and password:
        return "ODBC;";
    // User ID and password required:
        return "ODBC;DSN=mydb;";
    // Password required (myuserid must be replaced with a valid user ID):
        return "ODBC;DSN=mydb;UID=myuserid;";
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";
    ```

## <a name="connecting-to-a-specific-data-source"></a><a name="_core_connecting_to_a_specific_data_source"></a>Belirli bir Veri Kaynağına Bağlanma

Belirli bir veri kaynağına bağlanmak için veri kaynağınızın [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md)ile zaten yapılandırılmış olması gerekir.

#### <a name="to-connect-to-a-specific-data-source"></a>Belirli bir veri kaynağına bağlanmak için

1. Bir `CDatabase` nesne oluştur.

1. Onun `OpenEx` veya `Open` üye işlevini arayın.

Bir sihirbazla belirttiğiniz veri kaynağından başka bir şey sayılsa nasıl belirtilir hakkında daha fazla bilgi için [Bkz. CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [CDatabase::MFC](../../mfc/reference/cdatabase-class.md#open) *Başvurusu'nda*aç.

## <a name="disconnecting-from-a-data-source"></a><a name="_core_disconnecting_from_a_data_source"></a>Veri Kaynağından Bağlantı Kesme

`CDatabase`Üye işlevini çağırmadan `Close` önce tüm açık kayıt kümelerini kapatmanız gerekir. Kapatmak istediğiniz `CDatabase` nesneyle ilişkili kayıt kümelerinde `AddNew` bekleyen `Edit` veya ekstreler iptal edilir ve bekleyen tüm hareketler geri alınır.

#### <a name="to-disconnect-from-a-data-source"></a>Bir veri kaynağından bağlantı kesmek için

1. Nesnenin `CDatabase` [Yakın](../../mfc/reference/cdatabase-class.md#close) üye işlevini arayın.

1. Nesneyi yeniden kullanmak istemiyorsanız yok edin.

## <a name="reusing-a-cdatabase-object"></a><a name="_core_reusing_a_cdatabase_object"></a>CDatabase Nesnesi Yeniden Kullanma

Bir `CDatabase` nesneyi bağlantısını kestikten sonra, ister aynı veri kaynağına yeniden bağlanmak ister farklı bir veri kaynağına bağlanmak için kullanabilirsiniz.

#### <a name="to-reuse-a-cdatabase-object"></a>CDatabase nesnesini yeniden kullanmak için

1. Nesnenin özgün bağlantısını kapatın.

1. Nesneyi yok etmek yerine, nesnenin `OpenEx` veya `Open` üye işlevini yeniden çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Veri Kaynağı: Veri Kaynağının Şemasını Belirleme (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
