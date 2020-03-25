---
title: OLE DB Tüketici Şablonları Başvurusu
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
ms.openlocfilehash: 13805ab1dc2c2b4792fd05c9140006c610b42f75
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210112"
---
# <a name="ole-db-consumer-templates-reference"></a>OLE DB Tüketici Şablonları Başvurusu

OLE DB tüketici şablonları aşağıdaki sınıfları içerir. Başvuru malzemesi, [OLE DB tüketici şablonlarının makroları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)hakkındaki konuları da içerir.

## <a name="session-classes"></a>Oturum sınıfları

[CDataConnection](../../data/oledb/cdataconnection-class.md)<br/>
Veri kaynağıyla bağlantıyı yönetir. Bu, gerekli nesneleri (veri kaynağı ve oturumu) ve bir veri kaynağına bağlanırken yapmanız gereken bazı işleri (veri kaynağı ve oturum) ve bir kısmını kapsülleyen istemciler oluşturmak için yararlı bir sınıftır.

[CDataSource](../../data/oledb/cdatasource-class.md)<br/>
Bir sağlayıcının veri kaynağına bir bağlantıyı temsil eden bir OLE DB veri kaynağı nesnesine karşılık gelir. Her biri bir `CSession` nesnesi tarafından temsil edilen bir veya daha fazla veritabanı oturumu tek bir bağlantıda gerçekleşebilir.

[CEnumerator](../../data/oledb/cenumerator-class.md)<br/>
Kullanılabilir veri kaynakları hakkında satır kümesi bilgilerini alan OLE DB Numaralandırıcı nesnesine karşılık gelir.

[CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)<br/>
`CEnumerator` tarafından, Numaralandırıcı satır kümesinden veriye erişmek için kullanılır. Bu satır kümesi, geçerli Numaralandırıcı tarafından görünen veri kaynaklarından ve numaralandırıcılardan oluşur.

[CSession](../../data/oledb/csession-class.md)<br/>
Tek bir veritabanı erişim oturumunu temsil eder. Bir veya daha fazla oturum, her bir `CDataSource` nesnesiyle ilişkilendirilebilir.

## <a name="accessor-classes"></a>Erişimci sınıfları

[CAccessor](../../data/oledb/caccessor-class.md)<br/>
Statik olarak bir veri kaynağına bağlanan kayıtlar için kullanılır. Veri kaynağının yapısını bildiğiniz zaman bu erişimci sınıfını kullanın.

[CAccessorBase](../../data/oledb/caccessorbase-class.md)<br/>
Tüm erişimci sınıfları için temel sınıf.

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
Satır kümesinin sütun bilgilerine göre çalışma zamanında oluşturulabilen bir erişimci. Veri kaynağının yapısını bilemezsiniz, verileri almak için bu sınıfı kullanın.

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
Komut türleri bilinmiyorsa kullanılabilecek bir erişimci. Sağlayıcı arabirimi destekliyorsa `ICommandWithParameters` arabirimini çağırarak parametre bilgilerini edinir.

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
Veritabanının temel yapısı hakkında bilginiz yoksa bir veri kaynağına erişmenizi sağlar.

[CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
`CDynamicStringAccessor` benzer şekilde, bu sınıf veri deposundan ANSI dize verileri olarak erişilen verileri ister.

[CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
`CDynamicStringAccessor` benzer şekilde, bu sınıfın veri deposundan UNICODE dize verileri olarak erişilen verileri istemesi hariç.

[CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
Hem sütunları hem de komut parametrelerini işlemek için yöntemlere sahip bir erişimci. Bu sınıf ile, sağlayıcı türü dönüştürebileceğiniz sürece herhangi bir veri türünü kullanabilirsiniz.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
, Sınıfın parametreleri veya çıkış sütunlarını desteklemesini istemediğiniz durumlarda şablon bağımsız değişkeni olarak kullanılabilir.

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)<br/>
`CDynamicStringAccessor` benzer şekilde, bu sınıf veri deposundan erişilen tüm verileri XML biçimli (etiketli) veriler olarak dönüştürür.

## <a name="rowset-classes"></a>Satır kümesi sınıfları

[CAccessorRowset](../../data/oledb/caccessorrowset-class.md)<br/>
Bir satır kümesini ve onunla ilişkili erişimcileri kapsüller.

[CArrayRowset](../../data/oledb/carrayrowset-class.md)<br/>
Dizi sözdizimini kullanarak bir satır kümesinin öğelerine erişmek için kullanılır.

[CBulkRowset](../../data/oledb/cbulkrowset-class.md)<br/>
Tek bir çağrıda birden çok satır tanıtıcısı alarak satırları toplu olarak getirmek ve işlemek için kullanılır.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
Komut bir satır kümesi döndürmezse, şablon bağımsız değişkeni olarak kullanılabilir.

[CRestrictions](../../data/oledb/crestrictions-class.md)<br/>
Şema satır kümelerine yönelik kısıtlamaları belirtmek için kullanılır.

[CRowset](../../data/oledb/crowset-class.md)<br/>
Satır kümesi verilerini işlemek, ayarlamak ve almak için kullanılır.

[CStreamRowset](../../data/oledb/cstreamrowset-class.md)<br/>
Satır kümesi yerine bir `ISequentialStream` nesnesi döndürür; sonra verileri XML biçiminde almak için `Read` yöntemini kullanırsınız. (SQL Server 2000 biçimlendirme yapar; bu özelliğin yalnızca SQL Server 2000 ile birlikte çalışıp çalışmadığını unutmayın.)

[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)<br/>
`IRowsetNotify` yöntemleri `OnFieldChange`, `OnRowChange`ve `OnRowsetChange`için boş işlevlerle `IRowsetNotify`için kukla bir uygulama sağlar.

[Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)

OLE DB şablonları, size OLE DB şema satır kümelerine karşılık gelen bir sınıf kümesi sağlar.

## <a name="command-classes"></a>Komut sınıfları

[CCommand](../../data/oledb/ccommand-class.md)<br/>
Parametre tabanlı OLE DB komutu ayarlamak ve yürütmek için kullanılır. Basit bir satır kümesini yalnızca açmak için, bunun yerine `CTable` kullanın.

[CMultipleResults](../../data/oledb/cmultipleresults-class.md)<br/>
Komutun birden çok sonuç kümesini işlemesini istediğinizde `CCommand` şablonu için şablon bağımsız değişkeni olarak kullanılır.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
Bir erişimci sınıfı bağımsız değişkeni alan `CCommand` ve `CTable`gibi şablon sınıfları için şablon bağımsız değişkeni olarak kullanılır. Sınıfın parametreleri veya çıkış sütunlarını desteklemesini istemiyorsanız `CNoAccessor` kullanın.

[CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)<br/>
Komutun tek bir satır kümesini işlemesini istediğinizde `CCommand` şablonu için şablon bağımsız değişkeni olarak kullanılır. `CNoMultipleResults`, şablon bağımsız değişkeni için varsayılan değerdir.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
Komut veya tablo bir satır kümesi döndürmezse `CCommand` veya `CTable` için şablon bağımsız değişkeni olarak kullanılır.

[Rmt](../../data/oledb/ctable-class.md)<br/>
Parametresiz basit bir satır kümesine erişmek için kullanılır.

## <a name="property-classes"></a>Özellik sınıfları

[CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)<br/>
Tüketicinin Özellik bilgilerini istediği özellik kimliklerinin dizisini geçirmek için kullanılır. Özellikler bir özellik kümesine aittir.

[CDBPropSet](../../data/oledb/cdbpropset-class.md)<br/>
Bir sağlayıcıdaki özellikleri ayarlamak için kullanılır.

## <a name="bookmark-class"></a>Bookmark sınıfı

[CBookmark](../../data/oledb/cbookmark-class.md)<br/>
Bir satır kümesindeki verilere erişmek için dizin olarak kullanılır.

## <a name="error-class"></a>Hata sınıfı

[CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)<br/>
OLE DB hata bilgilerini almak için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonları Başvurusu](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB Şablonları](../../data/oledb/ole-db-templates.md)
