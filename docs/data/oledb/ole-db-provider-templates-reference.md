---
title: OLE DB Sağlayıcı Şablonları Başvurusu
ms.date: 11/04/2016
f1_keywords:
- vc.templates.ole
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
ms.openlocfilehash: 4c89d22cc66937ef9e10636bec79e2cf8b7de43c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501330"
---
# <a name="ole-db-provider-templates-reference"></a>OLE DB Sağlayıcı Şablonları Başvurusu

OLE DB sağlayıcı şablonlarının sınıfları ve arabirimleri aşağıdaki kategorilerde gruplandırılabilir. Başvuru malzemesi Ayrıca [OLE DB sağlayıcı şablonlarının makroları](../../data/oledb/macros-for-ole-db-provider-templates.md)hakkında bilgiler içerir.

Sınıflar aşağıdaki adlandırma kuralını kullanır: düzeniyle `IWidgetImpl` adlandırılmış bir sınıf, arabirimin `IWidget`bir uygulamasını sağlar.

## <a name="session-classes"></a>Oturum sınıfları

[IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)<br/>
Veri kaynağı nesnesinden yeni bir oturum oluşturur ve yeni oluşturulan oturumdaki istenen arabirimi döndürür. Veri kaynağı nesnelerinde zorunlu arabirim.

[ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)<br/>
Özellik kümesi eşlemesi tarafından tanımlanan statik bir işlevi çağırarak oturum özelliklerini uygular. Özellik kümesi eşlemesi, oturum sınıfınıza belirtilmelidir. Oturumlardaki zorunlu arabirim.

## <a name="rowset-classes"></a>Satır kümesi sınıfları

[CRowsetImpl](../../data/oledb/crowsetimpl-class.md)

Birçok uygulama arabiriminin birden çok devralınması gerekmeden standart bir OLE DB satır kümesi uygulamasını sağlar. Uygulama sağlamanız gereken tek yöntem `Execute`.

[CSimpleRow](../../data/oledb/csimplerow-class.md)<br/>
, `IRowsetImpl` Sınıfında kullanılan satır tanıtıcısı için varsayılan bir uygulama sağlar. Satır tanıtıcısı, bir sonuç satırı için mantıksal olarak benzersiz bir etikettir. `IRowsetImpl``CSimpleRow` içinde`IRowsetImpl::GetNextRows`istenen her satır için yeni bir oluşturur.

[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)<br/>
OLE DB `HACCESSOR`, sağlayıcıların bir `DBBINDING` yapı dizisine bir etiket olan öğesine uygulanmasını gerektirir. `HACCESSOR` ,`BindType` Yapıların adresleri olan öğeleri sağlar. Satır kümelerinde ve komutlarda zorunludur.

[IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)<br/>
Sağlayıcı sütun eşlemesi tarafından tanımlanan statik bir işleve temsilciler. Satır kümelerinde ve komutlarda zorunlu arabirim.

[IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)<br/>
Bir komutta veya bir satır kümesinde tür dönüştürmelerinden oluşan kullanılabilirlik hakkında bilgi verir. Komutlarda, satır kümelerinde ve Dizin satır kümelerinde zorunlu. OLE DB tarafından sağlanan dönüştürme nesnesine temsilci seçerek arabirimiuygular.`IConvertType`

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)<br/>
Arabirimini ve şablonlaştırılmış oluşturucu işlevini `CreateSchemaRowset`uygular. `IDBSchemaRowset`

[IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)<br/>
' İ açar ve tek bir temel tablodan veya dizindeki tüm satırları içeren bir satır kümesi döndürür. Bir oturum nesnesi için zorunlu arabirim.

[IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)<br/>
Mevcut satırlardaki sütunların değerlerinin güncelleştirilmesini sağlayan, satırları silen ve yeni satırlar eklenen OLE DB [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) arabirimini uygular.

[IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)<br/>
Bu sınıf, [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) 'dan devralınır ve [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)geçersiz kılınır. `IRowsetCreatorImpl`aynı işlevleri `IObjectWithSite` gerçekleştirir, ancak OLE DB özelliklerini `DBPROPCANSCROLLBACKWARDS` ve `DBPROPCANFETCHBACKWARDS`öğesini de sunar.

[IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)<br/>
İki satırlık verilerin aynı olup olmadığını karşılaştırmanıza olanak tanıyan arabiriminiuygular.`IRowsetIdentity`

[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)<br/>
Temel satır kümesi arabirimi olan `IRowset` arabirimin bir uygulamasını sağlar.

[IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)<br/>
Komut sınıfınıza tanımlanan özellik kümesi eşlemesini kullanarak satır kümesi özelliklerini uygular. Satır kümelerinde zorunlu arabirim.

[IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)<br/>
Bir satır kümesinden rastgele satırlar getiren OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) arabirimini uygular. Bir satır kümesinde OLE DB yer işaretlerini desteklemek için, satır kümesinin bu sınıftan devralmasını sağlayın.

[IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)<br/>
, Satır kümesinin içeriğinde yapılan değişikliklerin bağlantı noktasındaki `IID_IRowsetNotify` dinleyicileri bildirmek için yayın işlevlerini uygular. Bildirimleri işleyen tüketiciler, [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) uygular ve bu bağlantı noktasına kaydeder.

[IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)<br/>
, Tüketicilerin veri kaynağına yönelik [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) ile yapılan değişikliklerin aktarımını geciktirmesini ve iletimden önce değişiklikleri geri almasını sağlayan OLE DB [IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) arabirimini uygular.

## <a name="command-classes"></a>Komut sınıfları

[ICommandImpl](../../data/oledb/icommandimpl-class.md)<br/>
`ICommand` Arabirimin bir uygulamasını sağlar. Bu arabirim görünür değildir, ancak tarafından `ICommandTextImpl`işlenir. Komut nesnesinde zorunlu arabirim.

[ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)<br/>
Bu `ICommandProperties` arabirimin uygulanması, `BEGIN_PROPSET_MAP` makro tarafından tanımlanan statik bir işlev tarafından sağlanır. Komutlarınız zorunludur.

[ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)<br/>
Komut metnini ayarlar, depolar ve döndürür. Komutlarınız zorunludur.

[IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)<br/>
Oturum nesnesinden yeni bir komut oluşturur ve yeni oluşturulan komutta istenen arabirimi döndürür. Oturum nesnelerinde isteğe bağlı arabirim.

Diğer komut sınıfları `IColumnsInfoImpl` ve `IAccessorImpl`, yukarıdaki satır kümesi sınıfları bölümünde açıklanmıştır.

## <a name="data-source-classes"></a>Veri kaynağı sınıfları

[IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)<br/>
Tüketiciyle bağlantı oluşturur ve siler. Veri kaynağı nesnelerinde zorunlu arabirim ve numaralandırıcılara yönelik isteğe bağlı arabirim.

[IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)<br/>
`IDBProperties`, veri kaynağı nesneleri için zorunlu bir arabirim ve Numaralandırıcılar için isteğe bağlı bir arabirim. Ancak, bir Numaralandırıcı ortaya `IDBInitialize`çıkardığı takdirde, (veri kaynağındaki Özellikler) kullanıma sunmalıdır. `IDBProperties`

[IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)<br/>
Veri kaynağı nesnesine bir arabirim işaretçisi edinir. Oturumda zorunlu arabirim.

## <a name="other-classes"></a>Diğer sınıflar

[CUtlProps](../../data/oledb/cutlprops-class.md)<br/>
Çeşitli OLE DB Özellik arabirimleri için özellikleri uygular (örneğin `IDBProperties` `ISessionProperties`,, ve `IRowsetInfo`).

[IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)

OLE DB [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) arabirimini uygular, bir veri üyesine kayıt ekleme ve kayıtları alma.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB Şablonları](../../data/oledb/ole-db-templates.md)