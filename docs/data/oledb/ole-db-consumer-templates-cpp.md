---
title: OLE DB Tüketici Şablonları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- databases [C++], OLE DB templates
- OLE DB consumers [C++], data access
- OLE DB consumer templates [C++]
- databases [C++], consumers
ms.assetid: d3e42612-0bc0-4d65-9c32-0e8a7b219e82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 636f98337cacdeddbdd42dd74e498c0fbd12e4f8
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339405"
---
# <a name="ole-db-consumer-templates-c"></a>OLE DB Tüketici Şablonları (C++)
OLE DB Tüketici Şablonları, OLE DB sürüm 2.6 belirtimini destekler. (OLE DB Tüketici Şablonları OLE DB 2.6 karşı test edilmez ancak her arabirim belirtiminde desteklemez.) Tüketici Şablonları bir OLE DB Tüketicisi uygulamak için yazmanız gereken kod miktarını en aza indirin. Şablonlar sağlar:  
  
-   OLE DB özellikleri ve ATL ve MFC ile kolay tümleştirme kolay erişim.  
  
-   Veritabanı parametreler ve sütun için bir kolayca bağlama modeli.  
  
-   OLE DB programlama için yerel C/C++ veri türleri.  
  
 OLE DB Şablonları kullanmak için C++ şablonları, COM ve OLE DB arabirimleri ile ilgili bilgi sahibi olmalıdır. OLE DB ile ilgili bilgi sahibi değilseniz bkz [OLE DB Programcının Başvurusu](https://msdn.microsoft.com/library/ms718124.aspx).  
  
 OLE DB Şablonları, yeni bir nesne modeli eklemek yerine var olan OLE DB Nesne modeli destekler. OLE DB Tüketici Şablonları üst düzey sınıflar, OLE DB belirtiminde tanımlanan bileşenleri paralel. OLE DB Tüketici Şablonları tasarımını üzerinde bir satır kümesinde çoklu erişimci gibi gelişmiş özellikleri içerir. Şablonları ve birden çok devralma kitaplığı, küçük ve esnek hale getirir.  
  
## <a name="how-ole-db-consumers-access-data"></a>OLE DB tüketicileri verilere nasıl  
 Aşağıdaki konularda açıklanan nesneler çeşitli türlerde tüketiciler kullanın:  
  
-   [Veri Kaynakları ve Oturumlar](../../data/oledb/data-sources-and-sessions.md)  
  
-   [Erişimciler ve Satır Kümeleri](../../data/oledb/accessors-and-rowsets.md)  
  
-   [Komutlar ve Tablolar](../../data/oledb/commands-and-tables.md)  
  
-   [Kullanıcı Kayıtları](../../data/oledb/user-records.md)  
  
 Tüketici herhangi bir şey yapmadan önce ilk veritabanı (örneğin, SQL, Oracle, ODBC ve MSDS) erişmeniz türü için uygun bir OLE DB sağlayıcısı seçin. Bunu yapmak için genellikle bir numaralandırıcı kullanır (bkz [CEnumerator](../../data/oledb/cenumerator-class.md) belirtildiği gibi [veri kaynakları ve oturumlar](../../data/oledb/data-sources-and-sessions.md)).  
  
 [Veri kaynağı nesnesi](../../data/oledb/data-sources-and-sessions.md) seçtiğiniz veri kaynağına bağlanmak için gereken bağlantı bilgilerini sağlar. Veri kaynağı nesnesi, ayrıca, kullanıcılar veri kaynağına erişim izni vermek için kullanılan kimlik doğrulama bilgilerini (örneğin, oturum açma adları ve parolalar) içerir. Veri kaynağı nesnesi, veritabanına bir bağlantı kurar ve ardından bir veya daha fazla oturum nesneleri oluşturur. Her [oturum nesnesi](../../data/oledb/data-sources-and-sessions.md) (diğer bir deyişle, sorgulama ve veri alma) veritabanı ile kendi etkileşimlerini yönetir ve diğer oturumlarına bağımsız olarak bu işlemleri gerçekleştirir.  
  
 Oturum satır ve komut nesneleri oluşturur. [Komut nesnesi](../../data/oledb/commands-and-tables.md) kullanıcıların veritabanıyla, örneğin, SQL komutlarını kullanarak etkileşim kurmanıza olanak tanır. [Satır kümesi nesnesi](../../data/oledb/accessors-and-rowsets.md) , alabilir ve hangi gezinebileceğiniz aracılığıyla veri kümesi [güncelleştirme, silme ve Satır Ekle](../../data/oledb/updating-rowsets.md).  
  
 Bir OLE DB Tüketicisi sütunları yerel değişkenlerle veritabanı tablolarındaki bağlar; Bunu yapmak için kullandığı bir [erişimci](../../data/oledb/accessors-and-rowsets.md), tüketici veriler nasıl depolanır, bir harita içerir. Harita bağlamaları tablo sütunları ve tüketici uygulama yerel arabellekleri (değişken) arasında bir dizi oluşur.  
  
 Biri tüketicileriyle çalışırken önemli kavramı bir tüketici iki sınıf bildirmek: [komutu (veya tablo) sınıfı](../../data/oledb/commands-and-tables.md) ve [kullanıcı kayıt sınıfı](../../data/oledb/user-records.md). Satır kümesi, bir erişimci sınıfında hem bir satır kümesi sınıfının devraldığı komutu (veya tablo) sınıfı aracılığıyla erişin. Kullanıcı kayıt sınıfı, daha önce açıklanan satır kümesi bağlama eşlemesi içerir.  
  
 Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer.md)  
  
-   [OLE DB Tüketici senaryoları (örnekler)](../../data/oledb/working-with-ole-db-consumer-templates.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB programlama](../../data/oledb/ole-db-programming.md)   
 [Veri erişimi](../data-access-in-cpp.md)   
 [OLE DB SDK Belgeleri](https://msdn.microsoft.com/library/ms722784.aspx)   
 [OLE DB Programcının Başvurusu](https://msdn.microsoft.com/library/ms713643.aspx)