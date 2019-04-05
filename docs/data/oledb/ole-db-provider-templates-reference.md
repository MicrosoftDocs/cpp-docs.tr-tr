---
title: OLE DB Sağlayıcı Şablonları Başvurusu
ms.date: 11/04/2016
f1_keywords:
- vc.templates.ole
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
ms.openlocfilehash: e1d6be9687085361edd9141d8fb471e21b6f6376
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038683"
---
# <a name="ole-db-provider-templates-reference"></a>OLE DB Sağlayıcı Şablonları Başvurusu

Sınıflar ve arabirimler OLE DB sağlayıcı şablonları için aşağıdaki kategoride gruplandırılabilir. Başvuru malzemesi hakkında bilgiler de içerir. [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md).

Sınıfları aşağıdaki adlandırma kuralını kullanabilirsiniz: desen ile adlı bir sınıf `IWidgetImpl` arabiriminin sağlayacağını `IWidget`.

## <a name="session-classes"></a>Oturum sınıfı

[Idbcreatesessionımpl](../../data/oledb/idbcreatesessionimpl-class.md)<br/>
Veri kaynağı nesnesinin yeni bir oturum oluşturur ve yeni oluşturulan oturum istenen arabirim döndürür. Veri kaynağı nesneleri zorunlu arabirimde.

[ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)<br/>
Özellik kümesi eşlemesi tarafından tanımlanan statik bir işlev çağırarak oturum özellikleri uygular. Özellik kümesi eşlemesi oturumu Sınıfınız içinde belirtilmelidir. Oturumlarının zorunlu arabirimde.

## <a name="rowset-classes"></a>Satır kümesi sınıfları

[CRowsetImpl](../../data/oledb/crowsetimpl-class.md)

Standart bir OLE DB satır kümesi uygulaması, birçok uygulama arabirimlerin birden çok devralma gerek kalmadan sağlar. Kendisi için sağlamalısınız uygulamasıdır tek yöntem `Execute`.

[CSimpleRow](../../data/oledb/csimplerow-class.md)<br/>
Satır tanıtıcısı kullanılan bir varsayılan uygulamasını sağlar `IRowsetImpl` sınıfı. Bir satır tanıtıcı, mantıksal bir sonuç satırı için benzersiz bir etiket değil. `IRowsetImpl` Yeni bir oluşturur `CSimpleRow` her satır içinde istenen için `IRowsetImpl::GetNextRows`.

[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)<br/>
OLE DB sağlayıcıları uygulamak gerektiren bir `HACCESSOR`, bir dizi için bir etiket olduğu `DBBINDING` yapıları. Sağlar `HACCESSOR`adresler, s `BindType` yapıları. Zorunlu satır kümeleri ve komutları.

[Icolumnsınfoımpl](../../data/oledb/icolumnsinfoimpl-class.md)<br/>
Sağlayıcı sütun eşlemesi tarafından tanımlanan statik bir işlevi temsil eder. Zorunlu bir arabirim satır kümeleri ve komutları.

[Iconverttypeımpl](../../data/oledb/iconverttypeimpl-class.md)<br/>
Bir komutu veya bir satır kümesi tür dönüştürmeleri kullanılabilirliği hakkında bilgi sağlar. Zorunlu komutları, satır kümeleri ve dizin satır kümeleri. Implements `IConvertType` OLE DB tarafından sağlanan dönüştürme nesne için temsilci tarafından arabirimi.

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)<br/>
Implements `IDBSchemaRowset` arabirimi ve şablonlaştırılmış oluşturucu işlevi `CreateSchemaRowset`.

[IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)<br/>
Açar ve tek bir temel tablo veya dizini tablosundan tüm satırları içeren bir satır kümesi döndürür. Bir oturum nesnesi için zorunlu arabirim.

[IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)<br/>
OLE DB uygulayan [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) var olan satır, satırları silme ve yeni satır ekleyerek sütunların değerlerinin güncelleştirme sağlayan arabirim.

[IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)<br/>
Bu sınıf devraldığı [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) ve geçersiz kılmaları [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite). `IRowsetCreatorImpl` aynı işlevleri gerçekleştiren `IObjectWithSite` ancak OLE DB özelliklerini de etkinleştirir `DBPROPCANSCROLLBACKWARDS` ve `DBPROPCANFETCHBACKWARDS`.

[IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)<br/>
Implements `IRowsetIdentity` arabirimi, iki veri satırını aynı olup olmadığını karşılaştırmanızı sağlar.

[Irowsetımpl](../../data/oledb/irowsetimpl-class.md)<br/>
Bir uygulamasını sağlar `IRowset` temel satır kümesi arabirimi olan arabirimi.

[Irowsetınfoımpl](../../data/oledb/irowsetinfoimpl-class.md)<br/>
Implements özelliğini kullanarak satır kümesi özelliklerini komut Sınıfınız içinde tanımlanan eşlemesi ayarlayın. Satır kümeleri zorunlu arabirimde.

[IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)<br/>
OLE DB uygulayan [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) arabirimi, bir satır kümesinden rastgele satırları getirir. OLE DB yer işaretleri bir satır kümesinde desteklemek için bu sınıftan devralınan satır kümesi olun.

[IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)<br/>
Uygular bağlantı noktası üzerinde dinleyici bildirmek için işlevleri yayın `IID_IRowsetNotify` değişiklik kümesi içeriği. Bildirimleri işleme tüketiciler uygulamak [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) ve bu bağlantı noktasında kaydedin.

[IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)<br/>
OLE DB uygulayan [IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) yapılan değişikliklerle iletimini gecikme tüketiciler sağlayan arabirimi [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) için veri kaynağını seçin ve iletimden önce değişiklikleri geri al.

## <a name="command-classes"></a>Komut sınıfları

[Icommandımpl](../../data/oledb/icommandimpl-class.md)<br/>
Bir uygulamasını sağlar `ICommand` arabirimi. Bu arabirim için görünür değildir, ancak bu tarafından işlenen `ICommandTextImpl`. Komut nesnesi üzerinde zorunlu bir arabirim.

[ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)<br/>
Bu uygulaması `ICommandProperties` arabirim tarafından tanımlanan statik işlev tarafından sağlanır `BEGIN_PROPSET_MAP` makrosu. Zorunlu açma komutları.

[Icommandtextımpl](../../data/oledb/icommandtextimpl-class.md)<br/>
Ayarlar, depolar ve komut metni döndürür. Zorunlu açma komutları.

[Idbcreatecommandımpl](../../data/oledb/idbcreatecommandimpl-class.md)<br/>
Oturum nesnesinden yeni bir komut oluşturur ve yeni oluşturulan komut üzerinde istenen arabirim döndürür. Oturum nesneleri üzerinde isteğe bağlı bir arabirim.

Diğer komut sınıflardır `IColumnsInfoImpl` ve `IAccessorImpl`yukarıdaki satır kümesi sınıfları bölümünde açıklandığı gibi.

## <a name="data-source-classes"></a>Veri kaynak sınıfları

[Idbınitializeımpl](../../data/oledb/idbinitializeimpl-class.md)<br/>
Oluşturur ve tüketici bağlantıyla siler. Veri kaynağı nesneleri ve isteğe bağlı bir arabirim numaralandırıcılar üzerinde zorunlu arabirim.

[Idbpropertiesımpl](../../data/oledb/idbpropertiesimpl-class.md)<br/>
`IDBProperties` veri kaynağı nesneleri için zorunlu bir arabirim ve numaralandırıcılar için isteğe bağlı bir arabirim değildir. Ancak, bir numaralandırıcı sunarsa `IDBInitialize`, açığa çıkarmalıdır `IDBProperties` (veri kaynağı özellikleri).

[IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)<br/>
Veri kaynağı nesnesinin bir arabirim işaretçisi alır. Oturumun zorunlu arabirim.

## <a name="other-classes"></a>Diğer sınıflar

[CUtlProps](../../data/oledb/cutlprops-class.md)<br/>
OLE DB özelliği arabirimleri çeşitli özelliklerini uygular (örneğin, `IDBProperties`, `ISessionProperties`, ve `IRowsetInfo`).

[Ierrorrecordsımpl](../../data/oledb/ierrorrecordsimpl-class.md)

OLE DB uygulayan [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) kayıtları ekleme ve veri üyesi kayıtlar alınırken arabirimi.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB Şablonları](../../data/oledb/ole-db-templates.md)