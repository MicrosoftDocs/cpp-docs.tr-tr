---
title: CCustomSource (CustomDS.H)
ms.date: 10/22/2018
f1_keywords:
- myproviderds.h
- cmyprovidersource
- customds.h
- ccustomsource
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
- CCustomSource class in CustomDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
ms.openlocfilehash: 60324ae914c9490144a715e06323ee6d184ce201
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079730"
---
# <a name="ccustomsource-customdsh"></a>CCustomSource (CustomDS. h)

Sağlayıcı sınıfları birden çok devralma kullanır. Aşağıdaki kod, veri kaynağı nesnesinin devralma zincirini gösterir:

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSource
class ATL_NO_VTABLE CCustomSource :
   public CComObjectRootEx<CComSingleThreadModel>,
   public CComCoClass<CCustomSource, &CLSID_Custom>,
   public IDBCreateSessionImpl<CCustomSource, CCustomSession>,
   public IDBInitializeImpl<CCustomSource>,
   public IDBPropertiesImpl<CCustomSource>,
   public IPersistImpl<CCustomSource>,
   public IInternalConnectionImpl<CCustomSource>
```

Tüm COM bileşenleri `CComObjectRootEx` ve `CComCoClass`türetilir. `CComObjectRootEx`, `IUnknown` arabirimi için tüm uygulamaları sağlar. Herhangi bir iş parçacığı modelini işleyebilir. `CComCoClass`, gereken tüm hata desteğini işler. İstemciye daha zengin hata bilgileri göndermek istiyorsanız `CComCoClass`bazı hata API 'Lerini kullanabilirsiniz.

Veri kaynağı nesnesi Ayrıca birkaç ' Impl ' sınıfından devralır. Her sınıf, bir arabirim için uygulama sağlar. Veri kaynağı nesnesi `IPersist`, `IDBProperties`, `IDBInitialize`ve `IDBCreateSession` arabirimlerini uygular. Her arabirim, veri kaynağı nesnesini uygulamak için OLE DB gereklidir. Bu ' Impl ' sınıflarından birinden devralma veya devralma yaparak belirli işlevleri desteklemeyi veya desteklemeyi tercih edebilirsiniz. `IDBDataSourceAdmin` arabirimini desteklemek istiyorsanız, gereken işlevselliği almak için `IDBDataSourceAdminImpl` sınıfından kalıtılır.

## <a name="com-map"></a>COM eşlemesi

İstemci veri kaynağındaki bir arabirim için `QueryInterface` çağırdığında, aşağıdaki COM eşlemesinden geçer:

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSource
class ATL_NO_VTABLE CCustomSource :
   public CComObjectRootEx<CComSingleThreadModel>,
   public CComCoClass<CCustomSource, &CLSID_Custom>,
   public IDBCreateSessionImpl<CCustomSource, CCustomSession>,
   public IDBInitializeImpl<CCustomSource>,
   public IDBPropertiesImpl<CCustomSource>,
   public IPersistImpl<CCustomSource>,
   public IInternalConnectionImpl<CCustomSource>
```

Tüm COM bileşenleri `CComObjectRootEx` ve `CComCoClass`türetilir. `CComObjectRootEx`, `IUnknown` arabirimi için tüm uygulamaları sağlar. Herhangi bir iş parçacığı modelini işleyebilir. `CComCoClass`, gereken tüm hata desteğini işler. İstemciye daha zengin hata bilgileri göndermek istiyorsanız `CComCoClass`bazı hata API 'Lerini kullanabilirsiniz.

Veri kaynağı nesnesi Ayrıca birkaç ' Impl ' sınıfından devralır. Her sınıf, bir arabirim için uygulama sağlar. Veri kaynağı nesnesi `IPersist`, `IDBProperties`, `IDBInitialize`ve `IDBCreateSession` arabirimlerini uygular. Her arabirim, veri kaynağı nesnesini uygulamak için OLE DB gereklidir. Bu ' Impl ' sınıflarından birinden devralma veya devralma yaparak belirli işlevleri desteklemeyi veya desteklemeyi tercih edebilirsiniz. `IDBDataSourceAdmin` arabirimini desteklemek istiyorsanız, gereken işlevselliği almak için `IDBDataSourceAdminImpl` sınıfından kalıtılır.

## <a name="com-map"></a>COM eşlemesi

İstemci veri kaynağındaki bir arabirim için `QueryInterface` çağırdığında, aşağıdaki COM eşlemesinden geçer:

```cpp
BEGIN_COM_MAP(CCustomSource)
   COM_INTERFACE_ENTRY(IDBCreateSession)
   COM_INTERFACE_ENTRY(IDBInitialize)
   COM_INTERFACE_ENTRY(IDBProperties)
   COM_INTERFACE_ENTRY(IPersist)
   COM_INTERFACE_ENTRY(IInternalConnection)
END_COM_MAP()
```

