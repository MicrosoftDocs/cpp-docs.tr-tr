---
title: CMyProviderSession (MyProviderSess.H) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmyprovidersession
- myprovidersess.h
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4ffb1a0ca8e9a2cd5b90d33c21423beb0969a4f4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cmyprovidersession-myprovidersessh"></a>CMyProviderSession (MyProviderSess.H)
MyProviderSess.H bildirim ve OLE DB oturum nesnesi uygulamasını içerir. Veri kaynağı nesnesi oturum nesnesi oluşturur ve bir tüketici ve sağlayıcı arasında görüşmeyi temsil eder. Bir veri kaynağı için birden fazla eşzamanlı oturum açılabilir. Devralma listesini `CMyProviderSession` izler:  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 Oturum nesnesi devraldığı **IGetDataSource**, `IOpenRowset`, **ISessionProperties**, ve **IDBCreateCommand**. **IGetDataSource** arabirimi oluşturulduğu veri kaynağından almak bir oturum sağlar. Bu özellikler, oluşturduğunuz veri kaynağı veya veri kaynağı sağlayabilir diğer bilgileri almak gerektiğinde kullanışlı olur. **ISessionProperties** arabirimi oturum için tüm özellikleri işler. `IOpenRowset` Ve **IDBCreateCommand** arabirimleri veritabanı işlerini yapmak için kullanılır. Sağlayıcı komutları destekliyorsa, uygulayan **IDBCreateCommand** arabirimi. Bu komutları çalıştırabilirsiniz komut nesnesi oluşturmak için kullanılır. Sağlayıcı her zaman uygulayan `IOpenRowset` nesnesi. Bir sağlayıcıdan basit bir satır kümesi oluşturmak için kullanılır. Varsayılan bir satır olduğundan (örneğin, `"select * from mytable"`) bir sağlayıcıdan.  
  
 Sihirbaz ayrıca üç oturum sınıfı oluşturur: `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema`, ve `CMyProviderSessionTRSchema`. Bu oturumlar şema satır kümeleri için kullanılır. Şema satır kümeleri, sorgu veya fetch veri yakalamadan tüketici tüketiciye döndürmenizi sağlayıcı izin verir. Meta veri yakalama sağlayıcının yeteneklerini keşfetme daha çok daha hızlı olabilir.  
  
 OLE DB belirtimine gerektiren uygulama sağlayıcıları **IDBSchemaRowset** arabirimi destek üç şema satır kümesi türleri: **DBSCHEMA_COLUMNS**, **DBSCHEMA_PROVIDER_TYPES** , ve `DBSCHEMA_TABLES`. Sihirbaz her şeması satır kümesi için uygulamaları oluşturur. Sihirbaz tarafından oluşturulan her sınıf içeren bir `Execute` yöntemi. Bu `Execute` yöntemi, hangi tablolar, sütunlar ve veri türleri hakkında desteklediğiniz sağlayıcı veri döndürebilirsiniz. Bu veri genellikle derleme zamanında bilinir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)