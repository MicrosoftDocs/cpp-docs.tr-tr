---
description: 'Hakkında daha fazla bilgi edinin: OLE DB nesne modeli'
title: OLE DB Nesne Modeli
ms.date: 10/22/2018
helpviewer_keywords:
- rowsets, OLE DB object model
- OLE DB, object model
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
ms.openlocfilehash: 8286c62e890d891f015a0d54ac761b4de6e58d85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286975"
---
# <a name="ole-db-object-model"></a>OLE DB Nesne Modeli

OLE DB nesne modeli aşağıdaki nesneler veya bileşenlerden oluşur. Listelenen ilk dört nesne veya bileşen (veri kaynakları, oturumlar, komutlar ve satır kümeleri) bir veri kaynağına bağlanmanızı ve onu görüntülemenizi sağlar. Erişimcilerde başlayan Rest, görüntülendiği sırada verilerle çalışmaya ilgilidir.

## <a name="data-sources"></a>Data Sources

Veri kaynağı nesneleri, dosya veya DBMS gibi bir veri kaynağına bağlanmanıza olanak tanır. Veri kaynağı nesnesi, bağlantıyı oluşturur ve yönetir ve izinleri ve kimlik doğrulamaları bilgilerini (oturum açma adı ve parola gibi) içerir. Bir veri kaynağı nesnesi bir veya daha fazla oturum oluşturabilir.

## <a name="sessions"></a>Oturumlar

Oturum, verileri sorgulamak ve almak için veri kaynağıyla belirli bir etkileşimi yönetir. Her oturum tek bir işlemdir. İşlem, ACID testi tarafından tanımlanan, görünmeyen bir iş birimidir. ACID tanımı için bkz. [işlemler](#vcconoledbcomponents_transactions).

Oturumlar, satır kümelerini açma ve onu oluşturan veri kaynağı nesnesini döndürme gibi önemli görevleri işler. Oturumlar Ayrıca meta verileri veya veri kaynağının kendisi hakkındaki bilgileri (tablo bilgileri gibi) döndürebilir.

Bir oturum, bir veya daha fazla komut oluşturabilir.

## <a name="commands"></a>Komutlar

Komutları SQL deyimleri gibi bir metin komutu yürütür. Metin komutu SQL **Select** deyimleri gibi bir satır kümesi belirtiyorsa, komut satır kümesini oluşturur.

Bir komut, bir tüketici tarafından sağlayıcının temel alınan veri deposu tarafından yürütülmek üzere bir veri kaynağı nesnesine geçirilen bir dize (örneğin, SQL deyimleri) olan bir metin komutuna yönelik bir kapsayıcıdır. Genellikle, metin komutu bir SQL **Select** deyimidir (Bu durumda, SQL **Select** bir satır kümesi belirttiğinden, komut otomatik olarak bir satır kümesi oluşturur).

## <a name="rowsets"></a>Kümelerinde

Satır kümeleri verileri tablolu biçimde gösterir. Dizin, bir satır kümesinin özel bir durumdur. Oturumdan veya komuttan satır kümesi oluşturabilirsiniz.

### <a name="schema-rowsets"></a>Şema Satır Kümeleri

Şemaların bir veritabanıyla ilgili meta veriler (yapısal bilgiler) vardır. Şema satır kümeleri, şema bilgilerine sahip satır kümeleridir. DBMS için bazı OLE DB sağlayıcıları şema satır kümesi nesnelerini destekler. Şema satır kümeleri hakkında daha fazla bilgi için bkz. [şema satır kümeleri Ile meta veri alma](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) ve [şema satır kümesi sınıfları ve typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).

### <a name="view-objects"></a>Nesneleri görüntüle

Bir görünüm nesnesi bir satır kümesinden satır ve sütunların bir alt kümesini tanımlar. Kendi verileri yoktur. Görünüm nesneleri birden çok satır kümesinden verileri birleştiremez.

## <a name="accessors"></a>C

Yalnızca OLE DB erişimcileri kavramını kullanır. Bir erişimci, verilerin bir tüketiciye nasıl depolandığını açıklar. Satır kümesi alanları (sütunlar) ve tüketicide bildirdiğiniz veri üyeleri arasında bir bağlama kümesi (sütun Haritası denir) vardır.

## <a name="transactions"></a><a name="vcconoledbcomponents_transactions"></a> Hareket

İşlem nesneleri, en düşük düzeyden farklı olarak iç içe geçmiş işlemleri yaparken veya iptal edildiğinde kullanılır. İşlem, ACID testi tarafından tanımlanan, görünmeyen bir iş birimidir. ACID şunu temsil eder:

- Atomicity, daha küçük iş birimlerine bölünemeyeceğini

- Eşzamanlılık, bir seferde birden çok işlem oluşabilir

- Yalıtım, bir işlemin başka bir değişiklik yaptığı değişikliklerle ilgili sınırlı bilgisi vardır

- Dayanıklılık, işlem kalıcı değişiklikler yapar

## <a name="enumerators"></a>Numaralandırıcılar

Numaralandırıcılar, kullanılabilir veri kaynakları ve diğer Numaralandırıcılar için arama yapın. Belirli bir veri kaynağı için özelleştirilmeyen tüketiciler, kullanmak üzere bir veri kaynağı aramak için Numaralandırıcılar kullanır.

Microsoft veri erişim SDK 'sında sunulan bir kök Numaralandırıcı, veri kaynaklarını ve diğer numaralandırıcıları bulmak için kayıt defteri 'ne erişir. Diğer numaralandırıcılar kayıt defterinde çapraz geçiş yapar veya sağlayıcıya özgü bir şekilde arama yapar.

## <a name="errors"></a>Hatalar

Herhangi bir OLE DB nesnesi üzerinde herhangi bir arabirim hata oluşturabilir. Hatalar, isteğe bağlı özel bir hata nesnesi de dahil olmak üzere bir hata hakkında ek bilgilere sahiptir. Bu bilgiler bir HRESULT içinde depolanır.

## <a name="notifications"></a>Bildirimler

Bildirimler, bir satır kümesini paylaşan birlikte çalışan tüketici grupları tarafından kullanılır (paylaşım, tüketicilerin aynı işlem içinde çalıştığı varsayılır). Bildirimler, bir satır kümesini paylaşan ortak işletim tüketicilerinin, eşleri tarafından gerçekleştirilen satır kümesindeki eylemler hakkında bilgi sahibi olmasını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)