COM_INTERFACE_ENTRY makroları ATL 'den ve `CComObjectRootEx` `QueryInterface` uygulamasına uygun arabirimleri döndürmesini söyleyecektir.

## <a name="property-map"></a>Özellik eşlemesi

Özellik eşlemesi sağlayıcı tarafından atanan tüm özellikleri belirtir:

```cpp
BEGIN_PROPSET_MAP(CCustomSource)
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)
      PROPERTY_INFO_ENTRY(ACTIVESESSIONS)
      PROPERTY_INFO_ENTRY(ASYNCTXNABORT)
      PROPERTY_INFO_ENTRY(ASYNCTXNCOMMIT)
      PROPERTY_INFO_ENTRY(BYREFACCESSORS)
      PROPERTY_INFO_ENTRY_VALUE(CATALOGLOCATION, DBPROPVAL_CL_START)
      PROPERTY_INFO_ENTRY(CATALOGTERM)
      PROPERTY_INFO_ENTRY(CATALOGUSAGE)
      PROPERTY_INFO_ENTRY(COLUMNDEFINITION)
      PROPERTY_INFO_ENTRY(CONCATNULLBEHAVIOR)
      PROPERTY_INFO_ENTRY(DATASOURCENAME)
      PROPERTY_INFO_ENTRY(DATASOURCEREADONLY)
      PROPERTY_INFO_ENTRY(DBMSNAME)
      PROPERTY_INFO_ENTRY(DBMSVER)
      PROPERTY_INFO_ENTRY_VALUE(DSOTHREADMODEL, DBPROPVAL_RT_FREETHREAD)
      PROPERTY_INFO_ENTRY(GROUPBY)
      PROPERTY_INFO_ENTRY(HETEROGENEOUSTABLES)
      PROPERTY_INFO_ENTRY(IDENTIFIERCASE)
      PROPERTY_INFO_ENTRY(MAXINDEXSIZE)
      PROPERTY_INFO_ENTRY(MAXROWSIZE)
      PROPERTY_INFO_ENTRY(MAXROWSIZEINCLUDESBLOB)
      PROPERTY_INFO_ENTRY(MAXTABLESINSELECT)
      PROPERTY_INFO_ENTRY(MULTIPLEPARAMSETS)
      PROPERTY_INFO_ENTRY(MULTIPLERESULTS)
      PROPERTY_INFO_ENTRY(MULTIPLESTORAGEOBJECTS)
      PROPERTY_INFO_ENTRY(MULTITABLEUPDATE)
      PROPERTY_INFO_ENTRY(NULLCOLLATION)
      PROPERTY_INFO_ENTRY(OLEOBJECTS)
      PROPERTY_INFO_ENTRY(ORDERBYCOLUMNSINSELECT)
      PROPERTY_INFO_ENTRY(OUTPUTPARAMETERAVAILABILITY)
      PROPERTY_INFO_ENTRY(PERSISTENTIDTYPE)
      PROPERTY_INFO_ENTRY(PREPAREABORTBEHAVIOR)
      PROPERTY_INFO_ENTRY(PREPARECOMMITBEHAVIOR)
      PROPERTY_INFO_ENTRY(PROCEDURETERM)
      PROPERTY_INFO_ENTRY(PROVIDERNAME)
      PROPERTY_INFO_ENTRY(PROVIDEROLEDBVER)
      PROPERTY_INFO_ENTRY(PROVIDERVER)
      PROPERTY_INFO_ENTRY(QUOTEDIDENTIFIERCASE)
      PROPERTY_INFO_ENTRY(ROWSETCONVERSIONSONCOMMAND)
      PROPERTY_INFO_ENTRY(SCHEMATERM)
      PROPERTY_INFO_ENTRY(SCHEMAUSAGE)
      PROPERTY_INFO_ENTRY(STRUCTUREDSTORAGE)
      PROPERTY_INFO_ENTRY(SUBQUERIES)
      PROPERTY_INFO_ENTRY(TABLETERM)
      PROPERTY_INFO_ENTRY(USERNAME)
   END_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)
   BEGIN_PROPERTY_SET(DBPROPSET_DBINIT)
      PROPERTY_INFO_ENTRY(AUTH_PASSWORD)
      PROPERTY_INFO_ENTRY(AUTH_PERSIST_SENSITIVE_AUTHINFO)
      PROPERTY_INFO_ENTRY(AUTH_USERID)
      PROPERTY_INFO_ENTRY(INIT_DATASOURCE)
      PROPERTY_INFO_ENTRY(INIT_HWND)
      PROPERTY_INFO_ENTRY(INIT_LCID)
      PROPERTY_INFO_ENTRY(INIT_LOCATION)
      PROPERTY_INFO_ENTRY(INIT_MODE)
      PROPERTY_INFO_ENTRY(INIT_PROMPT)
      PROPERTY_INFO_ENTRY(INIT_PROVIDERSTRING)
      PROPERTY_INFO_ENTRY(INIT_TIMEOUT)
   END_PROPERTY_SET(DBPROPSET_DBINIT)
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCE)
      PROPERTY_INFO_ENTRY(CURRENTCATALOG)
   END_PROPERTY_SET(DBPROPSET_DATASOURCE)
   CHAIN_PROPERTY_SET(CCustomSession)
END_PROPSET_MAP()
```

