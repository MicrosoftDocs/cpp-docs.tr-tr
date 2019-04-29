---
title: OLE DB Programlama
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB [C++]
- data access [C++], OLE DB programming
- OLE DB [C++], about OLE DB
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
ms.openlocfilehash: ac74f94b4cdc738237c2994646f7602f7f5118ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361249"
---
# <a name="ole-db-programming"></a>OLE DB Programlama

Microsoft OLE DB eski bir teknolojidir; Yeni uygulamalar için bağlı SQL sunucuları için gereken veri erişimi API'si kullanılır. Diğer tüm yeni uygulamaları ODBC kullanmanız gerekir. SQL Server için geçerli OLE DB sağlayıcısı SQLNCLI11 ' dir. DLL. Sağlayıcı, SQL Server 2016'da hala sunulmamaktadır. Bu belge, OLE DB kullanmakta olan mevcut uygulamaları korumak için geliştiriciler içindir.

OLE DB Şablonları, OLE DB arabirimlerini C++ şablonları, yüksek performanslı OLE DB veritabanı teknoloji uygulayan sınıflar sağlayarak kullanmak yaygın olarak birçok kolaylaştırmak kullanılan ' dir. Bu şablon kitaplığı Tüketici Şablonları ve sağlayıcı şablonları bölünmüştür.

Visual C++ OLE DB başlangıç uygulamaları oluşturmak için sihirbaz desteği de vardır.

Ayrıca, OLE DB Tüketici Şablonları uygulamak için öznitelikler kullanabilirsiniz.

|Hakkında daha fazla bilgi edinmek için|Bkz. |
|-------------------------|---------|
|OLE DB Tüketici Şablonları (kavramsal konular) kullanma|[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)|
|OLE DB sağlayıcı şablonları (kavramsal konular) kullanma|[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)|
|OLE DB şablon sınıfları ve makroları|[OLE DB Şablonları başvurusu](../../data/oledb/ole-db-templates.md) (Visual C++)|
|OLE DB tüketici öznitelikleri|[OLE DB Tüketici Öznitelikleri](../../windows/ole-db-consumer-attributes.md)|
|OLE DB arabirimleri|[OLE DB Programcının Başvurusu](/sql/connect/oledb/oledb-driver-for-sql-server) (Windows SDK'da)|
|OLE DB Şablon örnekleri|[OLE DB Şablon örnekleri](https://github.com/Microsoft/VCSamples)|
|Veri erişim programlama genel bakış (Visual C++)|[Veri erişim programlama](../../data/data-access-programming-mfc-atl.md)|
|ODBC kavramsal konular|[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Erişimi](../data-access-in-cpp.md)