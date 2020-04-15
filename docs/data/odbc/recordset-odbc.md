---
title: Kayıt Kümesi (ODBC)
ms.date: 05/09/2019
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
ms.openlocfilehash: b7a55621f4875b24cc33a0fd49a5b8b4c88b34cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368643"
---
# <a name="recordset-odbc"></a>Kayıt Kümesi (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

[CRecordset nesnesi,](../../mfc/reference/crecordset-class.md) veri kaynağından seçilen bir kayıt kümesini temsil eder. Kayıtlar aşağıdakilerden olabilir:

- Bir masa.

- Bir sorgu.

- Bir veya daha fazla tabloya erişen depolanmış yordam.

Tabloya dayalı kayıt kümesine örnek olarak, Müşteri tablosuna erişen "tüm müşteriler" gelir. Bir sorgu örneği "Joe Smith için tüm faturalar." Kaydedilmiş yordamı temel alan bir kayıt kümesi örneği (bazen önceden tanımlanmış sorgu olarak da adlandırılır), arka uç veritabanında depolanan yordamı çağıran "tüm hatalı hesaplar"dır. Kayıt kümesi aynı veri kaynağından iki veya daha fazla tabloyu biraraya getirebilir, ancak farklı veri kaynaklarından gelen tabloları birleştiremez.

> [!NOTE]
> Bazı ODBC sürücüleri veritabanının görünümlerini destekler. Bu anlamda bir görünüm, başlangıçta SQL `CREATE VIEW` deyimi ile oluşturulan bir sorgudur.

## <a name="recordset-capabilities"></a><a name="_core_recordset_capabilities"></a>Recordset Yetenekleri

Tüm kayıt kümesi nesneleri aşağıdaki yetenekleri paylaşır:

