---
title: DAO Sınıfları
ms.date: 09/17/2019
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: 51abd29ef4de5d70f4a5b2b6b14b53510e7876a1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615927"
---
# <a name="dao-classes"></a>DAO Sınıfları

DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

Bu sınıflar, Microsoft Visual Basic ve Microsoft Access ile aynı veritabanı altyapısını kullanan veri erişim nesnesi (DAO) veritabanlarına kolay erişim sağlamak için diğer uygulama çerçevesi sınıflarıyla birlikte çalışır. DAO sınıfları, açık veritabanı bağlantısı (ODBC) sürücülerinin kullanılabildiği çok çeşitli veritabanlarına da erişebilir.

DAO veritabanları kullanan programlar en az bir `CDaoDatabase` nesne ve bir `CDaoRecordset` nesne olacaktır.

> [!NOTE]
> Visual C++ ortamı ve sihirbazları artık DAO desteklememektedir (DAO sınıfları dahil edilir ancak yine de kullanabilirsiniz). Microsoft, yeni MFC projeleri için ODBC kullanmanızı önerir. Yalnızca var olan uygulamaları korumak için DAO kullanmanız gerekir.

[Cdaoçalışma alanı](reference/cdaoworkspace-class.md)<br/>
Adlandırılmış, parola korumalı bir veritabanı oturumunu, oturum açmak için oturumdan yönetir. Çoğu program varsayılan çalışma alanını kullanır.

[CDaoDatabase](reference/cdaodatabase-class.md)<br/>
Veri üzerinde çalışabileceğiniz bir veritabanıyla bağlantı.

[CDaoRecordset](reference/cdaorecordset-class.md)<br/>
Bir veri kaynağından seçilen bir kayıt kümesini temsil eder.

[CDaoRecordView](reference/cdaorecordview-class.md)<br/>
Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

[CDaoQueryDef](reference/cdaoquerydef-class.md)<br/>
Genellikle bir veritabanına kaydedilmiş bir sorgu tanımını temsil eder.

[CDaoTableDef](reference/cdaotabledef-class.md)<br/>
Bir temel tablonun veya eklenmiş tablonun saklı tanımını temsil eder.

[CDaoException](reference/cdaoexception-class.md)<br/>
DAO sınıflarından kaynaklanan bir özel durum koşulunu temsil eder.

[Cdadofieldexchange](reference/cdaofieldexchange-class.md)<br/>
DAO veritabanı sınıfları tarafından kullanılan DAO Kayıt alanı değişimi (DFX) yordamlarını destekler. Normalde bu sınıfı doğrudan kullanamazsınız.

## <a name="related-classes"></a>İlgili sınıflar

[CLongBinary](reference/clongbinary-class.md)<br/>
Bir bit eşlem gibi ikili büyük nesne (BLOB) için bir tanıtıcıyı saklar. `CLongBinary`nesneler, veritabanı tablolarında depolanan büyük veri nesnelerini yönetmek için kullanılır.

[Colet para birimi](reference/colecurrency-class.md)<br/>
Sabit noktalı aritmetik tür olan ve sonra ondalık noktadan önce 15 basamakla ve sonrasında 4 basamaktan oluşan OLE Otomasyon türü **para birimi**için sarmalayıcı.

[Cotadatetime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE Otomasyonu tür **tarihi**için sarmalayıcı. Tarih ve saat değerlerini temsil eder.

[Colet varyantı](reference/colevariant-class.md)<br/>
OLE Otomasyonu tür **varyantı**için sarmalayıcı. **VARIANT**'lar içindeki veriler birçok biçimde depolanabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
