---
title: OLE DB sağlayıcı şablonları başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 42909a9ddc24131c759886c4d169c4fd7484ca98
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340423"
---
# <a name="ole-db-provider-templates-reference"></a>OLE DB Sağlayıcı Şablonları Başvurusu
Sınıflar ve arabirimler OLE DB sağlayıcı şablonları için aşağıdaki kategoride gruplandırılabilir. Başvuru malzemesi hakkında bilgiler de içerir. [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md).  
  
 Sınıfları aşağıdaki adlandırma kuralını kullanabilirsiniz: desen ile adlı bir sınıf `IWidgetImpl` arabiriminin sağlayacağını `IWidget`.  
  
## <a name="session-classes"></a>Oturum sınıfı  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 Veri kaynağı nesnesinin yeni bir oturum oluşturur ve yeni oluşturulan oturum istenen arabirim döndürür. Veri kaynağı nesneleri zorunlu arabirimde.  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 Özellik kümesi eşlemesi tarafından tanımlanan statik bir işlev çağırarak oturum özellikleri uygular. Özellik kümesi eşlemesi oturumu Sınıfınız içinde belirtilmelidir. Oturumlarının zorunlu arabirimde.  
  
## <a name="rowset-classes"></a>Satır kümesi sınıfları  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 Standart bir OLE DB satır kümesi uygulaması, birçok uygulama arabirimlerin birden çok devralma gerek kalmadan sağlar. Kendisi için sağlamalısınız uygulamasıdır tek yöntem `Execute`.  
  
 [CSimpleRow](../../data/oledb/csimplerow-class.md)  
 Satır tanıtıcısı kullanılan bir varsayılan uygulamasını sağlar `IRowsetImpl` sınıfı. Bir satır tanıtıcı, mantıksal bir sonuç satırı için benzersiz bir etiket değil. `IRowsetImpl` Yeni bir oluşturur `CSimpleRow` her satır içinde istenen için `IRowsetImpl::GetNextRows`.  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB sağlayıcıları uygulamak gerektiren bir `HACCESSOR`, bir dizi için bir etiket olduğu `DBBINDING` yapıları. Sağlar `HACCESSOR`adresler, s `BindType` yapıları. Zorunlu satır kümeleri ve komutları.  
  
 [Icolumnsınfoımpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 Sağlayıcı sütun eşlemesi tarafından tanımlanan statik bir işlevi temsil eder. Zorunlu bir arabirim satır kümeleri ve komutları.  
  
 [Iconverttypeımpl](../../data/oledb/iconverttypeimpl-class.md)  
 Bir komutu veya bir satır kümesi tür dönüştürmeleri kullanılabilirliği hakkında bilgi sağlar. Zorunlu komutları, satır kümeleri ve dizin satır kümeleri. Implements `IConvertType` OLE DB tarafından sağlanan dönüştürme nesne için temsilci tarafından arabirimi.  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 Implements `IDBSchemaRowset` arabirimi ve şablonlaştırılmış oluşturucu işlevi `CreateSchemaRowset`.  
  
 [Iopenrowsetımpl](../../data/oledb/iopenrowsetimpl-class.md)  
 Açar ve tek bir temel tablo veya dizini tablosundan tüm satırları içeren bir satır kümesi döndürür. Bir oturum nesnesi için zorunlu arabirim.  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 OLE DB uygulayan [IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx) var olan satır, satırları silme ve yeni satır ekleyerek sütunların değerlerinin güncelleştirme sağlayan arabirim.  
  
 [Irowsetcreatorımpl](../../data/oledb/irowsetcreatorimpl-class.md)  
 Bu sınıf devraldığı [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) ve geçersiz kılmaları [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). `IRowsetCreatorImpl` aynı işlevleri gerçekleştiren `IObjectWithSite` ancak OLE DB özelliklerini de etkinleştirir `DBPROPCANSCROLLBACKWARDS` ve `DBPROPCANFETCHBACKWARDS`.  
  
 [IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)  
 Implements `IRowsetIdentity` arabirimi, iki veri satırını aynı olup olmadığını karşılaştırmanızı sağlar.  
  
 [Irowsetımpl](../../data/oledb/irowsetimpl-class.md)  
 Bir uygulamasını sağlar `IRowset` temel satır kümesi arabirimi olan arabirimi.  
  
 [IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)  
 Implements özelliğini kullanarak satır kümesi özelliklerini komut Sınıfınız içinde tanımlanan eşlemesi ayarlayın. Satır kümeleri zorunlu arabirimde.  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 OLE DB uygulayan [IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx) arabirimi, bir satır kümesinden rastgele satırları getirir. OLE DB yer işaretleri bir satır kümesinde desteklemek için bu sınıftan devralınan satır kümesi olun.  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 Uygular bağlantı noktası üzerinde dinleyici bildirmek için işlevleri yayın `IID_IRowsetNotify` değişiklik kümesi içeriği. Bildirimleri işleme tüketiciler uygulamak [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx) ve bu bağlantı noktasında kaydedin.  
  
 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)  
 OLE DB uygulayan [IRowsetUpdate](https://msdn.microsoft.com/library/ms714401.aspx) yapılan değişikliklerle iletimini gecikme tüketiciler sağlayan arabirimi [IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx) için veri kaynağını seçin ve iletimden önce değişiklikleri geri al.  
  
## <a name="command-classes"></a>Komut sınıfları  
 [Icommandımpl](../../data/oledb/icommandimpl-class.md)  
 Bir uygulamasını sağlar `ICommand` arabirimi. Bu arabirim için görünür değildir, ancak bu tarafından işlenen `ICommandTextImpl`. Komut nesnesi üzerinde zorunlu bir arabirim.  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 Bu uygulaması `ICommandProperties` arabirim tarafından tanımlanan statik işlev tarafından sağlanır `BEGIN_PROPSET_MAP` makrosu. Zorunlu açma komutları.  
  
 [Icommandtextımpl](../../data/oledb/icommandtextimpl-class.md)  
 Ayarlar, depolar ve komut metni döndürür. Zorunlu açma komutları.  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 Oturum nesnesinden yeni bir komut oluşturur ve yeni oluşturulan komut üzerinde istenen arabirim döndürür. Oturum nesneleri üzerinde isteğe bağlı bir arabirim.  
  
 Diğer komut sınıflardır `IColumnsInfoImpl` ve `IAccessorImpl`yukarıdaki satır kümesi sınıfları bölümünde açıklandığı gibi.  
  
## <a name="data-source-classes"></a>Veri kaynak sınıfları  
 [Idbınitializeımpl](../../data/oledb/idbinitializeimpl-class.md)  
 Oluşturur ve tüketici bağlantıyla siler. Veri kaynağı nesneleri ve isteğe bağlı bir arabirim numaralandırıcılar üzerinde zorunlu arabirim.  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` veri kaynağı nesneleri için zorunlu bir arabirim ve numaralandırıcılar için isteğe bağlı bir arabirim değildir. Ancak, bir numaralandırıcı sunarsa `IDBInitialize`, açığa çıkarmalıdır `IDBProperties` (veri kaynağı özellikleri).  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 Veri kaynağı nesnesinin bir arabirim işaretçisi alır. Oturumun zorunlu arabirim.  
  
## <a name="other-classes"></a>Diğer sınıflar  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 OLE DB özelliği arabirimleri çeşitli özelliklerini uygular (örneğin, `IDBProperties`, `ISessionProperties`, ve `IRowsetInfo`).  
  
 [Ierrorrecordsımpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 OLE DB uygulayan [IErrorRecords](https://msdn.microsoft.com/library/ms718112.aspx) kayıtları ekleme ve veri üyesi kayıtlar alınırken arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB Şablonları](../../data/oledb/ole-db-templates.md)