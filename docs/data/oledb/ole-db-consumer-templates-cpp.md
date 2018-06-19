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
ms.openlocfilehash: 39264ed7485e67377963316730689645c73f185f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112114"
---
# <a name="ole-db-consumer-templates-c"></a>OLE DB Tüketici Şablonları (C++)
OLE DB Tüketici Şablonları OLE DB sürüm 2.6 belirtimini destekler. (OLE DB Tüketici Şablonları OLE DB 2.6 karşı test ancak her arabirimi belirtimini desteklemez.) Tüketici Şablonları bir OLE DB Tüketicisi uygulamak için yazmanız gereken kod miktarını en aza indirir. Şablonlar sağlar:  
  
-   Kolay erişim için OLE DB özellikleri ve ATL ve MFC ile kolay tümleştirme.  
  
-   Veritabanı parametreleri ve sütunlar için bir kolay bağlama modeli.  
  
-   OLE DB programlama için yerel C/C++ veri türleri.  
  
 OLE DB Şablonları kullanmak için C++ şablonları, COM ve OLE DB arabirimleri ile bilgi sahibi olmanız. OLE DB ile bilmiyorsanız bkz [OLE DB Programcının Başvurusu](https://msdn.microsoft.com/en-us/library/ms718124.aspx).  
  
 OLE DB Şablonları, yeni bir nesne modeli eklemek yerine varolan OLE DB Nesne modeli destekler. OLE DB Tüketici Şablonları üst düzey sınıflar OLE DB belirtiminde tanımlanan bileşenleri paralel. OLE DB Tüketici Şablonları tasarım üzerinde bir satır kümesinde çoklu erişimci gibi gelişmiş özellikler içeriyor. Şablonları ve birden çok devralma kullanımını kitaplığı küçük ve esnek hale getirir.  
  
## <a name="how-ole-db-consumers-access-data"></a>OLE DB tüketicileri veri nasıl erişim  
 Tüketiciler, aşağıdaki konularda açıklanan nesneleri çeşitli türlerde kullanın:  
  
-   [Veri Kaynakları ve Oturumlar](../../data/oledb/data-sources-and-sessions.md)  
  
-   [Erişimciler ve Satır Kümeleri](../../data/oledb/accessors-and-rowsets.md)  
  
-   [Komutlar ve Tablolar](../../data/oledb/commands-and-tables.md)  
  
-   [Kullanıcı Kayıtları](../../data/oledb/user-records.md)  
  
 Tüketici bir şey yapmadan önce ilk (örneğin, SQL, Oracle, ODBC ve MSDS) erişmesi gereken veritabanı türü için uygun bir OLE DB sağlayıcısı seçin. Bunu yapmak için genellikle bir numaralandırıcı kullanır (bkz [CEnumerator](../../data/oledb/cenumerator-class.md) bölümünde belirtildiği gibi [veri kaynakları ve oturumlar](../../data/oledb/data-sources-and-sessions.md)).  
  
 [Veri kaynağı nesnesi](../../data/oledb/data-sources-and-sessions.md) seçtiğiniz veri kaynağına bağlanmak için gerekli bağlantı bilgileri sağlar. Veri kaynağı nesnesi kullanıcılara veri kaynağına erişim izni vermek için kullanılan kimlik bilgileri (örneğin, oturum açma adları ve parolalar) de içerir. Veri kaynağı nesnesi veritabanına bir bağlantı kurar ve bir veya daha fazla oturum nesneleri oluşturur. Her [oturum nesnesi](../../data/oledb/data-sources-and-sessions.md) (diğer bir deyişle, sorgulama ve veri alma) veritabanı ile kendi etkileşimlerini yönetir ve diğer oturumlarına bağımsız olarak bu işlemleri gerçekleştirir.  
  
 Oturum satır kümesi ve komut nesneleri oluşturur. [Komut nesnesi](../../data/oledb/commands-and-tables.md) SQL komutlarını kullanarak veritabanı ile Örneğin, etkileşime girmesine izin verir. [Satır kümesi nesnesi](../../data/oledb/accessors-and-rowsets.md) hangi edebilir ve hangi gidebilirsiniz aracılığıyla veri kümesi [güncelleştirme, silme ve Satır Ekle](../../data/oledb/updating-rowsets.md).  
  
 Bir OLE DB Tüketicisi sütunları yerel değişken içeren veritabanı tablolarındaki bağlar; Bunu yapmak için kullandığı bir [erişimci](../../data/oledb/accessors-and-rowsets.md), veri tüketici içinde nasıl depolandığını bir harita içerir. Harita tablo sütunları ve tüketici uygulamasındaki yerel arabellekler (değişkenler) arasında bağlamaları kümesinden oluşur.  
  
 Tüketicileri ile çalışırken önemli bir kavram biri iki sınıf bir tüketici bildirin: [komutu (veya tablo) sınıfı](../../data/oledb/commands-and-tables.md) ve [kullanıcı kayıt sınıfı](../../data/oledb/user-records.md). Satır kümesi erişimci sınıfından hem satır kümesi sınıfından devralan komut (veya tablo) sınıfı aracılığıyla erişebilirsiniz. Kullanıcı kayıt sınıfı daha önce açıklanan satır kümesi bağlama eşlemesi içerir.  
  
 Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer.md)  
  
-   [OLE DB Tüketici senaryoları (örnekler)](../../data/oledb/working-with-ole-db-consumer-templates.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB programlama](../../data/oledb/ole-db-programming.md)   
 [Veri erişimi](../data-access-in-cpp.md)   
 [OLE DB SDK Belgeleri](https://msdn.microsoft.com/en-us/library/ms722784.aspx)   
 [OLE DB Programcının Başvurusu](https://msdn.microsoft.com/en-us/library/ms713643.aspx)