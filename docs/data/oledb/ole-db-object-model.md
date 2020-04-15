---
title: OLE DB Nesne Modeli
ms.date: 10/22/2018
helpviewer_keywords:
- rowsets, OLE DB object model
- OLE DB, object model
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
ms.openlocfilehash: b37205eb91317c602010a4b568057845b2345ef0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369791"
---
# <a name="ole-db-object-model"></a>OLE DB Nesne Modeli

OLE DB nesne modeli aşağıdaki nesnelerden veya bileşenlerden oluşur. Listelenen ilk dört nesne veya bileşen (veri kaynakları, oturumlar, komutlar ve satır kümeleri) bir veri kaynağına bağlanmanızı ve görüntülemenize olanak sağlar. Geri kalanı, erişimcilerle başlayarak, görüntülendiğinde verilerle çalışmakla ilgilidir.

## <a name="data-sources"></a>Veri Kaynakları

Veri kaynağı nesneleri, dosya veya DBMS gibi bir veri kaynağına bağlanmanızı sağlar. Bir veri kaynağı nesnesi bağlantıyı oluşturur ve yönetir ve izinler ve kimlik doğrulama bilgileri (oturum açma adı ve parola gibi) içerir. Bir veri kaynağı nesnesi bir veya daha fazla oturum oluşturabilir.

## <a name="sessions"></a>Oturumlar

Oturum, verileri sorgulamak ve almak için veri kaynağıyla belirli bir etkileşimi yönetir. Her oturum tek bir işlemdir. Hareket, ACID testi tarafından tanımlanan bölünmez bir çalışma birimidir. ASİt tanımı için [Bkz. İşlemler](#vcconoledbcomponents_transactions).

Oturumlar satır kümelerini açma ve onu oluşturan veri kaynağı nesnesini döndürme gibi önemli görevleri yapar. Oturumlar ayrıca meta verileri veya veri kaynağının kendisi (tablo bilgileri gibi) hakkında bilgi döndürebilir.

Bir oturum bir veya daha fazla komut oluşturabilir.

## <a name="commands"></a>Komutlar

Komutlar, SQL deyimi gibi bir metin komutunu yürütür. Metin komutu, SQL **SELECT** deyimi gibi bir satır kümesi belirtirse, komut rowset'i oluşturur.

Komut, yalnızca, sağlayıcının temel veri deposu tarafından yürütülmesi için bir veri kaynağı nesnesine bir tüketiciden geçirilen bir dize (SQL deyimi gibi) olan metin komutu için bir kapsayıcıdır. Genellikle metin komutu bir SQL **SELECT** deyimidir (bu durumda, SQL **SELECT** bir satır kümesi belirttiğinden, komut otomatik olarak bir satır kümesi oluşturur).

## <a name="rowsets"></a>Satır küme -leri

Satır kümeleri verileri tabular biçiminde gösterir. Dizin, bir satır kümesinin özel bir örneğidir. Oturumveya komuttan satır kümeleri oluşturabilirsiniz.

### <a name="schema-rowsets"></a>Şema Satır Kümeleri

Şemalar bir veritabanı hakkında meta verilere (yapısal bilgilere) sahiptir. Şema satır kümeleri şema bilgisine sahip satır kümeleridir. DBMS için bazı OLE DB sağlayıcıları şema rowset nesnelerini destekler. Şema satır kümeleri hakkında daha fazla bilgi için bkz: [Schema Rowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) ve [Schema Rowset Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)ile Meta Veri Edinme.

### <a name="view-objects"></a>Nesneleri Görüntüle

Görünüm nesnesi, bir satır kümesinden satır ve sütunalt kümesini tanımlar. Kendine ait bir verisi yok. Nesneleri görüntüleyin, birden çok satır kümesinden gelen verileri birleştiremez.

## <a name="accessors"></a>Erişimcisi

Yalnızca OLE DB erişimciler kavramını kullanır. Bir erişimci, verilerin bir tüketicide nasıl depolanır açıklanır. Satır kümesi alanları (sütunlar) ve tüketicide beyan ettiğiniz veri üyeleri arasında bir bağlama kümesi (sütun eşlemi olarak adlandırılır).

## <a name="transactions"></a><a name="vcconoledbcomponents_transactions"></a>Hareket

Hareket nesneleri, iç içe geçen hareketleri en düşük düzeydışında işlerken veya iptal ederken kullanılır. Hareket, ACID testi tarafından tanımlanan bölünmez bir çalışma birimidir. ASİt şu şekildedir:

- Atomiklik, daha küçük iş birimlerine bölünemez

- Eşzamanlılık, aynı anda birden fazla işlem oluşabilir

- Yalıtım, bir işlem başka tarafından yapılan değişiklikler hakkında sınırlı bilgiye sahiptir

- Dayanıklılık, işlem kalıcı değişiklikler yapar

## <a name="enumerators"></a>Numaralandırıcılar

Tümumerators kullanılabilir veri kaynakları ve diğer sayısallaştırıcılar için arama. Belirli bir veri kaynağı için özelleştirilmemiş tüketiciler, kullanılacak bir veri kaynağını aramak için sayısallaştırıcılar kullanır.

Microsoft Veri Erişimi SDK'sında gönderilen bir kök madde numarası, veri kaynakları ve diğer sayısallaştırıcıları arayarak kayıt defterinde geçer. Diğer sayısallaştırıcılar, kayıt defterinde veya sağlayıcıya özgü bir şekilde arama da gezinir.

## <a name="errors"></a>Hatalar

Herhangi bir OLE DB nesnesindeki herhangi bir arabirim hata oluşturabilir. Hatalar, isteğe bağlı özel hata nesnesi de dahil olmak üzere bir hata hakkında ek bilgilere sahiptir. Bu bilgiler bir HRESULT'da depolanır.

## <a name="notifications"></a>Bildirimler

Bildirimler, bir sıra kümesini paylaşan işbirliği yapan tüketici grupları tarafından kullanılır (burada paylaşım, tüketicilerin aynı işlem içinde çalıştığı varsayılır). Bildirimler, bir satır kümesini paylaşan işbirliği içinde olan tüketicilerin, akranları tarafından gerçekleştirilen rowset'teki eylemler hakkında bilgilendirilmelerini sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)
