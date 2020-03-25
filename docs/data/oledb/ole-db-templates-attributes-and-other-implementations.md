---
title: OLE DB Şablonları, Öznitelikler ve Diğer Uygulamalar
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
ms.openlocfilehash: 722bfdf02dc89e061351fd2a87b5d019db10da6e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209891"
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>OLE DB Şablonları, Öznitelikler ve Diğer Uygulamalar

## <a name="atl-ole-db-templates"></a>ATL OLE DB şablonları

ATL 'nin (etkin şablon kitaplığı) bir parçası olan OLE DB şablonları, yaygın olarak kullanılan OLE DB arabirimlerinin çoğunu uygulayan sınıflar sağlayarak yüksek performanslı OLE DB veritabanı teknolojisini daha kolay hale getirir. Bu şablon kitaplığı ile birlikte, OLE DB Starter uygulamaları oluşturmak için sihirbaz desteği sunar.

Bu şablon kitaplığı iki bölüm içerir:

- **OLE DB tüketici şablonları** OLE DB istemcisi (tüketici) uygulaması uygulamak için kullanılır.

- **OLE DB sağlayıcı şablonları** OLE DB sunucusu (sağlayıcı) uygulamasını uygulamak için kullanılır.

OLE DB şablonlarını kullanmak için şablonlar, COM ve OLE DB arabirimleriyle C++ ilgili bilgi sahibi olmanız gerekir. OLE DB hakkında bilgi sahibi değilseniz, [OLE DB Programcı başvurusu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)' na bakın.

Daha fazla bilgi için şunları yapabilirsiniz:

- [OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md) veya [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)hakkındaki konuları okuyun.

- [OLE DB tüketicisi](../../data/oledb/creating-an-ole-db-consumer.md) veya [OLE DB sağlayıcısı](../../data/oledb/creating-an-ole-db-provider.md)oluşturun.

- [OLE DB tüketici sınıfları](../../data/oledb/ole-db-consumer-templates-reference.md) veya [OLE DB sağlayıcı sınıfları](../../data/oledb/ole-db-provider-templates-reference.md)listesine bakın.

- [OLE DB şablonları örnekleri](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB)listesine bakın.

- Bkz. [OLE DB Programcı başvurusu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) (Windows SDK).

## <a name="ole-db-attributes"></a>OLE DB öznitelikleri

[OLE DB tüketici öznitelikleri](../../windows/ole-db-consumer-attributes.md) , OLE DB tüketicileri oluşturmak için kullanışlı bir yol sağlar. OLE DB öznitelikleri, çalışan OLE DB tüketicileri ve sağlayıcıları oluşturmak için [OLE DB tüketici şablonlarına](../../data/oledb/ole-db-consumer-templates-reference.md) göre kod ekler. Öznitelikleri tarafından desteklenmeyen işlevselliği belirtmeniz gerekiyorsa, OLE DB şablonlarını kodunuzda özniteliklerle birlikte kullanabilirsiniz.

## <a name="mfc-ole-db-classes"></a>MFC OLE DB sınıfları

MFC kitaplığı, denetimlerde veritabanı kayıtlarını görüntüleyen bir sınıf olan [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)sınıfı içerir. Görünüm bir `CRowset` nesnesine doğrudan bağlı bir form görünümüdür ve iletişim kutusu şablonunun denetimlerinde `CRowset` nesnesinin alanlarını görüntüler. Ayrıca, ilk, sonraki, önceki veya son kayda geçiş için varsayılan bir uygulama ve şu anda görünümdeki kayıtları güncelleştirmek için bir arabirim sağlar. Daha fazla bilgi için bkz. `COleDBRecordView`.

## <a name="ole-db-sdk-interfaces"></a>SDK arabirimlerini OLE DB

OLE DB Şablonlarının OLE DB işlevselliğini desteklememesi durumunda OLE DB arabirimlerini kullanmanız gerekir. Daha fazla bilgi için, Windows SDK [OLE DB Programcı başvurusu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)
