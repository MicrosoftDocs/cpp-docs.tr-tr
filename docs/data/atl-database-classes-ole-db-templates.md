---
title: ATL Veritabanı Sınıfları (OLE DB Şablonları)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: 2ecde060f10a7c2a056869525f58d0bb4da67963
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023444"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL Veritabanı Sınıfları (OLE DB Şablonları)

Microsoft, OLE DB, verilere çok çeşitli bilgi kaynakları ve biçimler Tekdüzen erişim sağlayan COM arabirimleri kümesi çeşitli uygulamalarını sağlar.  OLE DB resmi olarak kullanım dışı; eski kod bakımı geliştiriciler için belgelerdir. Yeni uygulamalar SQL veri kaynaklarına bağlanmak için ODBC kullanmanız gerekir.

ATL OLE DB veritabanı teknoloji birçok yaygın olarak kullanılan bir OLE DB arabirimlerini uygulayan sınıflar sağlayarak kullanımını kolaylaştırmak şablonlarında C++ OLE DB Şablonları var.

Bu şablon kitaplığı iki bölümden oluşur:

- [OLE DB Tüketici Şablonları](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB (tüketici) istemci uygulamalarını uygulamak için kullanılır.

- [OLE DB sağlayıcı şablonları](../data/oledb/ole-db-provider-templates-cpp.md) bir OLE DB sunucusu (sağlayıcı) uygulama uygulamak için kullanılır.

Ayrıca, [OLE DB tüketici öznitelikleri](../windows/ole-db-consumer-attributes.md) OLE DB tüketicileri oluşturmak için kullanışlı bir yol sağlar. OLE DB öznitelikleri çalışan OLE DB tüketicileri oluşturmak için OLE DB Tüketici şablonları temel alan kod yerleştirir.

MFC Kitaplığı sınıfını içeren Not [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), denetimlerde veritabanı kayıtlarını görüntüleyen. Doğrudan bağlı bir form görünümü görünümdür bir `CRowset` nesne ve alanlarını görüntüler `CRowset` iletişim şablonun denetimlerinde nesne.

Daha fazla bilgi için [OLE DB programlama](../data/oledb/ole-db-programming.md) ve [OLE DB Programcı Kılavuzu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketicisi Oluşturma](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[OLE DB Sağlayıcısı Oluşturma](../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB Sağlayıcı Şablonları Başvurusu](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB Şablon örnekleri](https://github.com/Microsoft/VCSamples)