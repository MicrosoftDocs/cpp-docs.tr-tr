---
title: Giriş-Çıkış İşleme için Öneriler
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
ms.openlocfilehash: c365120a385c440f09f0ee4c0a2fc52afb55834f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371732"
---
# <a name="recommendations-for-handling-inputoutput"></a>Giriş/Çıkış İşleme için Öneriler

Dosya tabanlı G/Ç kullanıp kullanmadığınız, aşağıdaki karar ağacındaki sorulara nasıl yanıt verilebildiğinize bağlıdır:

**Uygulamanızdaki birincil veriler bir disk dosyasında mı bulunur?**

- Evet, birincil veriler bir disk dosyasında bulunur:

   **Uygulama Dosya Aç'ta tüm dosyayı belleğe okur ve dosyanın tamamını Dosya Kaydet'te diske geri yazar mı?**

  - Evet: Bu varsayılan MFC belge örneğidir. Serileştirme kullanın. `CDocument`

  - Hayır: Bu genellikle dosyanın işlem tabanlı güncelleştirme durumudur. Dosyayı işlem başına olarak güncelleştirin ve `CDocument` serileştirme gerekmez.

- Hayır, birincil veriler bir disk dosyasında bulunmaz:

   **Veriler Bir ODBC veri kaynağında mı?**

  - Evet, veriler bir ODBC veri kaynağında bulunur:

      MFC'nin veritabanı desteğini kullanın. Bu servis talebi için standart `CDatabase` MFC uygulaması, [MFC: Belgeler ve Görünümlerle Veritabanı Sınıfları kullanma](../data/mfc-using-database-classes-with-documents-and-views.md)makalesinde belirtildiği gibi bir nesne içerir. Uygulama ayrıca yardımcı bir dosyayı okuyup yazabilir — uygulama sihirbazının amacı "hem veritabanı görünümü hem de dosya desteği" seçeneği. Bu durumda, yardımcı dosya için serileştirme kullanırsınız.

  - Hayır, veriler ODBC veri kaynağında yok.

      Bu duruma örnekler: veriler ODBC DBMS olmayan bir yerde bulunur; veriler OLE veya DDE gibi başka bir mekanizma aracılığıyla okunur.

      Bu gibi durumlarda serileştirme kullanmazsınız ve uygulamanızda Aç ve Kaydet menü öğeleri olmaz. MFC ODBC `CDocument` uygulamasının nesneleri depolamak `CRecordset` için belgeyi kullandığı gibi, bir ana taban olarak da kullanmak isteyebilirsiniz. Ancak çerçevenin varsayılan Dosya Aç/Kaydet belge serileştirmesini kullanmazsınız.

Dosya menüsündeki Aç, Kaydet ve Kaydet komutlarını desteklemek için çerçeve belge serileştirmesağlar. Serileştirme, normalde bir disk dosyası olan `CObject`sınıftan kalıcı depolamaya türetilen nesneler de dahil olmak üzere verileri okur ve yazar. Serileştirme kullanımı kolaydır ve birçok gereksinimlerinize hizmet eder, ancak birçok veri erişim uygulamasında uygunsuz olabilir. Veri erişim uygulamaları genellikle verileri işlem başına olarak güncelleştirin. Tüm veri dosyasını aynı anda okuyup yazmak yerine işlemden etkilenen kayıtları güncellerler.

Serileştirme hakkında bilgi için [serileştirme'ye](../mfc/serialization-in-mfc.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Seri Hale Getirme: Seri Hale Getirme ve Veritabanı Giriş/Çıkışı](../mfc/serialization-serialization-vs-database-input-output.md)
