---
title: 'TN055: Geçirme MFC ODBC veritabanı sınıfı uygulamalarını MFC DAO sınıflarına'
ms.date: 06/20/2018
f1_keywords:
- vc.mfc.odbc
helpviewer_keywords:
- DAO [MFC], migration
- TN055
- migration [MFC], ODBC database applications
- ODBC classes [MFC], DAO classes
- migrating ODBC database applications [MFC]
- porting database applications to DAO
- ODBC [MFC], DAO
- porting ODBC database applications to DAO
- migrating database applications [MFC]
ms.assetid: 0f858bd1-e168-4e2e-bcd1-8debd82856e4
ms.openlocfilehash: f8e0d8e50f05e86c35e0f8b7f324533bffea6f25
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399674"
---
# <a name="tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes"></a>TN055: Geçirme MFC ODBC veritabanı sınıfı uygulamalarını MFC DAO sınıflarına

> [!NOTE]
> Sihirbazlar ve Visual C++ ortamına DAO (DAO sınıflarına eklenmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, kullanmanızı önerir [OLE DB Şablonları](../data/oledb/ole-db-templates.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) yeni projeler için. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.

## <a name="overview"></a>Genel Bakış

Çoğu durumda MFC ODBC veritabanı sınıfları MFC'nin DAO veritabanı sınıfları için kullanan uygulamaları geçirmek için istenebilir. Bu teknik Not MFC ODBC ve DAO sınıfları arasındaki farklar çoğunu ayrıntılarını verir. Aklınızda farklarla ODBC sınıflardan MFC sınıfları için isterseniz uygulamaları geçirmek aşırı zor olmamalıdır.

## <a name="why-migrate-from-odbc-to-dao"></a>ODBC'den DAO'ya neden geçirme

Pek çok neden DAO veritabanı sınıfları için ODBC veritabanı sınıflarından uygulamaları geçirmek isteyebileceğiniz, ancak kararı mutlaka basit ya da belirgin değil vardır. Akılda tutulması gereken bir şey DAO tarafından kullanılan Microsoft Jet veritabanı altyapısı erişebileceği herhangi bir ODBC veri kaynağı bir ODBC sürücüsüne sahip okunur. ODBC veritabanı sınıfları kullanın veya kendiniz ancak Microsoft Jet veritabanı altyapısı, ODBC veri okuyabilirsiniz doğrudan ODBC arama daha verimli olabilir.

ODBC/DAO kararı kolaylaştırmak bazı basit durumlar. Örneğin, yalnızca verilere (erişim biçimi, Excel biçiminde ve benzeri) belirgin seçim DAO veritabanı sınıfları kullanmaktır doğrudan Microsoft Jet motoru okuyabilen bir biçimde erişim gerektiğinde.

Daha karmaşık durumlarda, bir sunucuda veya farklı sunuculara çeşitli verilerinizi mevcut olduğunda ortaya çıkar. Bu durumda, ODBC veritabanı sınıfları veya DAO veritabanı sınıfları karar zor bir bilgisayardır. İsterseniz heterojen birleşimler (SQL Server ve Oracle gibi çoklu biçimlerde sunuculardan verileri birleştirme) gibi şeyler yapın ve ardından Microsoft Jet veritabanı altyapısı, yerine için ODBC veritabanı kullanıyorsanız gerekli iş yapmak zorunda birleşim gerçekleştirir Sınıflar ya da çağrılan ODBC'yi doğrudan. Sürücü imleçler destekleyen bir ODBC sürücüsü kullanıyorsanız, en iyi seçimdir ODBC veritabanı sınıfları olabilir.

Özel gereksinimlerinize verilen çeşitli yöntemlerin performansını test etmek için bazı örnek kodlar yazmak isteyebilirsiniz seçim karmaşık, olabilir. Bu teknik Not, ODBC veritabanı sınıflarından DAO veritabanı sınıfları için geçiş kararı yaptığınız varsayılmaktadır.

## <a name="similarities-between-odbc-database-classes-and-mfc-dao-database-classes"></a>ODBC veritabanı sınıfları ve MFC DAO veritabanı sınıfları arasındaki benzerlikler

MFC ODBC sınıfları, özgün tasarımda Microsoft Access ve Microsoft Visual Basic kullanımda olan DAO nesne modelinde temel alınmıştır. Bu, tüm bu bölümde listelenen ODBC ve MFC DAO sınıflarını pek çok ortak özelliği olduğu anlamına gelir. Genel olarak, programlama modelleri aynıdır.

Bazı benzerlikler vurgulamak için:

- ODBC ve DAO sınıflarını temel alınan veritabanı yönetim sistemi (DBMS)'ni kullanarak veritabanı nesneleri vardır.

- Her ikisi de kayıt nesneleri temsil eden bir o DBMS döndürülen sonuç kümesi vardır.

- DAO veritabanı ve kayıt nesneleri üyeleri ODBC sınıfları için neredeyse aynı sahiptir.

- Her iki sınıfları kümesi ile verileri almak için kod bazı nesne ve üye ad değişiklikleri hariç aynıdır. Değişiklikleri gerekir ancak genellikle bir kolay ad değişikliği ODBC sınıflardan DAO sınıflarına geçiş yaparken işlemidir.

Örneğin, her iki modelleri oluşturma ve bir veritabanı nesnesi açmak, oluşturmak ve bir kayıt kümesi nesnesi açılamadı ve (taşıma), ancak bazı işlemi verilerde gezinme için verileri almak için yordam aynıdır.

## <a name="differences-between-odbc-and-dao-mfc-classes"></a>ODBC ve MFC DAO sınıfları arasındaki farklar

DAO sınıfları daha fazla nesne ve daha zengin bir yöntemler kümesine dahil, ancak bu bölüm yalnızca benzer sınıfları ve işlevleri farklılıkları ayrıntılarını kaydeder.

Sınıflar arasındaki en belirgin farklar benzer sınıflar ve genel işlevler için ad değişiklikleri olabilirsiniz. Aşağıdaki liste, ad değişiklikleri nesneleri, yöntemleri ve veritabanı sınıfları ile ilgili genel işlevleri gösterir:

|Sınıf veya işlev|MFC DAO sınıflarına eşdeğeri|
|-----------------------|-----------------------------------|
|`CDatabase`|`CDaoDatabase`|
|`CDatabase::ExecuteSQL`|`CDaoDatabase::Execute`|
|`CRecordset`|`CDaoRecordset`|
|`CRecordset::GetDefaultConnect`|`CDaoRecordset::GetDefaultDBName`|
|`CFieldExchange`|`CDaoFieldExchange`|
|`RFX_Bool`|`DFX_Bool`|
|`RFX_Byte`|`DFX_Byte`|
|`RFX_Int`|`DFX_Short`|
|`RFX_Long`|`DFX_Long`|
||`DFX_Currency`|
|`RFX_Single`|`DFX_Single`|
|`RFX_Double`|`DFX_Double`|
|`RFX_Date`<sup>1</sup>|`DFX_Date` (`COleDateTime`-tabanlı)|
|`RFX_Text`|`DFX_Text`|
|`RFX_Binary`|`DFX_Binary`|
|`RFX_LongBinary`|`DFX_LongBinary`|

<sup>1</sup> `RFX_Date` işlevi temel `CTime` ve `TIMESTAMP_STRUCT`.

Uygulamanızı etkileyebilecek ve birden fazla basit adı değişikliği gerektiren önemli değişiklikler işlevine aşağıda listelenmiştir.

- Kayıt kümesi gibi şeyleri açık tür ve Employee seçenekleri belirtmek için kullanılan makrolar ve sabitler değiştirildi.

   ODBC sınıfları ile MFC makroları aracılığıyla bu seçenekleri tanımlamak için gerekli veya numaralandırılmış türler.

   DAO sınıfları ile DAO üstbilgi dosyasında (DBDAOINT. Bu seçenekler tanımını sağlar. H). Bu nedenle kayıt kümesi bir listeden seçimli üyesidir `CRecordset`, ancak DAO ile bir sabit yerine. Örneğin kullanırsınız **anlık görüntü** türünü belirtirken `CRecordset` ODBC'de ancak **DB_OPEN_SNAPSHOT** türünü belirtirken `CDaoRecordset`.

- Varsayılan kayıt türü `CRecordset` olduğu **anlık görüntü** while için varsayılan kayıt türü `CDaoRecordset` olduğu **dynaset** (ODBC sınıf anlık görüntüler hakkında ek sorun için aşağıdaki nota bakın).

- ODBC `CRecordset` sınıfı salt iletme kayıt kümesi türü oluşturma seçeneğiniz vardır. İçinde `CDaoRecordset` sınıfı, yalnızca iletme bir kayıt kümesi türü, ancak bunun yerine bir özellik (veya seçeneği) kümelerinin belirli bir türde değil.

- Açılırken yalnızca ekleme yapılabilen bir kayıt bir `CRecordset` nesne kümesinin veri okumak ve eklenmiş olduğunu geliyordu. İle `CDaoRecordset` nesnesi salt ekleme seçeneği olabileceği anlamına gelir tam anlamıyla veri kümesinin yalnızca eklenebilir (ve okuma değil).

- ODBC sınıfları işlem üye işlevleri üyeleri `CDatabase` ve veritabanı düzeyinde harekete geçin. DAO sınıfları işlem üye işlevleri daha yüksek düzey bir sınıf üyeleri (`CDaoWorkspace`) ve böylece birden çok etkileyebilir `CDaoDatabase` (işlem alanı) aynı çalışma alanını paylaşan nesneler.

- Özel durum sınıfı değiştirildi. `CDBExceptions` ODBC sınıfları oluşturulur ve `CDaoExceptions` DAO sınıflardaki.

- `RFX_Date` kullanan `CTime` ve `TIMESTAMP_STRUCT` sırasında nesneleri `DFX_Date` kullanan `COleDateTime`. `COleDateTime` Hemen hemen aynıdır `CTime`, üzerinde bir 8 baytlık OLE dayanır ancak **tarih** 4 baytlık yerine **time_t** çok daha geniş bir yelpazede veri içerebileceği için.

   > [!NOTE]
   > DAO (`CDaoRecordset`) sırasında ODBC salt okunur anlık görüntüler (`CRecordset`) anlık görüntüleri sürücü ve ODBC imleç kitaplığı kullanımına bağlı olarak güncelleştirilebilir. İmleç kitaplığı kullanıyorsanız `CRecordset` anlık görüntüleri güncelleştirilebilir. ODBC imleç kitaplığını kullanmadan Microsoft sürücüleri Masaüstü Sürücü Paketi 3.0 kullanıyorsanız, `CRecordset` anlık görüntüleri salt okunurdur. Başka bir sürücü kullanıyorsanız olmadığını görmek için sürücünün belgelere bakın. anlık görüntüler (`STATIC_CURSORS`) salt okunurdur.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
