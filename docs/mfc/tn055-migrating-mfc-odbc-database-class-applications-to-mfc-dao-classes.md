---
title: 'TN055: MFC ODBC Veritabanı Sınıfı Uygulamalarını MFC DAO Sınıflarına Geçirme'
ms.date: 09/17/2019
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
ms.openlocfilehash: 744e1c71476ccfbe6ea8f8359dcdb9a29efc995e
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305375"
---
# <a name="tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes"></a>TN055: MFC ODBC Veritabanı Sınıfı Uygulamalarını MFC DAO Sınıflarına Geçirme

> [!NOTE]
> DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir. Visual C++ ortamı ve sihirbazları DAO 'yu desteklemez (DAO sınıfları dahil edilir ancak yine de kullanabilirsiniz). Microsoft, yeni projeler için [OLE DB şablonlarını](../data/oledb/ole-db-templates.md) veya [ODBC 'yi ve MFC 'yi](../data/odbc/odbc-and-mfc.md) kullanmanızı önerir. Yalnızca var olan uygulamaları korumak için DAO kullanmanız gerekir.

## <a name="overview"></a>Genel Bakış

Çoğu durumda, MFC 'nin ODBC veritabanı sınıflarını kullanan uygulamaların, MFC 'nin DAO veritabanı sınıflarına geçirilmesi istenebilir. Bu teknik notta, MFC ODBC ve DAO sınıfları arasındaki farklılıkların çoğu ayrıntılandıralınacaktır. Farklar göz önünde bulundurularak, ODBC sınıflarından uygulamaları istenirse MFC sınıflarına geçirmek aşırı zor olmamalıdır.

## <a name="why-migrate-from-odbc-to-dao"></a>Neden ODBC 'den DAO 'ya geçiş

ODBC veritabanı sınıflarından uygulamaları DAO veritabanı sınıflarına geçirmek isteyebileceğiniz birçok neden vardır, ancak karar basit veya belirgin değildir. Göz önünde bulundurmanız gereken tek şey, DAO tarafından kullanılan Microsoft Jet veritabanı altyapısının, ODBC sürücünüze sahip olduğunuz herhangi bir ODBC veri kaynağını okuyabileceği bir şeydir. ODBC veritabanı sınıflarını kullanmak veya ODBC 'yi doğrudan kendiniz çağırmak daha verimli olabilir, ancak Microsoft Jet veritabanı altyapısı ODBC verilerini okuyabilir.

ODBC/DAO kararını kolay hale getirmek için bazı basit durumlar. Örneğin, yalnızca Microsoft Jet motorunun doğrudan okuyabilmesini sağlayan bir biçimde verilere erişmeniz gerektiğinde (erişim biçimi, Excel biçimi vb.), DAO veritabanı sınıflarını kullanmak da açıktır.

Verileriniz bir sunucuda veya çeşitli farklı sunucularda olduğunda daha karmaşık durumlar oluşur. Bu durumda, ODBC veritabanı sınıflarını veya DAO veritabanı sınıflarını kullanma kararı zor bir durumdur. Heterojen birleşimler (SQL Server ve Oracle gibi birden çok biçimdeki sunuculardan veri birleştirme) gibi şeyler yapmak istiyorsanız, Microsoft Jet veritabanı altyapısı, ODBC veritabanını kullandıysanız gerekli olan işleri gerçekleştirmenize zorlamak yerine sizin için birleştirme işlemi gerçekleştirir Veya ODBC doğrudan olarak adlandırılır. Sürücü imleçlerini destekleyen bir ODBC sürücüsü kullanıyorsanız en iyi seçiminiz ODBC veritabanı sınıfları olabilir.

Seçim karmaşık olabilir, bu nedenle özel gereksinimleriniz verilen çeşitli yöntemlerin performansını test etmek için bazı örnek kodlar yazmak isteyebilirsiniz. Bu teknik notta ODBC veritabanı sınıflarından DAO veritabanı sınıflarına geçiş kararı verdiğinizi varsayılmaktadır.

## <a name="similarities-between-odbc-database-classes-and-mfc-dao-database-classes"></a>ODBC veritabanı sınıfları ve MFC DAO veritabanı sınıfları arasındaki benzerlikler

MFC ODBC sınıflarının orijinal tasarımı, Microsoft Access ve Microsoft Visual Basic 'da kullanımda olan DAO nesne modelini temel alır. Bu, ODBC ve DAO MFC sınıflarının pek çok ortak özelliği olduğu anlamına gelir. Bu, hepsi bu bölümde listelenmeyecektir. Genellikle, programlama modelleri aynıdır.

Birkaç benzerlikleri vurgulamak için:

- ODBC ve DAO sınıflarının her ikisi de temel alınan veritabanı yönetim sistemi (DBMS) kullanılarak yöneten veritabanı nesnelerine sahiptir.

- Her ikisinde de, bu DBMS 'den döndürülen sonuç kümesini temsil eden kayıt kümesi nesneleri vardır.

- DAO veritabanı ve kayıt kümesi nesneleri, ODBC sınıflarıyla neredeyse özdeş üyelere sahiptir.

- Her iki sınıf kümesiyle, veri alma kodu, bazı nesne ve üye adı değişiklikleri dışında aynıdır. Değişiklikler gerekli olacaktır, ancak genellikle işlem ODBC sınıflarından DAO sınıflarına geçiş yaparken doğrudan bir ad değişir.

