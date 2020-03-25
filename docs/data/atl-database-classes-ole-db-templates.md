---
title: ATL Veritabanı Sınıfları (OLE DB Şablonları)
ms.date: 05/02/2019
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: 76e9f49d4b394d0c807ca1f3d103ff325ded8a09
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213505"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL Veritabanı Sınıfları (OLE DB Şablonları)

Microsoft, farklı bilgi kaynaklarındaki ve biçimlerdeki verilere tek biçimli erişim sağlayan bir COM arabirimleri kümesi olan OLE DB çeşitli uygulamaları sağlar.

OLE DB şablonları, yaygın C++ olarak kullanılan OLE DB arabirimlerinin çoğunu uygulayan sınıflar sağlayarak OLE DB veritabanı teknolojisinin daha kolay KULLANıLMASıNı sağlayan ATL 'deki şablonlardır.

Bu şablon kitaplığı iki bölüm içerir:

- [OLE DB tüketici şablonları](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB istemcisi (tüketici) uygulaması uygulamak için kullanılır.

- [OLE DB sağlayıcı şablonları](../data/oledb/ole-db-provider-templates-cpp.md) OLE DB sunucusu (sağlayıcı) uygulamasını uygulamak için kullanılır.

Ayrıca, [OLE DB tüketici öznitelikleri](../windows/ole-db-consumer-attributes.md) , OLE DB tüketicileri oluşturmak için kullanışlı bir yol sağlar. OLE DB öznitelikleri, çalışan OLE DB tüketicileri oluşturmak için OLE DB tüketici şablonlarına göre kod ekler.

MFC kitaplığı, denetimler içindeki veritabanı kayıtlarını görüntüleyen bir sınıf olan [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)sınıfı içerdiğini unutmayın. Görünüm bir `CRowset` nesnesine doğrudan bağlı bir form görünümüdür ve iletişim kutusu şablonunun denetimlerinde `CRowset` nesnesinin alanlarını görüntüler.

Daha fazla bilgi için bkz. [OLE DB Programlama](../data/oledb/ole-db-programming.md) ve [OLE DB Programcı Kılavuzu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketicisi Oluşturma](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[OLE DB Sağlayıcısı Oluşturma](../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB Sağlayıcı Şablonları Başvurusu](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB şablonları örnekleri](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB)
