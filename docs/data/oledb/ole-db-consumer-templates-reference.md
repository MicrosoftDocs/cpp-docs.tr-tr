---
description: 'Hakkında daha fazla bilgi edinin: OLE DB tüketici şablonları başvurusu'
title: OLE DB Tüketici Şablonları Başvurusu
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
ms.openlocfilehash: e904237a7fbdef84c5f7f902ba352301a608b544
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286962"
---
# <a name="ole-db-consumer-templates-reference"></a>OLE DB Tüketici Şablonları Başvurusu

OLE DB tüketici şablonları aşağıdaki sınıfları içerir. Başvuru malzemesi, [OLE DB tüketici şablonlarının makroları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)hakkındaki konuları da içerir.

## <a name="session-classes"></a>Oturum sınıfları

[CDataConnection](../../data/oledb/cdataconnection-class.md)<br/>
Veri kaynağıyla bağlantıyı yönetir. Bu, gerekli nesneleri (veri kaynağı ve oturumu) ve bir veri kaynağına bağlanırken yapmanız gereken bazı işleri (veri kaynağı ve oturum) ve bir kısmını kapsülleyen istemciler oluşturmak için yararlı bir sınıftır.

[CDataSource](../../data/oledb/cdatasource-class.md)<br/>
Bir sağlayıcının veri kaynağına bir bağlantıyı temsil eden bir OLE DB veri kaynağı nesnesine karşılık gelir. Her biri bir nesne tarafından temsil edilen bir veya daha fazla veritabanı oturumu `CSession` tek bir bağlantıda gerçekleşebilir.

[CEnumerator](../../data/oledb/cenumerator-class.md)<br/>
Kullanılabilir veri kaynakları hakkında satır kümesi bilgilerini alan OLE DB Numaralandırıcı nesnesine karşılık gelir.

[CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)<br/>
`CEnumerator`Numaralandırıcı satır kümesinden veriye erişmek için tarafından kullanılır. Bu satır kümesi, geçerli Numaralandırıcı tarafından görünen veri kaynaklarından ve numaralandırıcılardan oluşur.

[CSession](../../data/oledb/csession-class.md)<br/>
Tek bir veritabanı erişim oturumunu temsil eder. Bir veya daha fazla oturum, her nesneyle ilişkilendirilebilir `CDataSource` .

## <a name="accessor-classes"></a>Erişimci sınıfları

[CAccessor](../../data/oledb/caccessor-class.md)<br/>
Statik olarak bir veri kaynağına bağlanan kayıtlar için kullanılır. Veri kaynağının yapısını bildiğiniz zaman bu erişimci sınıfını kullanın.

[CAccessorBase](../../data/oledb/caccessorbase-class.md)<br/>
Tüm erişimci sınıfları için temel sınıf.

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
Satır kümesinin sütun bilgilerine göre çalışma zamanında oluşturulabilen bir erişimci. Veri kaynağının yapısını bilemezsiniz, verileri almak için bu sınıfı kullanın.

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
Komut türleri bilinmiyorsa kullanılabilecek bir erişimci. `ICommandWithParameters`Sağlayıcı arabirimi destekliyorsa, arabirimi çağırarak parametre bilgilerini alır.

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
Veritabanının temel yapısı hakkında bilginiz yoksa bir veri kaynağına erişmenizi sağlar.

[CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
`CDynamicStringAccessor`Bu sınıfın, veri DEPOSUNDAN ANSI dize verileri olarak erişilen verileri istemesi hariç ile benzerdir.

[CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
`CDynamicStringAccessor`Bu sınıfın, veri DEPOSUNDAN UNICODE dize verileri olarak erişilen verileri istemesi hariç ile benzerdir.

[CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
Hem sütunları hem de komut parametrelerini işlemek için yöntemlere sahip bir erişimci. Bu sınıf ile, sağlayıcı türü dönüştürebileceğiniz sürece herhangi bir veri türünü kullanabilirsiniz.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
, Sınıfın parametreleri veya çıkış sütunlarını desteklemesini istemediğiniz durumlarda şablon bağımsız değişkeni olarak kullanılabilir.

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)<br/>
İle benzerdir `CDynamicStringAccessor` , bu sınıf, veri deposundan erişilen tüm VERILERI XML biçimli (etiketli) veriler olarak dönüştürür.

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
`ISequentialStream`Satır kümesi yerine bir nesne döndürür; ardından, `Read` XML biçimindeki verileri almak için yöntemini kullanın. (SQL Server 2000 biçimlendirme yapar; bu özelliğin yalnızca SQL Server 2000 ile birlikte çalışıp çalışmadığını unutmayın.)

[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)<br/>
, `IRowsetNotify` Ve yöntemleri için boş işlevlerle, için kukla bir uygulama `IRowsetNotify` sağlar `OnFieldChange` `OnRowChange` `OnRowsetChange` .

[Şema satır kümesi sınıfları ve typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)

OLE DB şablonları, size OLE DB şema satır kümelerine karşılık gelen bir sınıf kümesi sağlar.

## <a name="command-classes"></a>Komut sınıfları

[CCommand](../../data/oledb/ccommand-class.md)<br/>
Parametre tabanlı OLE DB komutu ayarlamak ve yürütmek için kullanılır. Yalnızca basit bir satır kümesini açmak için `CTable` yerine kullanın.

[CMultipleResults](../../data/oledb/cmultipleresults-class.md)<br/>
`CCommand`Komutun birden çok sonuç kümesini işlemesini istediğinizde şablon için şablon bağımsız değişkeni olarak kullanılır.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
, Ve gibi bir `CCommand` `CTable` erişimci sınıfı bağımsız değişkeni alan şablon sınıfları için şablon bağımsız değişkeni olarak kullanılır. `CNoAccessor`Sınıfın parametreleri veya çıkış sütunlarını desteklemesini istemiyorsanız kullanın.

[CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)<br/>
`CCommand`Komutun tek bir satır kümesini işlemesini istediğinizde şablon için şablon bağımsız değişkeni olarak kullanılır. `CNoMultipleResults` , şablon bağımsız değişkeni için varsayılan değerdir.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
`CCommand` `CTable` Komut veya tablo bir satır kümesi döndürmezse veya için şablon bağımsız değişkeni olarak kullanılır.

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

[OLE DB sağlayıcı şablonları başvurusu](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB şablonları](../../data/oledb/ole-db-templates.md)
