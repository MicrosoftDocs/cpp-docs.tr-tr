---
title: OLE DB Nesne modeli | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, OLE DB object model
- OLE DB, object model
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ba9fd9b7ba5503f6ed5e1837147524f5abc7c31b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-object-model"></a>OLE DB Nesne Modeli
OLE DB Nesne modeli aşağıdaki nesnelerden veya bileşenlerden oluşur. İlk dört nesne veya listelenen bileşenleri (veri kaynakları, oturumlar, komutları ve satır kümeleri) bir veri kaynağına bağlanmak ve onu görüntülemenizi sağlar. Erişimciler ile başlayarak, kalan ilişkilendirmek görüntülendiğinde verilerle çalışmak için.  
  
## <a name="data-sources"></a>Data Sources  
 Veri kaynağı nesneleri, bir dosya veya DBMS gibi bir veri kaynağına bağlanmak izin verin. Bir veri kaynağı nesnesi oluşturur ve bağlantısını yönetir ve izinleri ve kimlik doğrulama bilgilerini (örneğin, oturum açma adı ve parola) içeriyor. Bir veri kaynağı nesnesi bir veya daha fazla oturumları oluşturabilirsiniz.  
  
## <a name="sessions"></a>Oturumlar  
 Bir oturum sorgu ve veri almak için veri kaynağı ile belirli bir etkileşim yönetir. Her oturum tek bir işlem değil. Bir işlem ACID testi tarafından tanımlanan bir bölünemez iş birimidir. ACID tanımı için bkz: [işlemleri](#vcconoledbcomponents_transactions).  
  
 Oturumlar satır kümeleri açmak ve onu oluşturan veri kaynağı nesnesi döndüren gibi önemli görevleri gerçekleştirin. Oturumlar, meta veriler veya veri kaynağı kendisini (örneğin, tablo bilgileri) hakkında bilgi de geri dönebilirsiniz.  
  
 Bir oturumu bir veya daha fazla komut oluşturabilirsiniz.  
  
## <a name="commands"></a>Komutlar  
 Komutlar bir SQL deyimi gibi bir metin komutunu yürütün. Metin komutu bir SQL gibi bir satır kümesi belirtirse **seçin** deyimi, komut, satır kümesi oluşturur.  
  
 Bir komutu yalnızca bir tüketici'den bir veri kaynağı nesnesi için yürütme sağlayıcının temel veri deposu tarafından geçirilen bir dize (örneğin, bir SQL deyimi) bir metin komutu için kapsayıcıdır. Genellikle, metin bir SQL komuttur **seçin** deyimi (olduğundan, bu durumda SQL **seçin** bir satır kümesi belirtir komutu otomatik olarak bir satır kümesi oluşturur).  
  
## <a name="rowsets"></a>Satır kümeleri  
 Satır kümeleri verileri tablo biçiminde kullanıma sunar. Bir dizin, bir satır kümesi özel bir durumdur. Satır kümeleri oturum ya da komutu oluşturabilirsiniz.  
  
### <a name="schema-rowsets"></a>Şema Satır Kümeleri  
 Şemalar veritabanıyla ilgili meta veriler (yapısal bilgiler) içerir. Şema satır kümeleri şema bilgileri içeren satır kümeleri ' dir. Bazı OLE DB sağlayıcıları DBMS için şema satır kümesi nesneleri destekler. Şema satır kümeleri hakkında daha fazla bilgi için bkz: [şema satır kümeleri ile meta veri alma](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) ve [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
### <a name="view-objects"></a>Görünüm nesneleri  
 Bir görünüm nesnesi satırları ve satır sütunlarından bir alt kümesini tanımlar. Kendi veri içermiyor. Görünüm nesneleri birden çok satır kümeleri verilerden birleştiremez.  
  
## <a name="accessors"></a>Erişimciler  
 Sadece OLE DB erişimciler kavramını kullanır. Erişimci tüketicide verilerin depolanma şeklini açıklar. Satır kümesi alanları (sütunları) tüketicideki bildirme veri üyeleri arasında (bir sütun eşlemesi olarak adlandırılır) bağlamaları kümesi içerir.  
  
##  <a name="vcconoledbcomponents_transactions"></a> İşlemler  
 İşlem nesneleri tamamlama ya da iç içe geçmiş işlemler en alt düzeyin durduruluyor olduğunda kullanılır. Bir işlem ACID testi tarafından tanımlanan bir bölünemez iş birimidir. ACID anlamına gelir:  
  
-   Kararlılık: küçük çalışma birimlerine bölünemez.  
  
-   Eşzamanlılık: aynı anda birden fazla işlem oluşabilir.  
  
-   Yalıtım: bir işlem başka tarafından yapılan değişiklikler hakkında bilgi sınırlıdır.  
  
-   Dayanıklılık: işlem kalıcı değişiklikler yapar.  
  
## <a name="enumerators"></a>Numaralandırmalar  
 Numaralandırıcılar kullanılabilir veri kaynaklarını ve diğer numaralandırıcıları arayın. Belirli bir veri kaynağı için özelleştirilmiş değil tüketicileri numaralandırıcılar kullanmak için bir veri kaynağı için aramak için kullanın.  
  
 Microsoft Data Access SDK kök numaralandırıcısı, veri kaynaklarını ve diğer numaralandırıcıları arayan kayıt defteri erişir. Başka numaralandırıcılar, bir sağlayıcıya özgü şekilde kayıt defteri veya arama geçiş.  
  
## <a name="errors"></a>Hatalar  
 Herhangi bir OLE DB Nesne üzerinde herhangi bir arabirimi hatalara neden olabilir. Hata, bir isteğe bağlı özel hata nesnesi de dahil olmak üzere hatayla ilgili ek bilgileri içerir. Bu bilgiler bir HRESULT bulunur.  
  
## <a name="notifications"></a>Bildirimler  
 Bildirimler, (burada paylaşımı tüketicilerin aynı işlem içinde çalışmıyor olabilir varsayılır anlamına gelir) satır kümesi paylaşan birlikte çalışan tüketici grupları tarafından kullanılır. Bildirimleri satır kümesi kendi eşleri tarafından gerçekleştirilen eylemler hakkında bilgi sahibi olmak birlikte çalışan tüketiciler satır paylaşımını etkinleştirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB programlama](../../data/oledb/ole-db-programming.md)   
 [OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)