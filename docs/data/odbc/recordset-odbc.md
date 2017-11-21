---
title: "Kayıt kümesi (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 668cd4b2f27c2cde18528c0eb2d4d661160c4e4e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="recordset-odbc"></a>Kayıt Kümesi (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 A [CRecordset](../../mfc/reference/crecordset-class.md) nesnesi, bir veri kaynağından seçilen kayıt kümesini temsil eder. Kayıtları kaynaktan olabilir:  
  
-   Bir tablo.  
  
-   Bir sorgu.  
  
-   Bir veya daha fazla tablo erişen bir saklı yordam.  
  
 Bir tabloyu temel alan bir kayıt kümesi "tüm müşteriler,", müşteri tablosuna erişen örneğidir. Bir sorgu, "tüm faturaları Joe Smith için" örneğidir (Bazen önceden tanımlanmış sorgu denir) bir saklı yordamı kullanarak bir kayıt kümesi "tüm ödenmemiş hesapların" örneğidir bir saklı yordam arka uç veritabanı olarak çağırır. Bir kayıt kümesi, iki veya daha fazla aynı veri kaynağı tablolardan ancak farklı veri kaynakları tablolardan birleştirebilirsiniz.  
  
> [!NOTE]
>  Sihirbazlarla kayıt kümesi sınıflardan türetme hakkında daha fazla bilgi için bkz: [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md) ve [veritabanı desteği, MFC Uygulama Sihirbazı'nı](../../mfc/reference/database-support-mfc-application-wizard.md).  
  
> [!NOTE]
>  Bazı ODBC sürücüleri veritabanının görünümlerini destekler. Özgün SQL ile oluşturulan bir sorguyu görünümdür bu bağlamdaki `CREATE VIEW` deyimi. Sihirbazlar görünümleri şu anda desteklemez, ancak bu destek kendiniz kod mümkündür.  
  
##  <a name="_core_recordset_capabilities"></a>Kayıt kümesi özellikleri  
 Tüm kayıt kümesi nesneler aşağıdaki özellikleri içerir:  
  
-   Veri kaynağı salt okunur durumda değilse, kayıt olmasını belirtebilirsiniz [güncelleştirilebilir](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [eklenebilir](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), veya salt okunur. Kayıt kümesi güncelleştirilebilir ise, kötümser veya iyimser seçebilirsiniz [kilitleme](../../data/odbc/recordset-locking-records-odbc.md) yöntemleri, sağlanan sürücü uygun kilitleme desteği sağlar. Veri kaynağı salt okunur ise, kayıt kümesi salt okunur olacaktır.  
  
-   Üye işlevleri için çağırabilir [kaydırma](../../data/odbc/recordset-scrolling-odbc.md) seçilen kayıtlar arasında.  
  
-   Yapabilecekleriniz [filtre](../../data/odbc/recordset-filtering-records-odbc.md) kaydeden varolan kodlar arasından seçili sınırlamak için kaydeder.  
  
-   Yapabilecekleriniz [sıralama](../../data/odbc/recordset-sorting-records-odbc.md) kayıtları artan veya azalan dayalı bir veya daha fazla sütun.  
  
-   Yapabilecekleriniz [Parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) çalışma zamanında kayıt seçimi nitelemek için kayıt kümesi.  
  
##  <a name="_core_snapshots_and_dynasets"></a>Anlık görüntüler ve dinamik kümeler  
 Kayıt kümeleri asıl iki tür vardır: [anlık görüntüleri](../../data/odbc/snapshot.md) ve [dynaset'ler](../../data/odbc/dynaset.md). Sınıfı tarafından desteklenen `CRecordset`. Her tüm kayıt kümelerinin ortak özellikleri paylaşır, ancak her Ayrıca ortak işlevsellik kendi özelleştirilmiş şekilde genişletir. Anlık görüntü verileri statik bir görünümünü sağlar ve raporlar ve belirli bir zamandaki gibi verilerin görünümünü istediğiniz diğer durumlar için kullanışlıdır. Dinamik kümeler requery veya kayıt yenileme gerek kalmadan kayıt kümesinde görünür olması için diğer kullanıcılar tarafından yapılan güncelleştirmeler istediğinizde faydalıdır. Anlık görüntüler ve dinamik kümeler güncelleştirilebilir veya salt okunur olabilir. Eklenen kayıtları veya diğer kullanıcılar tarafından silinen çağıracak [CRecordset::Requery](../../mfc/reference/crecordset-class.md#requery).  
  
 `CRecordset`diğer iki tür kayıt kümeleri için de sağlar: dinamik kayıt kümeleri ve salt iletme kayıt kümeleri. Dinamik kayıt kümeleri kümelere benzer; Ancak, dinamik kayıt kümeleri eklenen veya arama olmadan silinen tüm kayıtları yansıtmak `CRecordset::Requery`. Bu nedenle, dinamik kayıt kümeleri genellikle DBMS üzerindeki işlem zamanına pahalıdır ve çoğu ODBC sürücüsü bunları desteklemiyor. Buna karşılık, salt iletme kayıt kümeleri güncelleştirmeleri veya geri kaydırma gerektirmeyen kayıt kümeleri için veri erişim en verimli yöntemi sağlar. Örneğin, burada yalnızca ileri yönde veri arasında gezinmek ihtiyacınız verileri bir veri kaynağından diğerine geçirmek için bir salt iletme kayıt kullanabilirsiniz. Salt iletme kayıt kümesi kullanmak için aşağıdakilerin her ikisi de yapmanız gerekir:  
  
-   Seçeneğini geçirdiğiniz **CRecordset::forwardOnly** olarak `nOpenType` parametresinin [açık](../../mfc/reference/crecordset-class.md#open) üye işlevi.  
  
-   Belirtin **CRecordset::readOnly** içinde `dwOptions` parametresinin **açık**.  
  
    > [!NOTE]
    >  Dynaset desteği için ODBC sürücü gereksinimleri hakkında daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md). Visual C++'ın bu sürümünde bulunan sürücülerin listesini ve ek sürücüler edinme hakkında bilgi için bkz: [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).  
  
##  <a name="_core_your_recordsets"></a>Kayıt kümeleri  
 Her ayrı tablo, görünüm veya erişmek istediğiniz saklı yordam için türetilmiş bir sınıf genellikle tanımlama `CRecordset`. (Özel durum bir kayıt kümesi sütunları iki veya daha fazla tablodan temsil eden bir veritabanı birleşimidir.) Bir kayıt kümesi sınıf türetin, kayıt alanı değişimi (RFX) mekanizması veya toplu kayıt alanı değişimi (Toplu RFX) mekanizması iletişim kutusu veri değişimi (DDX) mekanizmasına benzer olan sağlar. RFX ve toplu RFX veri kaynağından veri aktarımını kümenizin basitleştirmek; RFX veri kaynağına veri ek olarak, kayıt kümesinden aktarır. Daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md) ve [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Kayıt kümesi nesnesi için seçilen tüm kayıtları erişmenizi sağlar. Kullanarak birden fazla seçili kayıtlarda kaydırma `CRecordset` gibi üye işlevlerini `MoveNext` ve `MovePrev`. Aynı anda bir kayıt kümesi nesnesi seçili kayıtları, geçerli kayıt yalnızca birini temsil eder. Kayıt kümesi sütunları tablonun veya veritabanı sorgusundan sonuçlanan kayıtlar karşılık gelen sınıf üyesi değişkenleri bildirerek geçerli kaydın alanlarını inceleyebilirsiniz. Kayıt kümesi veri üyeleri hakkında daha fazla bilgi için bkz: [kayıt kümesi: Mimari (ODBC)](../../data/odbc/recordset-architecture-odbc.md).  
  
 Aşağıdaki konularda, kayıt kümesi nesnelerini kullanarak ayrıntılarını açıklanır. Konular, işlevsel kategoride ve sıralı okuma izni için doğal gözatma sırasında listelenir.  
  
### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>Açma, okuma ve kayıt kümeleri kapatma mekanizması hakkındaki konular  
  
-   [Kayıt kümesi: Mimari (ODBC)](../../data/odbc/recordset-architecture-odbc.md)  
  
-   [Kayıt kümesi: bir sınıf bir tablo için bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)  
  
-   [Kayıt kümesi: Oluşturma ve kapatma (ODBC) kayıt kümeleri](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)  
  
-   [Kayıt kümesi: Kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)  
  
-   [Kayıt kümesi: Yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)  
  
-   [Kayıt kümesi: Kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)  
  
-   [Kayıt kümesi: Kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)  
  
-   [Kayıt kümesi: kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>Kayıt kümelerini değiştirmenin mekanizması hakkındaki konular  
  
-   [Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)  
  
-   [Kayıt kümesi: Kayıtları kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)  
  
-   [Kayıt kümesi: kayıt kümesi (ODBC) yeniden sorgulama](../../data/odbc/recordset-requerying-a-recordset-odbc.md)  
  
### <a name="topics-about-somewhat-more-advanced-techniques"></a>Konular hakkında biraz daha gelişmiş teknikler  
  
-   [Kayıt kümesi: bir birleşim gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)  
  
-   [Kayıt kümesi: bir sınıf bir önceden tanımlanmış sorgu için bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)  
  
-   [Kayıt kümesi: Veri sütunlarını (ODBC) dinamik olarak bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)  
  
-   [Kayıt kümesi: Kayıtları toplu (ODBC) yakalama](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)  
  
-   [Kayıt kümesi: Büyük veri öğeleri ile çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)  
  
-   [Kayıt kümesi: SUM'ları ve diğer toplama sonuçlarını (ODBC) alma](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)  
  
### <a name="topics-about-how-recordsets-work"></a>Nasıl çalıştığıyla ilgili konular  
  
-   [Kayıt kümesi: Nasıl kümelerinin kayıtları seçme biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)  
  
-   [Kayıt kümesi: Kayıt kümeleri Güncelleştirmesi (ODBC) nasıl kaydeder.](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [MFC ODBC tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [İşlem (ODBC)](../../data/odbc/transaction-odbc.md)