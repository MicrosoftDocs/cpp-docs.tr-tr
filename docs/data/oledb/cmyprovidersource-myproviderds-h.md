---
title: CMyProviderSource (MyProviderDS.H) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0bdb766abd034868fe12fc0913fbdd99287b9e4f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cmyprovidersource-myproviderdsh"></a>CMyProviderSource (MyProviderDS.H)
Sağlayıcı sınıflar birden çok devralma kullanın. Aşağıdaki kod, veri kaynağı nesnesi için devralma zincirini gösterir:  
  
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
  
 Tüm COM bileşenleri türetin `CComObjectRootEx` ve `CComCoClass`. `CComObjectRootEx` Tüm uygulamasını sağlar **IUnknown** arabirimi. Herhangi bir iş parçacığı modelini işleyebilir. `CComCoClass` gerekli tüm hata desteğini işler. Daha zengin hata bilgisi istemciye göndermek istiyorsanız, bazı hata API'lerini kullanabilirsiniz, `CComCoClass`.  
  
 Veri kaynağı nesnesi de birkaç 'Impl' sınıflardan devralır. Her sınıf bir arabirim uygulamasını sağlar. Veri kaynağı nesnesi uygular `IPersist`, `IDBProperties`, **IDBInitialize**, ve **IDBCreateSession** arabirimleri. Her bir arabirime tarafından OLE DB veri kaynağı nesnesi uygulamak için gereklidir. Belirli işlevi devralarak veya bu 'Impl' sınıflarından birini devralarak desteklemiyor veya desteklemek üzere seçebilirsiniz. Desteklemek istiyorsanız **IDBDataSourceAdmin** , arabirim, devralınan **IDBDataSourceAdminImpl** gerekli işlevi almak için sınıf.  
  
## <a name="com-map"></a>COM eşlemesi  
 Her istemci çağırır `QueryInterface` isteğe bağlı olarak veri kaynağında bir arabirim için aşağıdaki COM eşlemesi üzerinden gider:  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 COM_INTERFACE_ENTRY makrolar ATL ve uygulanması söyleyin `QueryInterface` içinde `CComObjectRootEx` uygun arabirimleri dönün.  
  
## <a name="property-map"></a>Özellik eşlemesi  
 Özellik eşlemesi sağlayıcı tarafından atanmış tüm özellikleri belirtir:  
  
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
  
 OLE DB özelliklerinde gruplandırılır. Veri kaynağı nesnesinin iki tür özelliği vardır: biri **DBPROPSET_DATASOURCEINFO** kümesi ve biri için **DBPROPSET_DBINIT** ayarlayın. **DBPROPSET_DATASOURCEINFO** sağlayıcı ve veri kaynağı ile ilgili özellikler kümesi karşılık gelir. **DBPROPSET_DBINIT** kümesi başlangıçta kullanılan özelliklere karşılık gelir. OLE DB sağlayıcı şablonları bu kümeleri PROPERTY_SET makroları ile işleyin. Makrolar özellikler dizisi içeren bir blok oluşturur. Her istemci çağırır `IDBProperties` arabirimi, sağlayıcı özellik eşlemesini kullanır.  
  
 Her özellik belirtiminde uygulamak gerekmez. Ancak, gerekli özelliklerini desteklemelidir; Düzey 0 uyum belirtimine daha fazla bilgi için bkz. Bir özelliği desteklemek istemiyorsanız eşlemesinden kaldırabilirsiniz. Bir özelliği desteklemek istiyorsanız, PROPERTY_INFO_ENTRY makrosu kullanarak eşlemeye ekleyin. Makro karşılık gelen **UPROPINFO** aşağıdaki kodda gösterildiği gibi yapılandırın:  
  
```  
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
  
 Her bir öğesinde yapısı özelliği işlemek için bilgileri temsil eder. İçerdiği bir **DBPROPID** GUID ve kimliği özelliği için belirlemek için. Ayrıca, türü ve özellik değerini belirlemek üzere girişleri içerir.  
  
 (Bir tüketici herhangi bir zamanda yazılabilir bir özellik değerini değiştirebilir unutmayın) özelliğinin varsayılan değeri değiştirmek istiyorsanız, PROPERTY_INFO_ENTRY_VALUE ya da PROPERTY_INFO_ENTRY_EX makrosu kullanabilirsiniz. Bu makroları karşılık gelen bir özellik için bir değer belirtmenizi sağlar. PROPERTY_INFO_ENTRY_VALUE makrosu değeri değiştirmenize olanak sağlayan bir toplu notasyona ' dir. PROPERTY_INFO_ENTRY_VALUE makrosu PROPERTY_INFO_ENTRY_EX makrosu çağırır. Bu makrosu ekleme veya tüm öznitelikleri değiştirme sayesinde **UPROPINFO** yapısı.  
  
 Kendi özellik kümesi tanımlamak istiyorsanız, ek bir BEGIN_PROPSET_MAP/END_PROPSET_MAP bileşimi yaparak ekleyebilirsiniz. Özellik kümesi için bir GUID tanımlamak ve kendi özelliklerinizi tanımlamanız gerekir. Sağlayıcıya özgü özellikleri varsa, bunları yeni bir özellik var olan bir kullanmak yerine kümesi ekleyin. OLE DB sonraki sürümlerinde sorunları önler.  
  
## <a name="user-defined-property-sets"></a>Kullanıcı tanımlı özellik kümeleri  
 Visual C++ kullanıcı tanımlı özellik kümelerini destekler. Geçersiz kılma gerekmez **GetProperties** veya `GetPropertyInfo`. Bunun yerine, şablonları herhangi bir kullanıcı tanımlı özellik kümesi algılamak ve uygun nesneye ekler.  
  
 Başlatma zamanında kullanılabilir olması gereken kullanıcı tanımlı özellik kümesi varsa (diğer bir deyişle, tüketici çağırmadan önce **IDBInitialize::Initialize**), bu kullanarak belirttiğiniz **UPROPSET_USERINIT** BEGIN_PROPERTY_SET_EX makrosu birlikte bayrağı. Özellik kümesi bunun (OLE DB belirtiminin gerektirdiği gibi) çalışması veri kaynağı nesnesi olması gerekir. Örneğin:  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)