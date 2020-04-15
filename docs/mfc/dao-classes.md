---
title: DAO Sınıfları
ms.date: 09/17/2019
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: 7ae85cbeb7790cadb8c26dfbdb7a5163dbcd47c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373510"
---
# <a name="dao-classes"></a>DAO Sınıfları

DAO Access veritabanları ile kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir.

Bu sınıflar, Microsoft Visual Basic ve Microsoft Access ile aynı veritabanı altyapısını kullanan Veri Erişim Nesnesi (DAO) veritabanlarına kolay erişim sağlamak için diğer uygulama çerçeve sınıflarıyla birlikte çalışır. DAO sınıfları, Açık Veritabanı Bağlantısı (ODBC) sürücülerinin kullanılabildiği çok çeşitli veritabanlarına da erişebilir.

DAO veritabanlarını kullanan programların en `CDaoDatabase` az bir `CDaoRecordset` nesnesi ve nesnesi olacaktır.

> [!NOTE]
> Visual C++ ortamı ve sihirbazlar artık DAO'yu desteklemektedir (her ne kadar DAO sınıfları dahil olsa da ve bunları kullanmaya devam edebilirsiniz). Microsoft, yeni MFC projeleri için ODBC kullanmanızı önerir. DAO'yu yalnızca varolan uygulamaları korurken kullanmalısınız.

[Cdaoworkspace](../mfc/reference/cdaoworkspace-class.md)<br/>
Oturum açmadan oturum kapatmaya kadar adlandırılmış, parola korumalı bir veritabanı oturumunu yönetir. Çoğu program varsayılan çalışma alanını kullanır.

[Cdaodatabase](../mfc/reference/cdaodatabase-class.md)<br/>
Verileri üzerinde çalışabileceğiniz bir veritabanına bağlantı.

[Cdaorecordset](../mfc/reference/cdaorecordset-class.md)<br/>
Veri kaynağından seçilen bir kayıt kümesini temsil eder.

[Cdaorecordview](../mfc/reference/cdaorecordview-class.md)<br/>
Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

[Cdaoquerydef](../mfc/reference/cdaoquerydef-class.md)<br/>
Genellikle veritabanına kaydedilmiş bir sorgu tanımını temsil eder.

[Cdaotabledef](../mfc/reference/cdaotabledef-class.md)<br/>
Bir taban tablonun veya ekli tablonun depolanan tanımını temsil eder.

[Cdaoexception](../mfc/reference/cdaoexception-class.md)<br/>
DAO sınıflarından kaynaklanan bir özel durum dur.

[CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)<br/>
DAO veritabanı sınıfları tarafından kullanılan DAO kayıt alanı değişimi (DFX) yordamlarını destekler. Normalde bu sınıfı doğrudan kullanmazsınız.

## <a name="related-classes"></a>İlgili Sınıflar

[Clongbinary](../mfc/reference/clongbinary-class.md)<br/>
Bitmap gibi ikili büyük bir nesne (BLOB) için depolamaya bir tutamacı kapsüller. `CLongBinary`nesneler veritabanı tablolarında depolanan büyük veri nesnelerini yönetmek için kullanılır.

[Colecurrency](../mfc/reference/colecurrency-class.md)<br/>
Ondalık noktadan önce 15 basamaklı ve 4 basamak sonra bir sabit nokta aritmetik türü olan OLE otomasyon türü **CURRENCY**için sarıcı.

[Coledatetime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE otomasyon türü **DATE**için sarıcı. Tarih ve saat değerlerini temsil eder.

[Colevariant](../mfc/reference/colevariant-class.md)<br/>
OLE otomasyon tipi **VARIANT**için sarıcı . **VARIANT**s'deki veriler birçok formatta saklanabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../mfc/class-library-overview.md)
