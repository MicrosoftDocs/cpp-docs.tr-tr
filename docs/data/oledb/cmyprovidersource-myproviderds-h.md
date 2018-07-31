---
title: CMyProviderSource (MyProviderDS.H) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- myproviderds.h
- cmyprovidersource
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 848f940c9aa974c838a4600235ab97d099bcbd06
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340156"
---
# <a name="cmyprovidersource-myproviderdsh"></a>CMyProviderSource (MyProviderDS.H)
Birden çok devralma sağlayıcısı sınıfları kullanın. Aşağıdaki kod, veri kaynağı nesnesi için devralma zincirini gösterir:  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSource  
class ATL_NO_VTABLE CMyProviderSource :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public CComCoClass<CMyProviderSource, &CLSID_MyProvider>,  
   public IDBCreateSessionImpl<CMyProviderSource, CMyProviderSession>,  
   public IDBInitializeImpl<CMyProviderSource>,  
   public IDBPropertiesImpl<CMyProviderSource>,  
   public IPersistImpl<CMyProviderSource>,  
   public IInternalConnectionImpl<CMyProviderSource>  
```  
  
 Türetilen tüm COM bileşenlerini `CComObjectRootEx` ve `CComCoClass`. `CComObjectRootEx` Tüm uygulamasını sağlar `IUnknown` arabirimi. Bu, herhangi bir iş parçacığı modeli başa çıkabilir. `CComCoClass` gerekli herhangi bir hata destek işler. Daha zengin hata bilgileri istemciye göndermek istiyorsanız, bazı hata API'leri kullanabilirsiniz, `CComCoClass`.  
  
 Veri kaynağı nesnesinin ayrıca çeşitli ' Impl ' sınıfından devralır. Her sınıf, arabirim uygulamasını sağlar. Veri kaynağı nesnesi uygulayan `IPersist`, `IDBProperties`, `IDBInitialize`, ve `IDBCreateSession` arabirimleri. Her arabirim tarafından OLE DB veri kaynağı nesnesinin uygulamak için gereklidir. Bu 'Impl' sınıflarının birinden devralan değil ya da belirli işlevler desteklenmez veya desteklemek üzere seçebilirsiniz. Desteklemek istiyorsanız `IDBDataSourceAdmin` , arabirim, devralma `IDBDataSourceAdminImpl` gerekli işlevi almak için sınıf.  
  
## <a name="com-map"></a>COM eşlemesi  
 Her istemci çağrıları `QueryInterface` isteğe bağlı olarak veri kaynağında bir arabirim için aşağıdaki COM eşlemesi üzerinden geçer:  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 COM_INTERFACE_ENTRY makroları ATL rosling ve yürütmesinin `QueryInterface` içinde `CComObjectRootEx` uygun arabirimleri dönün.  
  
## <a name="property-map"></a>Özellik eşlemesi  
 Özellik eşlemesi sağlayıcı tarafından atanmış olan tüm özellikleri belirtir:  
  
```  
BEGIN_PROPSET_MAP(CMyProviderSource)  
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
   CHAIN_PROPERTY_SET(CMyProviderSession)  
END_PROPSET_MAP()  
```  
  
 OLE DB özelliklerinde gruplandırılır. Veri kaynağı nesnesinin özellikleri iki grup vardır: DBPROPSET_DATASOURCEINFO bir kümesi, diğeri DBPROPSET_DBINIT ayarlayın. DBPROPSET_DATASOURCEINFO kümesi özellikleri hakkında sağlayıcı ve veri kaynağına karşılık gelir. DBPROPSET_DBINIT kümesi başlangıçta kullanılan özelliklere karşılık gelir. OLE DB sağlayıcı şablonları PROPERTY_SET makrolar ile bu kümeleri işleyin. Makrolar, bir dizi özellikleri içeren bir blok oluşturur. Her istemci çağrıları `IDBProperties` arabirimi, sağlayıcı özellik eşlemesi kullanır.  
  
 Her özelliği belirtiminde uygulama gerekmez. Ancak, gerekli özelliklerini desteklemelidir; Düzey 0 Uyumluluğu belirtimi daha fazla bilgi için bkz. Bir özelliği desteklemek istemiyorsanız, haritadaki kaldırabilirsiniz. Bir özelliği desteklemek istiyorsanız, haritayı PROPERTY_INFO_ENTRY makrosu kullanarak ekleyin. Makro karşılık gelen `UPROPINFO` aşağıdaki kodda gösterildiği gibi yapılandırın:  
  
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
  
 Her öğe yapısında özelliği işlemek için bilgileri temsil eder. İçerdiği bir `DBPROPID` GUID ve ID özelliği belirlemek için. Ayrıca, türünü ve özelliğin değerini belirlemek için giriş içerir.  
  
 (Bir tüketici yazılabilir bir özellik değerini istediğiniz zaman değiştirebilirsiniz. Not) özelliğinin varsayılan değeri değiştirmek istiyorsanız, PROPERTY_INFO_ENTRY_VALUE ya da PROPERTY_INFO_ENTRY_EX makrosu kullanabilirsiniz. Bu makrolar, karşılık gelen bir özellik için bir değer belirtmenizi sağlar. PROPERTY_INFO_ENTRY_VALUE makrosu değeri değiştirmenize izin verir ve kısa bir gösterim ' dir. PROPERTY_INFO_ENTRY_VALUE makrosu PROPERTY_INFO_ENTRY_EX makrosu çağırır. Bu makro, eklemek veya tüm öznitelikleri değiştirmek sağlar `UPROPINFO` yapısı.  
  
 Kendi özellik kümesi tanımlamak istiyorsanız, ek bir BEGIN_PROPSET_MAP/END_PROPSET_MAP birleşim yaparak ekleyebilirsiniz. Özellik kümesi için bir GUID tanımlayın ve ardından kendi özelliklerinizi tanımlamanız gerekir. Sağlayıcıya özgü özellikleri varsa bunları kullanarak mevcut bir yerine yeni bir özellik ekleyin. Bu sorunlar daha sonraki sürümlerinde bir OLE DB önler.  
  
## <a name="user-defined-property-sets"></a>Kullanıcı tanımlı özellik kümeleri  
 Visual C++ kullanıcı tanımlı özellik kümesini destekler. Geçersiz kılma gerekmez `GetProperties` veya `GetPropertyInfo`. Bunun yerine, şablonlar, herhangi bir kullanıcı tarafından tanımlanan bir özellik kümesi algılamak ve uygun nesnesine ekleyin.  
  
 Başlatma zamanında kullanılabilir olması gereken kullanıcı tanımlı bir özellik kümesi varsa (diğer bir deyişle, tüketici çağırmadan önce `IDBInitialize::Initialize`), bu BEGIN_PROPERTY_SET_EX makrosu birlikte UPROPSET_USERINIT bayrağı kullanılarak belirtin. Özellik kümesi (OLE DB belirtimi gerektirdiği şekilde) çalışması bu veri kaynağı nesnesi olması gerekir. Örneğin:  
  
```cpp  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)