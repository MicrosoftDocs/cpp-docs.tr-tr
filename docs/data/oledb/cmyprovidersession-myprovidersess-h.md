---
title: CMyProviderSession (MyProviderSess.H) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyprovidersession
- myprovidersess.h
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6bc3a9d377592b16c7e90cf0e75a6fba0eb00a64
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340133"
---
# <a name="cmyprovidersession-myprovidersessh"></a>CMyProviderSession (MyProviderSess.H)
MyProviderSess.H bildirimini ve uygulamasını için OLE DB oturum nesnesi içerir. Veri kaynağı nesnesinin oturum nesnesi oluşturur ve bir konuşma müşteri ve sağlayıcı arasında temsil eder. Bir veri kaynağı için birden fazla eşzamanlı oturum açılabilir. Devralma listesini `CMyProviderSession` izler:  
  
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
  
 Oturum nesnesi devraldığı `IGetDataSource`, `IOpenRowset`, `ISessionProperties`, ve `IDBCreateCommand`. `IGetDataSource` Arabirim oluşturulduğu veri kaynağından almak bir oturum sağlar. Bu özellikler, oluşturduğunuz veri kaynağı veya veri kaynağı diğer bilgileri almaya ihtiyacınız olduğunda yararlıdır. `ISessionProperties` Arabirimi oturumu için tüm özellikleri işler. `IOpenRowset` Ve `IDBCreateCommand` arabirimleri veritabanı işlerini yapmak için kullanılır. Sağlayıcı komutları destekliyorsa, onu uygulayan `IDBCreateCommand` arabirimi. Bu komutları yürütebilir komut nesnesi oluşturmak için kullanılır. Sağlayıcı her zaman uygulayan `IOpenRowset` nesne. Basit bir satır kümesi Sağlayıcısı'ndan oluşturmak için kullanılır. Varsayılan bir satır olduğundan (örneğin, `"select * from mytable"`) bir sağlayıcısı.  
  
 Sihirbaz aynı zamanda üç oturumu sınıflar oluşturur: `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema`, ve `CMyProviderSessionTRSchema`. Bu oturumlar şema satır kümeleri için kullanılır. Şema satır kümeleri sağlayıcısı meta verileri bir sorgu veya fetch veri yürütülecek olan tüketici Tüketiciye döndürülecek izin verir. Meta veriler getirilirken bir sağlayıcının yeteneklerini keşfetmekten çok daha hızlı olabilir.  
  
 OLE DB belirtimi gerektiren uygulama sağlayıcıları `IDBSchemaRowset` arabirimi desteği üç şeması satır kümesi türleri: DBSCHEMA_COLUMNS DBSCHEMA_PROVIDER_TYPES ve DBSCHEMA_TABLES. Sihirbaz her şeması satır kümesi için uygulamaları oluşturur. Sihirbaz tarafından oluşturulan her bir sınıf içeren bir `Execute` yöntemi. Bu `Execute` yöntemi, hangi tablolar, sütunlar ve veri türleri hakkında size destek sağlayıcısı için veri döndürebilir. Bu veriler genellikle derleme zamanında olarak bilinir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)