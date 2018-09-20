---
title: DAO sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5af80f7a264a15f24ced0be37102802771dc6f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416688"
---
# <a name="dao-classes"></a>DAO Sınıfları

Bu sınıflar, Microsoft Visual Basic ve Microsoft Access aynı veritabanı motorunu kullanan veri erişim nesnesi (DAO) veritabanları kolay erişim vermek için diğer uygulama framework sınıfları ile çalışır. DAO sınıfları, çok çeşitli açık veritabanı bağlantısı (ODBC) sürücüleri kullanılabilir veritabanları da erişebilirsiniz.

DAO veritabanı kullanan programlar olacaktır en az bir `CDaoDatabase` nesnesi ve bir `CDaoRecordset` nesne.

> [!NOTE]
>  Artık Visual C++ ortamına ve sihirbazlar DAO (DAO sınıflarına eklenmiştir ve bunları kullanmaya devam edebilirsiniz ancak) destekler. Microsoft, yeni MFC projeleri için ODBC kullanma önerir. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.

[CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)<br/>
Adlandırılmış, parola korumalı veritabanı oturumunu, oturum açma işlemi için kapatma yönetir. Çoğu program varsayılan çalışma alanını kullanın.

[CDaoDatabase](../mfc/reference/cdaodatabase-class.md)<br/>
Veriler üzerinde çalışabileceğiniz bir veritabanına bir bağlantı.

[CDaoRecordset](../mfc/reference/cdaorecordset-class.md)<br/>
Bir veri kaynağından seçilen kayıt kümesini temsil eder.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

[CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)<br/>
Sorgu tanımı, genellikle bir bir veritabanında kayıtlı temsil eder.

[CDaoTableDef](../mfc/reference/cdaotabledef-class.md)<br/>
Temel tablonun veya eklenen tablonun saklı tanımını temsil eder.

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
DAO sınıflarından kaynaklanan bir özel durum koşulunu temsil eder.

[CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)<br/>
DAO veritabanı sınıfları tarafından kullanılan DAO kayıt alanı değişimi (DFX) yordamlarını destekler. Doğrudan bu sınıfı kullanın normalde değil.

## <a name="related-classes"></a>İlgili sınıflar

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
İkili büyük nesne (BLOB) depolama birimi için bir tanıtıcı gibi bir bit eşlemi kapsüller. `CLongBinary` nesneler, veritabanı tablolarında depolanan büyük veri nesnelerini yönetmek için kullanılır.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
OLE Otomasyon türü için sarmalayıcı **para birimi**, ondalık ayırıcıdan önce 15 basamakla ve 4 rakamdan sonra sabit nokta aritmetik türü.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE Otomasyon türü için sarmalayıcı **tarih**. Tarih ve saat değerlerini temsil eder.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
OLE Otomasyon türü için sarmalayıcı **değişken**. Verileri **değişken**s birçok biçimlerinde depolanabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

