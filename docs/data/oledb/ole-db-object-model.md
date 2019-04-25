---
title: OLE DB Nesne Modeli
ms.date: 10/22/2018
helpviewer_keywords:
- rowsets, OLE DB object model
- OLE DB, object model
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
ms.openlocfilehash: 303ad4166f0f1126182956fae9c19f513be7cfb3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283865"
---
# <a name="ole-db-object-model"></a>OLE DB Nesne Modeli

OLE DB Nesne modeli, aşağıdaki nesneler veya bileşenleri yapılır. İlk dört nesneleri veya listelenen bileşenleri (veri kaynakları, oturumlar, komutları ve satır kümeleri), bir veri kaynağına bağlanmak ve onu görüntülemenizi sağlar. Erişimcileri ile başlayarak, rest görüntülendiğinde verilerle çalışmaya ilgilidir.

## <a name="data-sources"></a>Data Sources

Veri kaynağı nesneleri bir dosya veya DBMS gibi bir veri kaynağına bağlanmanıza olanak sağlar. Bir veri kaynağı nesnesi oluşturur ve bağlantı yönetir ve izinleri ve kimlik doğrulama bilgilerini (örneğin, oturum açma adı ve parola) içerir. Bir veri kaynağı nesnesinin bir veya daha fazla oturumları oluşturabilirsiniz.

## <a name="sessions"></a>Oturumlar

Oturum, sorgu ve veri alımı veri kaynağındaki belirli bir etkileşim yönetir. Her oturum, tek bir işlem değil. Bir işlem, ACID testi tarafından tanımlanan bir bölünemez iş birimidir. ACID tanımı için bkz [işlemleri](#vcconoledbcomponents_transactions).

Oturumlarının satır kümeleri açmak ve onu oluşturan veri kaynağı nesnesi döndüren gibi önemli görevler yapın. Oturumlarının ayrıca meta veriler ya da veri kaynağının (örneğin, tablo bilgileri) hakkında bilgi döndürebilir.

Bir oturumu bir veya daha fazla komut oluşturabilirsiniz.

## <a name="commands"></a>Komutlar

Bir SQL deyimi gibi bir metin komut komutları yürütün. Metin komutu bir SQL gibi bir satır kümesi belirtirse **seçin** deyimi, komut satır kümesi oluşturur.

Yalnızca bir tüketici için bir veri kaynağı nesnesi yürütme için sağlayıcıya ait temel veri deposu tarafından geçirilen bir dize (örneğin, bir SQL deyimi) olan bir metin komutu için kapsayıcı bir komuttur. Genellikle, bir SQL metin komutu, **seçin** deyimi (Bu durumda, çünkü SQL **seçin** bir satır kümesi belirtir komut otomatik olarak bir satır kümesi oluşturur).

## <a name="rowsets"></a>Satır kümeleri

Satır kümeleri verileri tablo biçiminde gösterin. Dizin, bir satır kümesi özel bir durumdur. Oturum ya da komut satır kümeleri oluşturabilirsiniz.

### <a name="schema-rowsets"></a>Şema Satır Kümeleri

Şemaların veritabanı hakkındaki meta verileri (yapısal bilgileri) vardır. Şema satır kümeleri şema bilgileri olan bir satır var. Bazı OLE DB sağlayıcıları için DBMS şeması satır kümesi nesneleri destekler. Şema satır kümeleri hakkında daha fazla bilgi için bkz: [kümelerinin şema satır kümeleri ile](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) ve [şeması satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).

### <a name="view-objects"></a>Nesneleri görüntüle

Bir görünüm nesnesi bir satır kümesi sütun ve satır kümesini tanımlar. Bu, kendi veri yok. Görünüm nesneleri birden çok satır kümeleri verilerden birleştiremezsiniz.

## <a name="accessors"></a>Erişimciler

Sadece OLE DB erişimcileri kavramını kullanır. Erişimci, tüketicide verilerin depolanma şeklini tanımlar. Satır kümesi alan (sütun) ve tüketici olarak bildirdiğiniz veri üyeleri arasında (sütun eşlemesi olarak bilinir) bağlamaları kümesi vardır.

##  <a name="vcconoledbcomponents_transactions"></a> İşlemler

İşlem nesneleri Sistemi'ne veya iptal ediliyor en alt düzeyin iç içe işlemler kullanılır. Bir işlem, ACID testi tarafından tanımlanan bir bölünemez iş birimidir. ACID anlamına gelir:

- Kararlılık, küçük çalışma birimlerine bölünmüş olamaz

- Eşzamanlılık, aynı anda birden fazla işlem oluşabilir

- Yalıtım, bir işlem bir başkası tarafından yapılan değişiklikler hakkında bilgi sınırlıdır.

- Dayanıklılık, işlem kalıcı değişiklikler yapar.

## <a name="enumerators"></a>Numaralandırıcılar

Numaralandırıcılar, kullanılabilir veri kaynaklarını ve diğer numaralandırıcıları arayın. Belirli veri kaynağı için özelleştirilmiş olmayan tüketiciler numaralandırıcılar kullanmak bir veri kaynağını aramak için kullanın.

Microsoft Data Access SDK kök numaralandırıcısı, veri kaynakları ve başka numaralandırıcılar için kayıt defteri erişir. Başka numaralandırıcılar kayıt defteri veya arama sağlayıcıya özgü bir şekilde çapraz geçiş yapma.

## <a name="errors"></a>Hatalar

Herhangi bir OLE DB Nesne herhangi bir arabirimde hatalara neden olabilir. İsteğe bağlı bir özel hata nesneyi dahil olmak üzere, bir hata hakkında ek bilgi hatalarla karşılaştınız. Bu bilgiler, HRESULT depolanır.

## <a name="notifications"></a>Bildirimler

Bildirimleri (burada paylaşımı tüketicilerin aynı işlem içinde çalışmıyor olabilir varsayılır anlamına gelir), satır kümesi paylaşan kurduğuna ilişkin tüketici grupları tarafından kullanılır. Satır kümesi kendi eşleri tarafından gerçekleştirilen eylemler hakkında bilgilendirilmesi kurduğuna ilişkin tüketicileri bir satır kümesi paylaşan bildirimlerini etkinleştirin.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)