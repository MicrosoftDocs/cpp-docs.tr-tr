---
title: "OLE DB Tüketici Şablonları başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc.templates.ole
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 29f833f6a598b9028506fb11d163be49212bd998
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-consumer-templates-reference"></a>OLE DB Tüketici Şablonları Başvurusu
OLE DB Tüketici şablonları aşağıdaki sınıflar içerir. Başvuru malzemesinde üzerinde konuları da içerir. [OLE DB Tüketici Şablonları için makrolar](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## <a name="session-classes"></a>Oturum sınıfı  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 Veri kaynağı ile bağlantı yönetir. Bu gerekli nesneleri (veri kaynağı ve oturum) ve bir veri kaynağına bağlanırken gerçekleştirmeniz gereken iş bazıları yalıtır çünkü istemciler oluşturmak için yararlı bir sınıftır.  
  
 [CDataSource](../../data/oledb/cdatasource-class.md)  
 Bir veri kaynağına bağlantı sağlayıcısı üzerinden temsil eden bir OLE DB veri kaynağı nesnesi karşılık gelir. Bir veya daha fazla veritabanı oturumları, tarafından gösterilen her bir `CSession` nesne, tek bir bağlantı üzerinde yer alabilir.  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 Kullanılabilir veri kaynakları ile ilgili satır kümesi bilgilerini alır bir OLE DB Numaralandırıcı nesne karşılık gelir.  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 Tarafından kullanılan `CEnumerator` Numaralandırıcı satır kümesinden verilere erişmek için. Bu satır kümesi veri kaynakları ve numaralandırmalar geçerli Numaralandırıcının görünür oluşur.  
  
 [CSession](../../data/oledb/csession-class.md)  
 Tek veritabanı erişim oturumu temsil eder. Bir veya daha fazla oturum ilişkilendirilebilir her `CDataSource` nesnesi.  
  
## <a name="accessor-classes"></a>Erişimci sınıfları  
 [CAccessor](../../data/oledb/caccessor-class.md)  
 Statik olarak bir veri kaynağına bağlı kayıtlar için kullanılır. Veri kaynağının yapısı bildiğiniz durumlarda bu erişimci sınıfı kullanın.  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 Tüm erişimcisi sınıflar için temel sınıf.  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 Çalışma zamanında satır kümesi sütunu bilgilere göre oluşturulabilmesi için bir erişimci. Bu sınıf, veri kaynağının yapısını bilmiyorsanız veri almak için kullanın.  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 Komut türleri bilinmeyen olduğunda kullanılabilmesi için bir erişimci. Parametre bilgileri çağırarak alır `ICommandWithParameters` sağlayıcı arabirimi destekliyorsa, arabirim.  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 Veritabanı yapılarını hiçbir bilgiye sahip olduğunda bir veri kaynağına erişim sağlar.  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 Benzer şekilde `CDynamicStringAccessor` dışında bu sınıfın ANSI dize veri olarak veri deposundan erişilen verileri ister.  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 Benzer şekilde `CDynamicStringAccessor` dışında bu sınıfın UNICODE dize veri olarak veri deposundan erişilen verileri ister.  
  
 [CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  
 Sütunları ve komut parametrelerini işlemek için bir erişimci yöntemleri. Bu sınıf ile sağlayıcı türü dönüştürebilirsiniz sürece herhangi bir veri türünün kullanabilirsiniz.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Parametreleri desteklemiyor veya sütunların çıktısı için sınıf istemediğinizde şablon bağımsız değişken kullanılabilir.  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 Benzer şekilde `CDynamicStringAccessor` dışında bu sınıfın tüm verileri XML biçimli (etiketli) veri olarak veri deposundan erişilen dönüştürür.  
  
## <a name="rowset-classes"></a>Satır kümesi sınıfları  
 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)  
 Bir satır kümesi ve onun ilişkili erişimciler yalıtır.  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 Array sözdizimini kullanarak bir satır kümesi öğeleri erişmek için kullanılır.  
  
 [CBulkRowset](../../data/oledb/cbulkrowset-class.md)  
 Fetch ve tek bir çağrı ile birden çok satır işleyicilerini alarak satırları toplu işlemek için kullanılır.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Komut bir satır kümesi döndürmezse şablon bağımsız değişken kullanılabilir.  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md)  
 Şema satır kümeleri için kısıtlamaları belirtmek için kullanılır.  
  
 [CRowset](../../data/oledb/crowset-class.md)  
 İşlemek için kullanılan, ayarlayın ve satır kümesi veri alın.  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 Döndürür bir `ISequentialStream` sonra kullanın; nesnesi bir satır kümesi yerine **okuma** XML biçiminde veri alma yöntemi. (SQL Server 2000 biçimlendirme yapar; bu özellik yalnızca SQL Server 2000 ile çalıştığını unutmayın.)  
  
 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)  
 Sahte bir uygulamasını sağlar `IRowsetNotify`, boş işlevleri için ile `IRowsetNotify` yöntemleri `OnFieldChange`, `OnRowChange`, ve `OnRowsetChange`.  
  
 [Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)  
  
 OLE DB Şablonları, OLE DB şema satır kümeleri için karşılık gelen sınıf kümesi sağlar.  
  
## <a name="command-classes"></a>Komut sınıfları  
 [CCommand](../../data/oledb/ccommand-class.md)  
 Ayarlama ve bir parametre tabanlı OLE DB komutu yürütmek için kullanılır. Yalnızca basit bir satır kümesinde açmak için kullanmak `CTable` yerine.  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 Bir şablon bağımsız değişken olarak kullanılan `CCommand` birden çok sonuç kümesi işlemek için komutu istediğinizde şablonu.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Şablon sınıfları için bir şablon bağımsız değişken olarak gibi kullanılan `CCommand` ve `CTable`, Süren erişimci sınıfı bağımsız değişken. Kullanım `CNoAccessor` parametrelerini desteklemek veya sütunların çıktısı için sınıf istemiyorsanız.  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 Bir şablon bağımsız değişken olarak kullanılan `CCommand` tek bir satır kümesi işlemek için komutu istediğinizde şablonu. `CNoMultipleResults` Şablon bağımsız değişken için varsayılan değerdir.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Bir şablon bağımsız değişken olarak kullanılan `CCommand` veya `CTable` komut veya tablo bir satır kümesi döndürmezse.  
  
 [CTable](../../data/oledb/ctable-class.md)  
 Hiçbir parametre basit bir satır kümesinde erişmek için kullanılır.  
  
## <a name="property-classes"></a>Özelliği sınıfları  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 Bir dizi özellik kimlikleri için özellik bilgilerini tüketici istediği iletmek için kullanılır. Özellikler bir özellik kümesine ait.  
  
 [CDBPropSet](../../data/oledb/cdbpropset-class.md)  
 Bir sağlayıcısında özelliklerini ayarlamak için kullanılır.  
  
## <a name="bookmark-class"></a>Yer işareti sınıfı  
 [CBookmark](../../data/oledb/cbookmark-class.md)  
 Bir dizini olarak bir satır kümesi veri erişimi için kullanılır.  
  
## <a name="error-class"></a>Hata sınıfı  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 OLE DB hata bilgilerini almak için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları başvurusu](../../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB Şablonları](../../data/oledb/ole-db-templates.md)