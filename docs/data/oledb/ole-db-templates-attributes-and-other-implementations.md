---
title: OLE DB Şablonları, öznitelikler ve diğer uygulamalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6e5fa63a0da718b80c2b0d61e5215a947e21d496
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101725"
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>OLE DB Şablonları, Öznitelikler ve Diğer Uygulamalar

## <a name="atl-ole-db-templates"></a>ATL OLE DB Şablonları  

OLE DB ATL (Etkin Şablon Kütüphanesi) parçası olan şablonlar, yüksek performanslı OLE DB veritabanı teknoloji birçok yaygın olarak kullanılan bir OLE DB arabirimlerini uygulayan sınıflar sağlayarak kullanmak kolaylaştırır. Yanı sıra bu şablon OLE DB başlangıç uygulamaları oluşturmak için sihirbaz desteği kitaplığı gelir.  
  
Bu şablon kitaplığı iki bölümden oluşur:  
  
- **OLE DB Tüketici Şablonları** OLE DB (tüketici) istemci uygulamalarını uygulamak için kullanılır.  
  
- **OLE DB sağlayıcı şablonları** bir OLE DB sunucusu (sağlayıcı) uygulama uygulamak için kullanılır.  
  
OLE DB Şablonları kullanmak için C++ şablonları, COM ve OLE DB arabirimleri ile ilgili bilgi sahibi olmalıdır. OLE DB ile ilgili bilgi sahibi değilseniz bkz [OLE DB Programcının Başvurusu](/previous-versions/windows/desktop/ms713643\(v=vs.85\)).  
  
Daha fazla bilgi için şunları yapabilirsiniz:  
  
- İlgili konuları okuyun [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md) veya [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
- Oluşturma bir [OLE DB Tüketici](../../data/oledb/creating-an-ole-db-consumer.md) veya [OLE DB sağlayıcısı](../../data/oledb/creating-an-ole-db-provider.md).  
  
- Listesine bakın [OLE DB Tüketici sınıflar](../../data/oledb/ole-db-consumer-templates-reference.md) veya [OLE DB sağlayıcısı sınıfları](../../data/oledb/ole-db-provider-templates-reference.md).  
  
- Listesine bakın [OLE DB Şablon örnekleri](https://github.com/Microsoft/VCSamples).  
  
- Bkz: [OLE DB Programcının Başvurusu](/previous-versions/windows/desktop/ms713643\(v=vs.85\)) (içinde Windows SDK'sı).  
  
## <a name="ole-db-attributes"></a>OLE DB öznitelikleri  

[OLE DB tüketici öznitelikleri](../../windows/ole-db-consumer-attributes.md) OLE DB tüketicileri oluşturmak için kullanışlı bir yol sağlar. OLE DB özniteliklere göre kod ekleme [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-reference.md) çalışma OLE DB Tüketicileri ve sağlayıcıları oluşturmak için. Öznitelikleri tarafından desteklenmeyen bir işlev belirtmek gerekirse, OLE DB Şablonları öznitelikleri ile birlikte kodunuzda kullanabilirsiniz.  
  
## <a name="mfc-ole-db-classes"></a>MFC OLE DB sınıfları  

MFC Kitaplığı bir sınıfı olan [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), denetimlerde veritabanı kayıtlarını görüntüleyen. Doğrudan bağlı bir form görünümü görünümdür bir `CRowset` nesne ve alanlarını görüntüler `CRowset` iletişim şablonun denetimlerinde nesne. Ayrıca taşımak için varsayılan bir uygulama sağlar, ilk İleri, önceki ya da son kaydını ve kayıtta şu anda Görünümü güncelleştirmek için bir arabirim. Daha fazla bilgi için bkz. `COleDBRecordView`.  
  
## <a name="ole-db-sdk-interfaces"></a>OLE DB SDK arabirimleriyle  

Burada OLE DB Şablonları, OLE DB işlevselliğini desteklemeyen durumlarda, OLE DB arabirimlerini kullanmanız gerekir. Daha fazla bilgi için [OLE DB Programcının Başvurusu](/previous-versions/windows/desktop/ms713643\(v=vs.85\)) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)