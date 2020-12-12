---
description: Daha fazla bilgi için bkz. kayıt kümesi (ODBC)
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
ms.openlocfilehash: edbad5851db6f5ac9e1fddcc769c4f860ee5478e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204543"
---
# <a name="recordset-odbc"></a>Kayıt Kümesi (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir [CRecordset](../../mfc/reference/crecordset-class.md) nesnesi, bir veri kaynağından seçilen bir kayıt kümesini temsil eder. Kayıtlar şu kaynaktan olabilir:

- Bir tablo.

- Bir sorgu.

- Bir veya daha fazla tabloya erişen saklı yordam.

Bir tabloyu temel alan bir kayıt kümesi örneği, bir müşteri tablosuna erişen "tüm müşteriler" dir. Bir sorgu örneği, "ali Smith için tüm faturalar" dır. Bir saklı yordama dayalı bir kayıt kümesi örneği (bazen önceden tanımlanmış sorgu olarak adlandırılır), arka uç veritabanında bir saklı yordam çağıran "tüm delinli hesaplar" dır. Bir kayıt kümesi aynı veri kaynağından iki veya daha fazla tabloyu birleştirebiliyor, ancak farklı veri kaynaklarından tablo içermemelidir.

> [!NOTE]
> Bazı ODBC sürücüleri veritabanının görünümlerini destekler. Bu anlamda bir görünüm, ilk olarak SQL ifadesiyle oluşturulmuş bir sorgudur `CREATE VIEW` .

## <a name="recordset-capabilities"></a><a name="_core_recordset_capabilities"></a> Kayıt kümesi özellikleri

Tüm kayıt kümesi nesneleri aşağıdaki özellikleri paylaşır:

- Veri kaynağı salt [okunurdur, kayıt](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)kümenizin [güncelleştirilebilir](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), uygulanabilir veya salt okunurdur olduğunu belirtebilirsiniz. Kayıt kümesi güncelleştirilebilirse, sürücünün uygun kilitleme desteğini sağladığı şekilde, kötümser veya iyimser [kilitleme](../../data/odbc/recordset-locking-records-odbc.md) yöntemlerini seçebilirsiniz. Veri kaynağı salt okunurdur, kayıt kümesi salt okunurdur.

- Seçilen kayıtlar arasında [gezinmek](../../data/odbc/recordset-scrolling-odbc.md) için üye işlevlerini çağırabilirsiniz.

- Kullanılabilir kayıtlardan hangi kayıtların seçili olduğunu kısıtlamak için kayıtlara [filtre](../../data/odbc/recordset-filtering-records-odbc.md) uygulayabilirsiniz.

- Kayıtları bir veya daha fazla sütuna göre artan veya azalan sırada [sıralayabilirsiniz](../../data/odbc/recordset-sorting-records-odbc.md) .

- Çalışma zamanında kayıt kümesi seçimini nitelemek için kayıt kümesini [parametreleştirebilirsiniz](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) .

## <a name="snapshots-and-dynasets"></a><a name="_core_snapshots_and_dynasets"></a> Anlık görüntüler ve dinamik kümeler

