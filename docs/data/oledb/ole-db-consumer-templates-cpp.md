---
description: 'Hakkında daha fazla bilgi edinin: OLE DB tüketici şablonları (C++)'
title: OLE DB Tüketici Şablonları (C++)
ms.date: 10/22/2018
helpviewer_keywords:
- databases [C++], OLE DB templates
- OLE DB consumers [C++], data access
- OLE DB consumer templates [C++]
- databases [C++], consumers
ms.assetid: d3e42612-0bc0-4d65-9c32-0e8a7b219e82
ms.openlocfilehash: 6aaf935234b8ec3396c97345ca7e38a0f8d806bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317161"
---
# <a name="ole-db-consumer-templates-c"></a>OLE DB Tüketici Şablonları (C++)

OLE DB tüketici şablonları OLE DB sürüm 2,6 belirtimini destekler. (OLE DB tüketici şablonları, OLE DB 2,6 'e göre test edilir ancak belirtimde her arabirimi desteklemez.) Tüketici şablonları, OLE DB tüketicisini uygulamak için yazmanız gereken kod miktarını en aza indirir. Şablonlar şunları sağlar:

- OLE DB özelliklere kolay erişim ve ATL ve MFC ile kolay tümleştirme.

- Veritabanı parametreleri ve sütunları için kolay bağlama modeli.

- OLE DB programlama için yerel C/C++ veri türleri.

OLE DB şablonlarını kullanmak için, C++ şablonları, COM ve OLE DB arabirimleri hakkında bilgi sahibi olmanız gerekir. OLE DB hakkında bilgi sahibi değilseniz [SQL Server Için Microsoft OLE DB sürücü](/sql/connect/oledb/oledb-driver-for-sql-server)' ne bakın.

OLE DB şablonları, yeni bir nesne modeli eklemek yerine mevcut OLE DB nesne modelini destekler. OLE DB tüketici şablonlarındaki en üst katman sınıfları OLE DB belirtiminde tanımlanan bileşenleri paralel olarak. OLE DB tüketici şablonlarının tasarımı, bir satır kümesinde birden çok erişimci gibi gelişmiş özellikler içerir. Şablonların kullanımı ve birden çok devralma, kitaplığı küçük ve esnek hale getirir.

## <a name="how-ole-db-consumers-access-data"></a>OLE DB tüketicileri verilere nasıl erişir

Tüketiciler, aşağıdaki konularda açıklanan çeşitli nesne türlerini kullanır:

- [Veri kaynakları ve oturumlar](../../data/oledb/data-sources-and-sessions.md)

- [Erişimciler ve satır kümeleri](../../data/oledb/accessors-and-rowsets.md)

- [Komutlar ve tablolar](../../data/oledb/commands-and-tables.md)

- [Kullanıcı kayıtları](../../data/oledb/user-records.md)

Tüketici hiçbir şey yapmadan önce, erişmeniz gereken veritabanı türü için uygun bir OLE DB sağlayıcı seçin (örneğin, SQL, Oracle, ODBC ve MSDS). Bunu yapmak için genellikle bir Numaralandırıcı kullanırsınız ( [veri kaynakları ve oturumlarda](../../data/oledb/data-sources-and-sessions.md)belirtildiği şekilde, bkz. [CEnumerator](../../data/oledb/cenumerator-class.md) ).

[Veri kaynağı nesnesi](../../data/oledb/data-sources-and-sessions.md) , seçtiğiniz veri kaynağına bağlanmak için gerekli olan bağlantı bilgilerini sağlar. Veri kaynağı nesnesi Ayrıca, kullanıcılara veri kaynağına erişim izni vermek için kullanılan kimlik doğrulama bilgilerini (örneğin, oturum açma adları ve parolalar) içerir. Veri kaynağı nesnesi veritabanına bir bağlantı yapar ve ardından bir veya daha fazla oturum nesnesi oluşturur. Her [oturum nesnesi](../../data/oledb/data-sources-and-sessions.md) , veritabanı ile kendi etkileşimlerini yönetir (yani, verileri sorgulama ve alma) ve bu işlemleri diğer mevcut oturumlardan bağımsız olarak gerçekleştirir.

Oturum satır kümesi ve komut nesnelerini oluşturur. [Komut nesnesi](../../data/oledb/commands-and-tables.md) , kullanıcıların veritabanıyla etkileşime geçmesini sağlar, ÖRNEĞIN, SQL komutlarını kullanma. [Satır kümesi nesnesi](../../data/oledb/accessors-and-rowsets.md) , içinde gezinebileceğiniz ve [satırları güncelleştirebilir, silebileceğiniz ve ekleyebileceğiniz](../../data/oledb/updating-rowsets.md)bir veri kümesidir.

OLE DB tüketicisi, veritabanı tablolarındaki sütunları yerel değişkenlerle bağlar; Bunu yapmak için, verilerin tüketici içinde nasıl depolandığını içeren bir harita içeren bir [erişimci](../../data/oledb/accessors-and-rowsets.md)kullanır. Eşleme, tüketici uygulamasındaki tablo sütunları ve yerel arabellekler (değişkenler) arasındaki bağlamalar kümesinden oluşur.

Tüketicilerle çalışırken önemli bir kavram, bir tüketicide iki sınıf bildirmenizin yanı sıra [komut (veya tablo) sınıfı](../../data/oledb/commands-and-tables.md) ve [Kullanıcı kayıt sınıfı](../../data/oledb/user-records.md). Satır kümesine, hem erişimci sınıfından hem de satır kümesi sınıfından devralan komut (veya tablo) sınıfı aracılığıyla erişirsiniz. Kullanıcı kayıt sınıfı, daha önce açıklanan satır kümesi bağlama eşlemesini içerir.

Daha fazla bilgi edinmek için aşağıdaki kaynaklara bakın:

- [OLE DB tüketicisi oluşturma](../../data/oledb/creating-an-ole-db-consumer.md)

- [Ortak OLE DB tüketici senaryoları (örnekler)](../../data/oledb/working-with-ole-db-consumer-templates.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[Veri Erişimi](../data-access-in-cpp.md)<br/>
[SDK belgelerini OLE DB](/previous-versions/windows/desktop/ms722784(v=vs.85))<br/>
[SQL Server için Microsoft OLE DB sürücüsü](/sql/connect/oledb/oledb-driver-for-sql-server)
