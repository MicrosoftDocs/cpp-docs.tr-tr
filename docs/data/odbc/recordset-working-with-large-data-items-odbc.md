---
title: 'Kayıt kümesi: Büyük veri öğeleri ile çalışma (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6845d2e3c1b1eac31486200a0f610037d4774626
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)
Bu konu, MFC ODBC sınıfları ve MFC DAO sınıfları için geçerlidir.  
  
> [!NOTE]
>  MFC DAO sınıflarını kullanıyorsanız, büyük veri öğeleri sınıfı ile yönetme [CLongBinary](../../mfc/reference/cbytearray-class.md) sınıfı yerine [CLongBinary](../../mfc/reference/clongbinary-class.md). MFC ODBC sınıfları toplu satır getirme ile kullanıyorsanız `CLongBinary` yerine `CByteArray`. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Veritabanı büyük veri parçaları, bit eşlemler (çalışan fotoğrafları, haritalar, resimleri, ürünler, OLE nesneleri ve benzeri) gibi depolayabilir varsayalım. Bu tür verilerin genellikle bir ikili büyük nesne (veya BLOB) çünkü adlandırılır:  
  
-   Her bir alan değeri büyük.  
  
-   Sayılar ve diğer basit veri türlerinin aksine, tahmin edilebilir bir boyutu vardır.  
  
-   Programınızı perspektifinden formless veridir.  
  
 Bu konuda bu tür nesneler ile çalışmak için veritabanı sınıfları sağlamak hangi destek açıklanır.  
  
##  <a name="_core_managing_large_objects"></a> Büyük nesneleri yönetme  
 Kayıt kümeleri ikili büyük nesneler yönetme özel zorluğunu çözmek için iki yolu vardır. Sınıf kullanabilirsiniz [CLongBinary](../../mfc/reference/cbytearray-class.md) veya sınıf kullanabilirsiniz [CLongBinary](../../mfc/reference/clongbinary-class.md). Genel olarak, `CByteArray` büyük ikili verileri yönetmek için tercih edilen yöntemdir.  
  
 `CByteArray` ' den daha fazla yükü gerektirdiğinden `CLongBinary` ancak açıklandığı gibi daha yetenekli [CLongBinary sınıfı](#_core_the_cbytearray_class). `CLongBinary` kısa bir süre içinde açıklanan [CLongBinary sınıfı](#_core_the_clongbinary_class).  
  
 Kullanma hakkında ayrıntılı bilgi için `CByteArray` büyük veri öğeleri ile çalışmak için bkz: [Teknik Not 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_cbytearray_class"></a> CLongBinary sınıfı  
 `CByteArray` MFC koleksiyon sınıfları biridir. A `CByteArray` nesne depolar dinamik bir bayt dizisi — dizi gerektiğinde büyüyebilir. Sınıfı, yerleşik C++ dizileri gibi dizini tarafından hızlı erişim sağlar. `CByteArray` nesneleri seri hale getirilmiş ve tanılama amacıyla yazılan. Sınıf, alma ve belirtilen baytları, ekleme ve bayt ekleme ve bir bayt ya da tüm baytlar kaldırma için üye işlevleri sağlar. Bu tesisler ikili veriyi ayrıştırmayı kolaylaştırır. Örneğin, ikili nesne OLE nesnesi ise, gerçek nesnenin ulaşması için bazı üstbilgi bayt iş gerekebilir.  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a> CLongBinary kayıt kümeleri içinde kullanma  
 Türü kayıt bir alan veri üyesi vererek `CByteArray`, sabit bir taban içinden sağlamış [RFX](../../data/odbc/record-field-exchange-rfx.md) aktarım böyle bir nesnenin kümenizin ve veri kaynağı arasındaki ve değiştirebileceğiniz aracılığıyla yönetebilirsiniz nesne içindeki verileri. RFX belirli bir site için alınan veriler gerekir ve arka plandaki verilere erişmek için bir yönteme ihtiyacınız vardır.  
  
 Kullanma hakkında ayrıntılı bilgi için `CByteArray` büyük veri öğeleri ile çalışmak için bkz: [Teknik Not 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_clongbinary_class"></a> CLongBinary sınıfı  
 A [CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesidir basit bir kabuk geçici bir `HGLOBAL` işlemek için yığında ayrılmış depolama bloğu. İkili büyük nesne içeren bir tablo sütunu bağlar, RFX ayırır `HGLOBAL` kayıt kümesine veri aktarmak gereken ve işleyiciyi depolar işlemek `CLongBinary` kümesinin alan.  
  
 Buna karşılık, kullandığınız `HGLOBAL` işlemek, `m_hData`, size herhangi işleyici verileriyle yaptığınız gibi üzerinde işletim verilerle kendisini çalışmak için. Bu yerdir [CLongBinary](../../mfc/reference/cbytearray-class.md) özellikleri ekler.  
  
> [!CAUTION]
>  CLongBinary nesneleri işlev çağrılarında parametre olarak kullanılamaz. Ek olarak, **:: SQLGetData**, mutlaka kaydırılabilir bir anlık görüntü için kayan performansını yavaşlatır. Kullandığınızda da doğru olabilir bir **:: SQLGetData** kendiniz dinamik şema sütunlarını almak için çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: SUM'ları ve diğer toplama sonuçlarını (ODBC) alma](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)