İki ana kayıt kümesi türü vardır: [anlık görüntüler](../../data/odbc/snapshot.md) ve [Dinamik kümeler](../../data/odbc/dynaset.md). Her ikisi de sınıfına göre desteklenir `CRecordset` . Her biri, tüm kayıt kümelerinin ortak özelliklerini paylaşır, ancak her ikisi de ortak işlevselliği kendi özel yöntemiyle genişletir. Anlık görüntüler verilerin statik bir görünümünü sağlar ve verilerin belirli bir zamanda bulunduğu şekilde görünümünü istediğiniz raporlar ve diğer durumlar için faydalıdır. Dinamik kümeler, kayıt kümesini yeniden sorgulamak veya yenilemek zorunda kalmadan, diğer kullanıcıların yaptığı güncelleştirmelerin kayıt kümesinde görünmesini istediğinizde yararlıdır. Anlık görüntüler ve dinamik kümeler güncelleştirilebilir veya salt okunurdur. Diğer kullanıcılar tarafından eklenen veya silinen kayıtları yansıtmak için [CRecordset:: Requery](../../mfc/reference/crecordset-class.md#requery)çağırın.

`CRecordset` Ayrıca, diğer iki tür kayıt kümesini sağlar: dinamik kayıt kümeleri ve salt iletme kayıt kümeleri. Dinamik kayıt kümeleri dinamik kümelerine benzerdir; Ancak, dinamik kayıt kümeleri çağrılmadan eklenen veya silinen kayıtları yansıtır `CRecordset::Requery` . Bu nedenle, dinamik kayıt kümeleri DBMS üzerindeki işleme süresine göre genellikle pahalıdır ve birçok ODBC sürücüsü bunları desteklemez. Buna karşılık, salt iletme kayıt kümeleri, güncelleştirme veya geriye doğru kaydırma gerektirmeyen kayıt kümeleri için en verimli veri erişimi yöntemini sağlar. Örneğin, verileri bir veri kaynağından diğerine geçirmek için yalnızca ileriye doğru bir kayıt kümesi kullanabilirsiniz. burada yalnızca bir ileri yönde veri üzerinde geçiş yapmanız gerekir. Yalnızca bir salt iletme kayıt kümesi kullanmak için aşağıdakilerden her ikisini de yapmanız gerekir:

- Seçeneği `CRecordset::forwardOnly` [Açık](../../mfc/reference/crecordset-class.md#open) üye Işlevin *nOpenType* parametresi olarak geçirin.

- `CRecordset::readOnly`' In *dwOptions* parametresinde belirtin `Open` .

    > [!NOTE]
    >  Dinamik küme desteği için ODBC sürücü gereksinimleri hakkında bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md). Bu Visual C++ sürümünde yer alan ODBC sürücülerinin bir listesi ve ek sürücü alma hakkında bilgi için bkz. [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).

## <a name="your-recordsets"></a><a name="_core_your_recordsets"></a> Kayıt kümeleriniz

Erişmek istediğiniz her farklı tablo, görünüm veya saklı yordam için, genellikle öğesinden türetilmiş bir sınıf tanımlarsınız `CRecordset` . (Özel durum, bir kayıt kümesinde iki veya daha fazla tablodan sütunları temsil eden bir veritabanı birleşmedir.) Bir kayıt kümesi sınıfı türettiğinizde, kayıt alanı değişimi (RFX) mekanizmasını veya iletişim kutusu veri değişimi (DDX) mekanizmasına benzer toplu kayıt alanı değişimi (toplu RFX) mekanizmasını etkinleştirin. RFX ve toplu RFX veri kaynağından kayıt kümenize veri aktarımını basitleştirir; RFX ek olarak, kayıt kümenize veri kaynağına veri aktarır. Daha fazla bilgi için bkz. [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md) ve [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Bir kayıt kümesi nesnesi tüm seçili kayıtlara erişmenizi sağlar. Ve gibi üye işlevlerini kullanarak seçilen birden çok kayıt üzerinde gezinolursunuz `CRecordset` `MoveNext` `MovePrev` . Aynı zamanda, bir kayıt kümesi nesnesi seçili kayıtlardan yalnızca birini temsil eder, geçerli kayıt. Kayıt kümesi sınıfı üye değişkenlerini, tablonun sütunlarına veya veritabanı sorgusunun sonucu olan kayıtlarla ilgili olarak bildirerek, geçerli kaydın alanlarını inceleyebilirsiniz. Kayıt kümesi veri üyeleri hakkında daha fazla bilgi için bkz. [kayıt kümesi: mimari (ODBC)](../../data/odbc/recordset-architecture-odbc.md).

Aşağıdaki konularda, kayıt kümesi nesnelerinin kullanımıyla ilgili ayrıntılar açıklanmaktadır. Konular, işlevsel kategorilerde ve sıralı okumaya izin vermek için doğal bir tarama sırasıyla listelenir.

### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>Kayıt kümelerini açma, okuma ve kapatma mekanizması hakkında konular

- [Kayıt kümesi: mimari (ODBC)](../../data/odbc/recordset-architecture-odbc.md)

- [Kayıt kümesi: tablo için sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

- [Kayıt kümesi: kayıt kümeleri oluşturma ve kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)

- [Kayıt kümesi: Kaydırma (ODBS)](../../data/odbc/recordset-scrolling-odbc.md)

- [Kayıt kümesi: yer Işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)

- [Kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)

- [Kayıt kümesi: kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)

- [Kayıt kümesi: bir kayıt kümesini Parametreleştirirken (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>Kayıt kümelerini değiştirme mekanizması hakkındaki konular

- [Kayıt kümesi: kayıtları ekleme, güncelleştirme ve silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)

- [Kayıt kümesi: kayıtları kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)

- [Kayıt kümesi: bir kayıt kümesini yeniden sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)

### <a name="topics-about-somewhat-more-advanced-techniques"></a>Biraz daha gelişmiş teknikler hakkında konular

- [Kayıt kümesi: JOIN gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)

- [Kayıt kümesi: önceden tanımlanmış sorgu için bir sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

- [Kayıt kümesi: veri sütunlarını dinamik olarak bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

- [Kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

- [Kayıt kümesi: büyük veri öğeleri ile çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

- [Kayıt kümesi: toplamları ve diğer toplama sonuçlarını alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

### <a name="topics-about-how-recordsets-work"></a>Kayıt kümelerinin nasıl çalıştığı hakkında konular

- [Kayıt kümesi: kayıt kümelerinin kayıtları seçme biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

- [Kayıt kümesi: kayıt kümelerinin kayıtları Güncelleştirmesi (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[MFC ODBC tüketme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)
