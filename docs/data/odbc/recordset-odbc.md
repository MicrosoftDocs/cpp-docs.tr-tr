---
title: Kayıt Kümesi (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, snapshots
- recordsets, creating
- dynamic recordsets
- forward-only recordsets
- recordsets, dynasets
- ODBC recordsets, CRecordset objects
- ODBC recordsets
- recordsets, about recordsets
- snapshots, ODBC recordsets
- dynasets
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
ms.openlocfilehash: d16087722752b7bbdabd37410908c7ea2ae18ceb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435262"
---
# <a name="recordset-odbc"></a>Kayıt Kümesi (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

A [CRecordset](../../mfc/reference/crecordset-class.md) nesnesi, bir veri kaynağından seçilen kayıt kümesini temsil eder. Kayıtları olabilir:

- Bir tablo.

- Sorgu.

- Bir veya daha fazla tablo erişen bir saklı yordam.

Bir tabloyu temel alan bir kayıt kümesi "tüm müşteriler,", bir müşteri tablosu erişen örneğidir. Bir sorgu, "tüm faturalara Joe Smith için" örneğidir Bir saklı yordama (bazen önceden tanımlanmış sorgu olarak adlandırılır) bağlı bir kayıt kümesi "tüm ödenmemiş hesapları" örneğidir arka uç veritabanında bir saklı yordam çağırır. Bir kayıt kümesi iki veya daha fazla aynı veri kaynağından alınan tablolar ancak değil farklı veri kaynaklarından alınan tablolar katılabilirsiniz.

> [!NOTE]
>  Kayıt kümesi sınıfları sihirbazlarıyla türetme hakkında daha fazla bilgi için bkz [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md) ve [veritabanı desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md).

> [!NOTE]
>  Veritabanı görünümlerini bazı ODBC sürücüleri destekler. Bu bağlamdaki bir görünüm başlangıçta SQL ile oluşturulan bir sorgudur `CREATE VIEW` deyimi. Sihirbazlar görünümleri şu anda desteklemez, ancak bu desteğin kodunu kendiniz yazmak mümkündür.

##  <a name="_core_recordset_capabilities"></a> Kayıt kümesi özellikleri

Tüm kayıt nesneleri aşağıdaki özellikleri paylaşır:

- Veri kaynağı salt okunur durumda değilse, kayıt olması gerektiğini belirtebilirsiniz [güncelleştirilebilir](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [eklenebilir](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), veya salt okunur. Kayıt kümesi güncelleştirilebilir, iyimser veya kötümser seçebilirsiniz [kilitleme](../../data/odbc/recordset-locking-records-odbc.md) yöntemleri, sağlanan sürücü uygun kilitleme desteği sağlar. Veri kaynağı salt okunur ise, kayıt kümesinin salt okunur olacaktır.

- Üye işlevler çağırabilir [kaydırma](../../data/odbc/recordset-scrolling-odbc.md) seçilen kayıtlar arasında.

- Yapabilecekleriniz [filtre](../../data/odbc/recordset-filtering-records-odbc.md) kaydeden kullanılabilir bu seçili sınırlamak için kayıtları.

- Yapabilecekleriniz [sıralama](../../data/odbc/recordset-sorting-records-odbc.md) kayıtları artan veya azalan düzende bir veya daha fazla sütuna bağlı.

- Yapabilecekleriniz [Parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) çalışma zamanında kayıt seçimi nitelemek için kayıt kümesi.

##  <a name="_core_snapshots_and_dynasets"></a> Anlık görüntüler ve dinamik kümeler

Kayıt kümeleri asıl iki tür vardır: [anlık görüntüleri](../../data/odbc/snapshot.md) ve [dynaset'ler](../../data/odbc/dynaset.md). Sınıfı tarafından desteklenen `CRecordset`. Her tüm kayıt kümelerini genel özelliklerini paylaşır, ancak her Ayrıca ortak işlevsellik kendi özelleştirilmiş şekilde genişletir. Anlık görüntüleri, verilerin statik görünümünü sağlar ve raporların ve belirli bir zamandaki gibi verilerin görünümünü istediğiniz diğer durumlarda yararlıdır. Dynaset'ler kayıt kümesinde yeniden sorgulama veya kayıt yenileyin gerek kalmadan görülebilmesi için diğer kullanıcılar tarafından yapılan güncelleştirmeler istediğinizde yararlıdır. Anlık görüntüler ve dinamik kümeler, güncelleştirilebilir veya salt okunur olabilir. Eklenen kayıtları veya diğer kullanıcılar tarafından silinmiş çağıracak [CRecordset::Requery](../../mfc/reference/crecordset-class.md#requery).

`CRecordset` diğer iki tür kayıt kümeleri için de sağlar: dinamik kayıt kümeleri ve salt iletme kayıt kümeleri. Dynaset'ler için dinamik kayıt kümeleri benzerdir; Ancak, dinamik kayıt kümeleri eklendiğinde veya silindiğinde arama olmadan herhangi bir kayıt yansıtacak `CRecordset::Requery`. Bu nedenle, dinamik kayıt kümeleri genellikle DBMS üzerinde işlem süresi açısından pahalıdır ve çoğu ODBC sürücüsü makineleri desteklememektedir. Buna karşılık, salt iletme kayıt kümeleri güncelleştirmeleri ya da geriye dönük kaydırma gerektirmeyen kayıt kümeleri için veri erişimini en verimli yöntemi sunar. Örneğin, yalnızca ileri yönde verilerinde gezinmek gerek duyduğunuz verileri bir veri kaynağından diğerine geçirmek için bir salt iletme kayıt kullanabilirsiniz. Salt iletme kayıt kümesi kullanmak için aşağıdakilerin ikisi de yapmanız gerekir:

- Seçeneğini geçirdiğiniz `CRecordset::forwardOnly` olarak *nOpenType* parametresinin [açık](../../mfc/reference/crecordset-class.md#open) üye işlevi.

- Belirtin `CRecordset::readOnly` içinde *dwOptions* parametresinin `Open`.

    > [!NOTE]
    >  Dynaset desteği için ODBC sürücü gereksinimleri hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md). Visual C++'ın bu sürümünde bulunan ODBC sürücülerinin listesini ve ek sürücüler hakkında bilgi için bkz: [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).

##  <a name="_core_your_recordsets"></a> Kümeleriniz

Her benzersiz tablo, görünüm veya erişmek istediğiniz saklı yordam için türetilen bir sınıf genellikle tanımlamak `CRecordset`. (Özel durum bir kayıt kümesi sütunları iki veya daha fazla tablodan temsil eden bir veritabanı birleşimidir.) Bir kayıt kümesi sınıf türetin, kayıt alanı değişimi (RFX) mekanizması veya toplu kayıt alanı değişimi (Bulk RFX) mekanizması benzeyen bir iletişim kutusu veri değişimi (DDX) mekanizması sağlar. RFX ve toplu RFX veri kaynağından veri aktarımını kümenizin basitleştirin; RFX veri kaynağına veri ek olarak, kayıt aktarır. Daha fazla bilgi için [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md) ve [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Kayıt kümesi nesnesi için seçilen tüm kayıtları erişmenizi sağlar. Kullanarak birden çok seçili kayıtlarda gezinin `CRecordset` gibi üye işlevleri `MoveNext` ve `MovePrev`. Aynı zamanda, bir kayıt kümesi nesnesi seçili kayıtları, geçerli kaydın yalnızca birini temsil eder. Kayıt kümesi sütunları tablodaki veya veritabanı sorgudan sonuçlanan kayıtlar karşılık gelen sınıf üyesi değişkenleri bildirerek geçerli kaydın alanlarını inceleyebilirsiniz. Kayıt kümesi veri üyeleri hakkında daha fazla bilgi için bkz. [kayıt kümesi: Mimari (ODBC)](../../data/odbc/recordset-architecture-odbc.md).

Aşağıdaki konularda, kayıt kümesi nesnelerini kullanarak ayrıntılarını açıklanır. Konular, sıralı okuma izni için doğal gözatma sırasında işlevsel kategoriler de listelenir.

### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>Açma, okuma ve kayıt kümelerini kapatma mekanizması ile ilgili konular

- [Kayıt kümesi: Mimari (ODBC)](../../data/odbc/recordset-architecture-odbc.md)

- [Kayıt Kümesi: Tablo için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

- [Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)

- [Kayıt Kümesi: Kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)

- [Kayıt Kümesi: Yer İşaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)

- [Kayıt Kümesi: Kayıtları Filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)

- [Kayıt Kümesi: Kayıtları Sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)

- [Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>Kayıt kümelerini değiştirme mekanizması ile ilgili konular

- [Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)

- [Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)

- [Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)

### <a name="topics-about-somewhat-more-advanced-techniques"></a>Konular hakkında biraz daha gelişmiş teknikler

- [Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)

- [Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

- [Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

- [Kayıt Kümesi: Kayıtları Toplu Yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

- [Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

- [Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

### <a name="topics-about-how-recordsets-work"></a>Nasıl çalıştığıyla ilgili konular

- [Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

- [Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[MFC ODBC tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)