- Veri kaynağı salt okunur değilse, kayıt ayarınızın [güncellenebilir](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [eklenebilir](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)veya salt okunur olduğunu belirtebilirsiniz. Kayıt kümesi güncelleştirilebilirse, sürücünün uygun kilitleme desteğini sağlaması koşuluyla kötümser veya iyimser [kilitleme](../../data/odbc/recordset-locking-records-odbc.md) yöntemlerini seçebilirsiniz. Veri kaynağı salt okunursa, kayıt kümesi salt okunur.

- Seçili kayıtlar arasında [gezinmek](../../data/odbc/recordset-scrolling-odbc.md) için üye işlevleri arayabilirsiniz.

- Kullanılabilir kayıtlardan hangi kayıtların seçildiğini kısıtlamak için kayıtları [filtreleyebilirsiniz.](../../data/odbc/recordset-filtering-records-odbc.md)

- Kayıtları [sort](../../data/odbc/recordset-sorting-records-odbc.md) artan veya azalan sırada, bir veya daha fazla sütuna göre sıralayabilirsiniz.

- Kayıt kümesi seçimini çalışma zamanında hak kazanmak için kayıt kümesini [parametrenize alabilirsiniz.](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

## <a name="snapshots-and-dynasets"></a><a name="_core_snapshots_and_dynasets"></a>Anlık Görüntüler ve Dynasets

İki temel kayıt türü vardır: [anlık görüntüler](../../data/odbc/snapshot.md) ve [dinamitler.](../../data/odbc/dynaset.md) Her ikisi de `CRecordset`sınıf tarafından desteklenir. Her biri tüm kayıt kümelerinin ortak özelliklerini paylaşır, ancak her biri ortak işlevselliği kendi özel bir şekilde genişletir. Anlık görüntüler verilerin statik bir görünümünü sağlar ve raporlar ve belirli bir zamanda var olan verilerin görünümünü istediğiniz diğer durumlar için yararlıdır. Dynasets, diğer kullanıcılar tarafından yapılan güncelleştirmelerin kayıt kümesini yeniden sorgulamak veya yenilemek zorunda kalmadan kayıt kümesinde görünür olmasını istediğinizde yararlıdır. Anlık görüntüler ve dynaset'ler güncelleştirilebilir veya salt okunabilir. Diğer kullanıcılar tarafından eklenen veya silinen kayıtları yansıtmak için [CRecordset::Requery'yi](../../mfc/reference/crecordset-class.md#requery)arayın.

`CRecordset`ayrıca diğer iki kayıt seti türüne de izin verir: dinamik kayıt kümeleri ve yalnızca ileriye yönelik kayıt kümeleri. Dinamik kayıt setleri dinamitlere benzer; ancak, dinamik kayıt kümeleri, aramadan `CRecordset::Requery`eklenen veya silinen tüm kayıtları yansıtır. Bu nedenle, dinamik kayıt kümeleri DBMS'deki işleme süresine göre genellikle pahalıdır ve birçok ODBC sürücüsü bunları desteklemez. Buna karşılık, yalnızca ileri kayıt kümeleri, güncelleştirme veya geriye kaydırma gerektirmeyen kayıt kümeleri için en verimli veri erişim yöntemini sağlar. Örneğin, verileri bir veri kaynağından diğerine geçirmek için yalnızca ileri kayıt kümesi kullanabilirsiniz ve burada verileri yalnızca ileri yönde taşımanız gerekir. Yalnızca ileri kayıt kümesini kullanmak için aşağıdakilerden her ikisini de yapmanız gerekir:

- `CRecordset::forwardOnly` [Seçeneği Open](../../mfc/reference/crecordset-class.md#open) üye işlevinin *nOpenType* parametresi olarak geçirin.

- *DwOptions* parametresinde belirtin. `Open` `CRecordset::readOnly`

    > [!NOTE]
    >  Dynaset desteği için ODBC sürücü gereksinimleri hakkında daha fazla bilgi için [ODBC'ye](../../data/odbc/odbc-basics.md)bakın. Visual C++ bu sürümünde yer alan ODBC sürücülerinin listesi ve ek sürücü edinme hakkında bilgi için [Bkz. ODBC Sürücü Listesi.](../../data/odbc/odbc-driver-list.md)

## <a name="your-recordsets"></a><a name="_core_your_recordsets"></a>Kayıt Kümeleriniz

Erişmek istediğiniz her farklı tablo, görünüm veya depolanan yordam için genellikle türetilen bir sınıf `CRecordset`tanımlarsınız. (Özel durum, bir kayıt kümesinin iki veya daha fazla tablodaki sütunları temsil ettiği bir veritabanı birleştirmedir.) Bir kayıt kümesi sınıfı türettiğinizde, iletişim veri alışverişi (DDX) mekanizmasına benzer kayıt alanı değişimi (RFX) mekanizmasını veya toplu kayıt alanı değişimi (Toplu RFX) mekanizmasını etkinleştirin. RFX ve Toplu RFX, veri kaynağından kayıt setinize veri aktarımını basitleştirir; RFX ayrıca verileri kayıt setinizden veri kaynağına aktarmaktadır. Daha fazla bilgi için bkz: [Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md) ve [Recordset: Kayıtları Toplu Olarak Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Kayıt kümesi nesnesi, seçili tüm kayıtlara erişmenizi sağlar. Üye işlevleri kullanarak `CRecordset` birden çok seçili `MoveNext` kayıt `MovePrev`arasında gezinirsiniz. Aynı zamanda, bir kayıt kümesi nesnesi seçili kayıtlardan yalnızca birini, geçerli kaydı temsil eder. Tablonun sütunlarına veya veritabanı sorgusundan kaynaklanan kayıtların sütunlarına karşılık gelen kayıt kümesi sınıf üye değişkenlerini beyan ederek geçerli kaydın alanlarını inceleyebilirsiniz. Kayıt kümesi veri üyeleri hakkında bilgi için bkz: [Recordset: Architecture (ODBC)](../../data/odbc/recordset-architecture-odbc.md).

Aşağıdaki konular kayıt kümesi nesnelerini kullanmanın ayrıntılarını açıklar. Konular fonksiyonel kategorilerde listelenir ve sıralı okumaya izin vermek için doğal bir gözatma sırası.

### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>Kayıt kümelerini açma, okuma ve kapatma mekaniği ile ilgili konular

- [Kayıt kümesi: Mimari (ODBC)](../../data/odbc/recordset-architecture-odbc.md)

- [Kayıt Kümesi: Tablo için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

- [Kayıt Kümesi: Kayıt Kümeleri Oluşturma ve Kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)

- [Kayıt Kümesi: Kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)

- [Kayıt Kümesi: Yer İşaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)

- [Kayıt Kümesi: Kayıtları Filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)

- [Kayıt Kümesi: Kayıtları Sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)

- [Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>Kayıt kümelerini değiştirme mekaniği ile ilgili konular

- [Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)

- [Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)

- [Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)

### <a name="topics-about-somewhat-more-advanced-techniques"></a>Biraz daha gelişmiş teknikler hakkında konular

- [Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)

- [Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

- [Kayıt Kümesi: Veri Sütunlarını Dinamik Olarak Bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

- [Kayıt Kümesi: Kayıtları Toplu Yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

- [Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

- [Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

### <a name="topics-about-how-recordsets-work"></a>Kayıt kümelerinin nasıl çalıştığıyla ilgili konular

- [Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

- [Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[MFC ODBC Tüketimi](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)
