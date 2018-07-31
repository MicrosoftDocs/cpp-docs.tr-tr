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
ms.openlocfilehash: 38915b3a10f1ed3e2a175687937b3b18a60a9be4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338499"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Kayıt kümesi: Büyük Veri Öğeleri ile Çalışma (ODBC)
Bu konuda, hem MFC ODBC sınıfları ve MFC DAO sınıflarına uygulanır.  
  
> [!NOTE]
>  MFC DAO sınıflarına kullanıyorsanız, büyük veri öğeleri sınıfı ile yönetme [CByteArray](../../mfc/reference/cbytearray-class.md) sınıfı yerine [CLongBinary](../../mfc/reference/clongbinary-class.md). MFC ODBC sınıfları toplu satır getirme ile kullanıyorsanız, `CLongBinary` yerine `CByteArray`. Toplu satır getirme hakkında daha fazla bilgi için bkz. [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Veritabanınızın büyük bit eşlemler (çalışan fotoğrafları, haritalar, resimler ürünleri, OLE nesneleri, vb.) gibi veri parçalarını depolayabilirsiniz varsayalım. Bu tür verilerin genellikle bir ikili büyük nesne (veya BLOB) çünkü adlandırılır:  
  
-   Her bir alanın değeri büyük/küçük harf büyüktür.  
  
-   Sayı ve diğer basit veri türleri farklı olarak, hiçbir öngörülebilir boyutu vardır.  
  
-   Programınızı perspektifinden formless verilerdir.  
  
 Bu konuda, bu tür nesneler ile çalışma için veritabanı sınıfları sağlar. hangi Destek Hizmetleri açıklanmaktadır.  
  
##  <a name="_core_managing_large_objects"></a> Büyük nesneler yönetme  
 Kayıt kümelerini yönetme ikili büyük nesneler özel zorluğunu çözmek için iki yolu vardır. Sınıf kullanabileceğiniz [CByteArray](../../mfc/reference/cbytearray-class.md) veya sınıf kullanabileceğiniz [CLongBinary](../../mfc/reference/clongbinary-class.md). Genel olarak, `CByteArray` büyük ikili verileri yönetmek için tercih edilen yoludur.  
  
 `CByteArray` değerinden daha fazla ek yük gerektirir `CLongBinary` ancak açıklandığı gibi daha yetenekli [CByteArray sınıfı](#_core_the_cbytearray_class). `CLongBinary` kısa bir süre içinde açıklanan [CLongBinary sınıfı](#_core_the_clongbinary_class).  
  
 Kullanma hakkında ayrıntılı bilgi için `CByteArray` büyük veri öğeleri ile çalışmak için bkz [Teknik Not 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_cbytearray_class"></a> CByteArray sınıfı  
 `CByteArray` MFC koleksiyon sınıfları biridir. A `CByteArray` nesnesini depolar dinamik bir bayt dizisi — dizi gerektiğinde büyüyebilir. Sınıfı, yerleşik C++ dizileri içeren dizine göre hızlı erişim sağlar. `CByteArray` nesneleri seri hale getirilmiş ve tanılama amacıyla yazılan. Sınıfı, alma ve belirtilen baytları, ekleme ve bayt ekleme ve bir bayt ya da tüm baytlar kaldırma için üye işlevlerini sağlar. Şu tesisler ikili veriyi ayrıştırmayı kolaylaştırır. Örneğin, ikili nesne bir OLE nesne ise, gerçek nesneye erişmek için üstbilgi baytlarıyla çalışmak gerekebilir.  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a> CByteArray kayıt kümeleri içinde kullanma  
 Kümenizin alan veri üyesi tür vererek `CByteArray`, bir sabit temelden sağladığınız [RFX](../../data/odbc/record-field-exchange-rfx.md) aktarımını böyle bir nesnenin kümenizin ve veri kaynağı arasında ve değiştirebileceğiniz aracılığıyla yönetebilirsiniz veri nesnesi içinde. RFX belirli bir site için veri alındı gerekir ve temel alınan verilere erişmek için bir yönteme ihtiyacınız vardır.  
  
 Kullanma hakkında ayrıntılı bilgi için `CByteArray` büyük veri öğeleri ile çalışmak için bkz [Teknik Not 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_clongbinary_class"></a> CLongBinary sınıfı  
 A [CLongBinary](../../mfc/reference/clongbinary-class.md) nesnedir, basit bir kabuk etrafında bir `HGLOBAL` işlemek için yığın üzerinde ayrılan depolama bloğu. İkili büyük nesne içeren bir tablo sütunu bağlar, RFX ayırır `HGLOBAL` kayıt kümesine veri aktarması ve tutamacın depolar işlemek `CLongBinary` alan kümesi.  
  
 Buna karşılık, kullandığınız `HGLOBAL` tutamacını `m_hData`herhangi verileri işlemek şekilde üzerinde çalışan verilerle kendisini çalışmak için. Burada [CByteArray](../../mfc/reference/cbytearray-class.md) özellikleri ekler.  
  
> [!CAUTION]
>  CLongBinary nesneleri, işlev çağrıları parametre olarak kullanılamaz. Ek olarak, `::SQLGetData`, kaydırılabilir bir anlık görüntü için kayan performansı yavaşlatabilir. Kullandığınızda da doğru olabilir bir `::SQLGetData` çağrısını kendiniz dinamik şema sütunları alınamıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: SUM'ları ve diğer toplama sonuçlarını (ODBC) alma](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)