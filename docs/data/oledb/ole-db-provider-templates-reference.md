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
ms.openlocfilehash: 040e8a5e244b7978a2b9ead394e243207939655c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-provider-templates-reference"></a>OLE DB Sağlayıcı Şablonları Başvurusu
Sınıflar ve arabirimler OLE DB sağlayıcı şablonları için aşağıdaki kategorilerde gruplandırılabilir. Başvuru malzemesinde hakkında bilgiler de içerir. [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md).  
  
 Sınıfları aşağıdaki adlandırma kuralını kullanın: desenle adlı bir sınıf **IWidgetImpl** arabirimini uygulaması sağlayacak **IWidget**.  
  
## <a name="session-classes"></a>Oturum sınıfı  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 Veri kaynağı nesnesinden yeni bir oturum oluşturur ve yeni oluşturulan oturum istenen arabirimi döndürür. Veri kaynağı nesneleri zorunlu arabirimde.  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 Oturum özellikleri özellik kümesi eşlemesini tarafından tanımlanan statik işlevini çağırarak uygular. Özellik kümesi eşlemesini oturum sınıfınızda belirtilmesi gerekir. Oturumları zorunlu arabirimde.  
  
## <a name="rowset-classes"></a>Satır kümesi sınıfları  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 Birçok uygulama arabirimlerinin birden çok devralma gerektirmeden standart bir OLE DB satır kümesi uygulaması sağlar. Kendisi için sağlamanız gerekir uygulamasıdır tek yöntem **yürütme**.  
  
 [CSimpleRow](../../data/oledb/csimplerow-class.md)  
 Kullanılan satır işleyici için bir varsayılan uygulama sağlar `IRowsetImpl` sınıfı. Bir satır mantıksal bir sonuç satır için benzersiz bir etiket işleyicisidir. `IRowsetImpl` Yeni bir `CSimpleRow` içindeki her satır istenen için `IRowsetImpl::GetNextRows`.  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB sağlayıcıları uygulamak gerektiren bir **HACCESSOR**, bir dizi etiket olduğu **IAccessor::CreateAccessor'ı** yapıları. Sağlar **HACCESSOR**adresleri olan s **BindType** yapıları. Zorunlu satır kümeleri ve komutları.  
  
 [Icolumnsınfoımpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 Sağlayıcı sütun eşlemesi tarafından tanımlanan statik bir işlevi temsil eder. Satır kümeleri ve komutları zorunlu arabirimde.  
  
 [Iconverttypeımpl](../../data/oledb/iconverttypeimpl-class.md)  
 Bir komutu veya bir satır kümesi tür dönüşümleri kullanılabilirliği hakkında bilgi sağlar. Zorunlu komutları, satır kümeleri ve dizin satır kümeleri. Implements **IConvertType** OLE DB tarafından sağlanan dönüştürme nesneye temsilci tarafından arabirimi.  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 Implements **IDBSchemaRowset** arabirimi ve şablonlaştırılmış creator işlevi `CreateSchemaRowset`.  
  
 [Iopenrowsetımpl](../../data/oledb/iopenrowsetimpl-class.md)  
 Açılır ve tek bir temel tablo veya dizini tüm satırları içeren bir satır kümesi döndürür. Bir oturum nesnesi için zorunlu arabirim.  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 OLE DB uygulayan [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) satırları silme ve yeni satırlar ekleme varolan satırları sütunlardaki değerlerin güncelleştirme sağlayan arabirim.  
  
 [Irowsetcreatorımpl](../../data/oledb/irowsetcreatorimpl-class.md)  
 Bu sınıf devraldığı [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) ve geçersiz kılmalar [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). `IRowsetCreatorImpl` aynı işlevleri gerçekleştiren `IObjectWithSite` ancak OLE DB özellikleri de etkinleştirir **DBPROPCANSCROLLBACKWARDS** ve **DBPROPCANFETCHBACKWARDS**.  
  
 [IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)  
 Implements **IRowsetIdentity** iki veri satırını aynı olsun olmasın karşılaştırmanıza olanak verir arabirimi.  
  
 [Irowsetımpl](../../data/oledb/irowsetimpl-class.md)  
 Bir uygulamasını sağlar `IRowset` temel satır kümesi arabirimi arabirimi.  
  
 [IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)  
 Implements özelliğini kullanarak satır kümesi özellikleri komut sınıfında tanımlanan eşlemesi ayarlayın. Satır kümeleri zorunlu arabirimde.  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 OLE DB uygulayan [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) rasgele satır satır kümesinden getirir arabirimi. OLE DB yer işaretleri bir satır kümesinde desteklemek için bu sınıftan devralınan satır kümesi olun.  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 Implements yayın dinleyicileri bağlantı noktasında bildirmek amacıyla işlevleri **IID_IRowsetNotify** satır içeriğini değişiklikler. Bildirimleri işleme tüketicileri uygulamak [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) ve bu bağlantı noktasında kaydedin.  
  
 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)  
 OLE DB uygulayan [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) yapılan değişikliklerle iletimini gecikme tüketicileri sağlayan arabirim [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) için veri kaynağı ve iletimden önce değişiklikleri geri almak.  
  
## <a name="command-classes"></a>Komut sınıfları  
 [Icommandımpl](../../data/oledb/icommandimpl-class.md)  
 Bir uygulamasını sağlar `ICommand` arabirimi. Bu arabirim görünür değildir, ancak tarafından işlenen **Icommandtextımpl**. Komut nesnesi üzerinde zorunlu bir arabirim.  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 Bu uygulaması, **ICommandProperties** arabirimi tarafından tanımlanan statik bir işlev tarafından sağlanan `BEGIN_PROPSET_MAP` makrosu. Zorunlu açma komutları.  
  
 [Icommandtextımpl](../../data/oledb/icommandtextimpl-class.md)  
 Ayarlar, depolar ve komut metni döndürür. Zorunlu açma komutları.  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 Oturum nesnesinden yeni bir komut oluşturur ve yeni oluşturulan komutunda istenen arabirimi döndürür. Oturum nesneleri üzerinde isteğe bağlı bir arabirim.  
  
 Diğer komut sınıflardır `IColumnsInfoImpl` ve `IAccessorImpl`, yukarıdaki satır kümesi sınıfları bölümünde de açıklanmıştır.  
  
## <a name="data-source-classes"></a>Veri kaynağı sınıfları  
 [Idbınitializeımpl](../../data/oledb/idbinitializeimpl-class.md)  
 Oluşturur ve tüketici bağlantıyla siler. Veri kaynağı nesneleri ve isteğe bağlı bir arabirim numaralandırıcılar üzerinde zorunlu arabirimde.  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` veri kaynağı nesneleri için zorunlu bir arabirim ve numaralandırmalar için isteğe bağlı bir arabirim ' dir. Ancak, bir numaralandırıcı gösterir, **IDBInitialize**, kullanıma gerekir `IDBProperties` (veri kaynağı özellikleri).  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 Veri kaynağı nesnesi için bir arabirim işaretçisi alır. Zorunlu arabirim oturum.  
  
## <a name="other-classes"></a>Diğer sınıflar  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 OLE DB özelliği arabirimleri çeşitli özelliklerini uygular (örneğin, `IDBProperties`, **ISessionProperties**, ve `IRowsetInfo`).  
  
 [Ierrorrecordsımpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 OLE DB uygulayan [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) kayıtları ekleme ve veri üyeden kayıtları almak arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB Şablonları](../../data/oledb/ole-db-templates.md)