Örneğin, her iki modelde de veri alma yordamı, bir veritabanı nesnesi oluşturup açmak, bir kayıt kümesi nesnesi oluşturup açmak ve bir işlem gerçekleştirerek veri (taşı) ile gezinmeleridir.

## <a name="differences-between-odbc-and-dao-mfc-classes"></a>ODBC ve DAO MFC sınıfları arasındaki farklılıklar

DAO sınıfları daha fazla nesne ve daha zengin bir yöntemler kümesi içerir, ancak bu bölüm yalnızca benzer sınıflarda ve işlevlerde farkları ayrıntılandırır.

Sınıflar arasındaki en belirgin farklılıklar büyük olasılıkla benzer sınıflar ve genel işlevler için ad değişiklikleridir. Aşağıdaki listede, veritabanı sınıflarıyla ilişkili nesneler, Yöntemler ve genel işlevlerin ad değişiklikleri gösterilmektedir:

|Sınıf veya işlev|MFC DAO sınıflarında eşdeğer|
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
|`RFX_Date`<sup>1</sup>|`DFX_Date` (`COleDateTime`tabanlı)|
|`RFX_Text`|`DFX_Text`|
|`RFX_Binary`|`DFX_Binary`|
|`RFX_LongBinary`|`DFX_LongBinary`|

<sup>1</sup> `RFX_Date` işlevi `CTime` ve `TIMESTAMP_STRUCT`temel alır.

İşlevselliğe yapılan önemli değişiklikler, uygulamanızı etkileyebilecek ve basit ad değişikliklerinin daha fazlasını gerektirenlerin aşağıda listelenmiştir.

- Kayıt kümesi açık türü ve kayıt kümesi açma seçenekleri gibi şeyleri belirtmek için kullanılan sabitler ve makrolar değiştirilmiştir.

   ODBC sınıfları MFC ile bu seçenekleri makrolar veya numaralandırılmış türler aracılığıyla tanımlamak için gereklidir.

   DAO sınıfları ile, DAO bu seçeneklerin tanımını bir başlık dosyasında (DBDAOINT) sağlar. H). Bu nedenle, kayıt kümesi türü `CRecordset`numaralandırılmış bir üyesidir, ancak DAO ile bunun yerine bir sabittir. Örneğin, ODBC 'de `CRecordset` türünü belirtirken, ancak `CDaoRecordset`türünü belirtirken **db_open_snapshot** **anlık görüntü** kullanırsınız.

- `CRecordset` için varsayılan kayıt kümesi türü, `CDaoRecordset` için varsayılan kayıt kümesi türü **Dynaset** olduğundan, **anlık görüntüdür** (ODBC sınıfı anlık görüntüleri hakkında ek bir sorun için aşağıdaki nota bakın).

- ODBC `CRecordset` sınıfında yalnızca bir salt iletme kayıt kümesi türü oluşturma seçeneği vardır. `CDaoRecordset` sınıfında, ileri salt bir kayıt kümesi türü değildir, bunun yerine belirli kayıt kümeleri türlerinin bir özelliği (veya seçeneği) değildir.

- Bir `CRecordset` nesnesini açarken yalnızca bir Append kayıt kümesi, kayıt kümesi verilerinin okunmasının ve eklenebileceği anlamına gelir. `CDaoRecordset` nesnesi ile, yalnızca APPEND seçeneği, kayıt kümesinin verilerinin yalnızca eklenebileceği (ve okunmayacağı) anlamına gelir.

- ODBC sınıfları işlem üyesi işlevleri `CDatabase` üyeleridir ve veritabanı düzeyinde çalışır. DAO sınıflarında, işlem üyesi işlevleri daha yüksek düzey bir sınıfın (`CDaoWorkspace`) üyeleridir ve bu nedenle aynı çalışma alanını (işlem alanı) paylaşan birden çok `CDaoDatabase` nesnesini etkileyebilir.

- Özel durum sınıfı değiştirildi. `CDBExceptions` ODBC sınıflarında oluşturulur ve DAO sınıflarında `CDaoExceptions`.

- `RFX_Date`, `DFX_Date` `COleDateTime`kullandığından `CTime` ve `TIMESTAMP_STRUCT` nesnelerini kullanır. `COleDateTime`, `CTime`neredeyse aynıdır, ancak 4 baytlık **time_t** yerine 8 BAYTLıK bir OLE **tarihini** temel alır, böylece çok daha büyük bir veri aralığı olabilir.

   > [!NOTE]
   > DAO (`CDaoRecordset`) anlık görüntüleri salt okunurdur ve ODBC (`CRecordset`) anlık görüntüleri, ODBC imleç kitaplığının sürücüsüne ve kullanımına bağlı olarak güncelleştirilebilir. İmleç kitaplığını kullanıyorsanız, `CRecordset` anlık görüntüleri güncelleştirilebilir. ODBC imleç kitaplığı olmadan masaüstü sürücü paketi 3,0 ' den Microsoft sürücülerinden herhangi birini kullanıyorsanız, `CRecordset` anlık görüntüleri salt okunurdur. Başka bir sürücü kullanıyorsanız, anlık görüntülerin (`STATIC_CURSORS`) salt okunurdur olup olmadığını görmek için sürücünün belgelerini denetleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
