---
title: ATL Veritabanı Sınıfları (OLE DB Şablonları)
ms.date: 05/02/2019
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: dc016a5e1e1d9652f6a69f73b5760f42dec5e889
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222562"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL Veritabanı Sınıfları (OLE DB Şablonları)

Microsoft, OLE DB, verilere çok çeşitli bilgi kaynakları ve biçimler Tekdüzen erişim sağlayan COM arabirimleri kümesi çeşitli uygulamalarını sağlar.

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