OLE DB Özellikler gruplandırılır. Veri kaynağı nesnesinin iki grup özelliği vardır: biri DBPROPSET_DATASOURCEINFO kümesi ve diğeri DBPROPSET_DBINIT kümesi için. DBPROPSET_DATASOURCEINFO kümesi, sağlayıcının ve veri kaynağının özelliklerine karşılık gelir. DBPROPSET_DBINIT kümesi, başlatma sırasında kullanılan özelliklere karşılık gelir. OLE DB sağlayıcı şablonları, bu kümeleri PROPERTY_SET makrolarıyla işler. Makrolar bir özellikler dizisi içeren bir blok oluşturur. İstemci `IDBProperties` arabirimini her çağırdığında, sağlayıcı özellik eşlemesini kullanır.

Belirtimde her özelliği uygulamanız gerekmez. Ancak, gerekli özellikleri desteklemeniz gerekir; daha fazla bilgi için düzey 0 uyumluluk belirtimine bakın. Bir özelliği desteklemek istemiyorsanız, bunu haritadan kaldırabilirsiniz. Bir özelliği desteklemek istiyorsanız, PROPERTY_INFO_ENTRY makro kullanarak Haritayı haritaya ekleyin. Makro, aşağıdaki kodda gösterildiği gibi `UPROPINFO` yapısına karşılık gelir:

```cpp
struct UPROPINFO
{
   DBPROPID    dwPropId;
   ULONG       ulIDS;
   VARTYPE     VarType;
   DBPROPFLAGS dwFlags;
   union
   {
      DWORD dwVal;
      LPOLESTR szVal;
   };
   DBPROPOPTIONS dwOption;
};
```

Yapıdaki her öğe, özelliği işlemek için bilgileri temsil eder. Özelliğin GUID 'INI ve KIMLIĞINI belirlemede bir `DBPROPID` içerir. Ayrıca, özelliğin türünü ve değerini belirleme girdilerini de içerir.

Bir özelliğin varsayılan değerini değiştirmek istiyorsanız (bir müşterinin yazılabilir bir özelliğin değerini istediğiniz zaman değiştirebileceğine, PROPERTY_INFO_ENTRY_VALUE veya PROPERTY_INFO_ENTRY_EX makrosunu kullanabilirsiniz. Bu makrolar, karşılık gelen bir özellik için bir değer belirtmenize olanak tanır. PROPERTY_INFO_ENTRY_VALUE makrosu, değeri değiştirmenize olanak tanıyan bir Özet gösterimidir. PROPERTY_INFO_ENTRY_VALUE makro PROPERTY_INFO_ENTRY_EX makrosunu çağırır. Bu makro `UPROPINFO` yapısındaki tüm öznitelikleri eklemenize veya değiştirmenize olanak sağlar.

Kendi özellik kümesini tanımlamak istiyorsanız, ek bir BEGIN_PROPSET_MAP/END_PROPSET_MAP birleşimi yaparak bir tane ekleyebilirsiniz. Özellik kümesi için bir GUID tanımlayın ve ardından kendi özelliklerinizi tanımlayın. Sağlayıcıya özel özellikler varsa, var olan bir özellik kullanmak yerine bunları yeni bir özellik kümesine ekleyin. Bu, sonraki OLE DB sürümlerindeki sorunları önler.

## <a name="user-defined-property-sets"></a>Kullanıcı tanımlı özellik kümeleri

Görsel C++ Kullanıcı tanımlı özellik kümelerini destekler. `GetProperties` veya `GetPropertyInfo`geçersiz kılmak zorunda değilsiniz. Bunun yerine, şablonlar Kullanıcı tanımlı herhangi bir özellik kümesini algılar ve uygun nesneye ekler.

Başlatma zamanında kullanılabilir olması gereken kullanıcı tanımlı bir özellik kümesine sahipseniz (diğer bir deyişle, tüketici `IDBInitialize::Initialize`çağırmadan önce), bunu BEGIN_PROPERTY_SET_EX makrolarıyla birlikte UPROPSET_USERINIT bayrağını kullanarak belirtebilirsiniz. Özellik kümesi, bunun çalışması için veri kaynağı nesnesinde olmalıdır (OLE DB belirtimi gerektirdiğinden). Örnek:

```cpp
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)
```

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)<br/>
