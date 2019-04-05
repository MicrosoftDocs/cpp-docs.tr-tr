---
title: OLE DB Tüketici Şablonları Başvurusu
ms.date: 11/04/2016
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc.templates.ole
- vc-attr.db_source
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
ms.openlocfilehash: fb0b24798b3f2682bbbec7624df34b40a2a9f4cc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032277"
---
# <a name="ole-db-consumer-templates-reference"></a>OLE DB Tüketici Şablonları Başvurusu

OLE DB Tüketici şablonları aşağıdaki sınıfları içerir. Başvuru malzemesi üzerinde konuları da içerir. [OLE DB Tüketici Şablonları için makrolar](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

## <a name="session-classes"></a>Oturum sınıfı

[CDataConnection](../../data/oledb/cdataconnection-class.md)<br/>
Veri kaynağı ile bağlantı yönetir. Bu gerekli nesneleri (veri kaynağı ve oturum) ve bir veri kaynağına bağlanırken gerçekleştirmeniz gereken işinin bir kısmını kapsülleyen çünkü istemciler oluşturan için kullanışlı bir sınıftır.

[CDataSource](../../data/oledb/cdatasource-class.md)<br/>
Bir veri kaynağına bağlantı sağlayıcısı üzerinden temsil eden bir OLE DB veri kaynağı nesnesinin karşılık gelir. Bir veya daha fazla veritabanı oturumları, tarafından gösterilen her bir `CSession` nesne, tek bir bağlantı üzerinde gerçekleştirilebilir.

[CEnumerator](../../data/oledb/cenumerator-class.md)<br/>
Kullanılabilir veri kaynakları hakkında daha fazla satır kümesi bilgileri alır bir OLE DB sabit listesi nesnesi karşılık gelir.

[CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)<br/>
Tarafından kullanılan `CEnumerator` Numaralandırıcı satır kümesinden verilere erişmek için. Bu satır kümesi veri kaynakları ve geçerli Numaralandırıcının görünür numaralandırıcılar oluşur.

[CSession](../../data/oledb/csession-class.md)<br/>
Bir tek veritabanı erişim oturumu temsil eder. Bir veya daha fazla oturum ilişkilendirilebilir her `CDataSource` nesne.

## <a name="accessor-classes"></a>Erişimci sınıfları

[CAccessor](../../data/oledb/caccessor-class.md)<br/>
Statik olarak bağlı bir veri kaynağına kayıtlar için kullanılır. Veri kaynağının yapısını bildiğinizde bu erişimci sınıfı kullanın.

[CAccessorBase](../../data/oledb/caccessorbase-class.md)<br/>
Tüm erişimci sınıflar için temel sınıf.

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
Satır kümesi sütunu bilgilere göre çalışma zamanında oluşturulabilir erişimci. Bu sınıf, veri kaynağının yapısını bilmiyorsanız, veri almak için kullanın.

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
Komut türü bilinmeyen olduğunda kullanılabilecek bir erişimcisi. Çağırarak parametre bilgilerini alır `ICommandWithParameters` sağlayıcı arabirimi destekliyor, arabirim.

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
Temel alınan veritabanı yapısı bilgisi varsa, bir veri kaynağına erişim sağlar.

[CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
Benzer şekilde `CDynamicStringAccessor` dışında bu sınıf ANSI dize verileri veri deposundan erişilen verileri ister.

[CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
Benzer şekilde `CDynamicStringAccessor` dışında bu sınıf UNICODE dize verileri veri deposundan erişilen verileri ister.

[CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
Hem sütunları hem de komut parametreleri işlemek için bir erişimci yöntemlerini. Bu sınıf ile sağlayıcı türüne dönüştürebilirsiniz sürece herhangi bir veri türü kullanabilirsiniz.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
Parametrelerini veya sütunlarını çıkış desteklemeye sınıfı istemediğinizde, şablon bağımsız değişkeni kullanılabilir.

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)<br/>
Benzer şekilde `CDynamicStringAccessor` dışında bu sınıfın XML biçimli (etiketli) veri veri deposundan erişilen tüm verileri dönüştürür.

## <a name="rowset-classes"></a>Satır kümesi sınıfları

[CAccessorRowset](../../data/oledb/caccessorrowset-class.md)<br/>
Bir satır kümesi ve ilişkili erişimcilerini kapsüller.

[CArrayRowset](../../data/oledb/carrayrowset-class.md)<br/>
Dizi söz dizimini kullanarak bir satır kümesi öğelere erişmek için kullanılır.

[CBulkRowset](../../data/oledb/cbulkrowset-class.md)<br/>
Getirme ve tek bir çağrı ile birden çok satır işleyicilerini alarak toplu satırları yönlendirme için kullanılır.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
Komut satır döndürmezse, şablon bağımsız değişkeni kullanılabilir.

[cRestrictions](../../data/oledb/crestrictions-class.md)<br/>
Şema satır kümeleri için kısıtlamaları belirtmek için kullanılır.

[CRowset](../../data/oledb/crowset-class.md)<br/>
Satır kümesi veri işleme ve ayarlamak için kullanılır.

[CStreamRowset](../../data/oledb/cstreamrowset-class.md)<br/>
Döndürür bir `ISequentialStream` yerine bir satır kümesi nesnesi; ardından `Read` XML biçiminde veri almak için yöntemi. (SQL Server 2000 biçimlendirme yapar; bu özellik yalnızca SQL Server 2000 ile çalıştığını unutmayın.)

[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)<br/>
İşlevsiz bir uygulamasını sağlar `IRowsetNotify`, için boş işlevlerle `IRowsetNotify` yöntemleri `OnFieldChange`, `OnRowChange`, ve `OnRowsetChange`.

[Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)

OLE DB Şablonları, OLE DB şema satır kümeleri karşılık gelen sınıf kümesi sağlar.

## <a name="command-classes"></a>Komut sınıfları

[CCommand](../../data/oledb/ccommand-class.md)<br/>
Ayarlayın ve parametre tabanlı bir OLE DB komutu yürütmek için kullanılır. Yalnızca basit bir satır kümesinde'ni açmak için kullanmak `CTable` yerine.

[CMultipleResults](../../data/oledb/cmultipleresults-class.md)<br/>
Bir şablon bağımsız değişken olarak kullanılan `CCommand` birden çok sonuç kümesi işlemek için komutu istediğinizde şablonu.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
Şablon sınıfları için bir şablon bağımsız değişkeni olarak gibi kullanılan `CCommand` ve `CTable`, süren bir erişimci sınıfında bağımsız değişken. Kullanım `CNoAccessor` parametrelerini veya sütunlarını çıkış desteklemeye sınıfı istemiyorsanız.

[CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)<br/>
Bir şablon bağımsız değişken olarak kullanılan `CCommand` komutu tek bir satır kümesi işlemek istediğinizde şablonu. `CNoMultipleResults` Şablon bağımsız değişkeni için varsayılan değerdir.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
Bir şablon bağımsız değişken olarak kullanılan `CCommand` veya `CTable` komut veya tablo satır döndürmezse.

[CTable](../../data/oledb/ctable-class.md)<br/>
Basit bir satır kümesinde parametresiz erişmek için kullanılır.

## <a name="property-classes"></a>Özellik sınıfları

[Cdbpropıdset](../../data/oledb/cdbpropidset-class.md)<br/>
Bir dizi özellik kimlikleri için özellik bilgilerini tüketici istediği geçirmek için kullanılır. Özellikleri bir özellik kümesine ait değil.

[CDBPropSet](../../data/oledb/cdbpropset-class.md)<br/>
Bir sağlayıcısında özelliklerini ayarlamak için kullanılır.

## <a name="bookmark-class"></a>Yer işareti sınıfı

[CBookmark](../../data/oledb/cbookmark-class.md)<br/>
Bir satır kümesi veri erişimi için bir dizin olarak kullanılır.

## <a name="error-class"></a>Hata sınıfı

[Cdberrorınfo](../../data/oledb/cdberrorinfo-class.md)<br/>
OLE DB hata bilgilerini almak için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonları Başvurusu](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB Şablonları](../../data/oledb/ole-db-templates.md)