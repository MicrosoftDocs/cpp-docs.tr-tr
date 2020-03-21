---
title: CCustomSession (CustomSess.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidersession
- myprovidersess.h
- ccustomsession
- customsess.h
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
- CCustomSession class in CustomSess.H
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
ms.openlocfilehash: 4775f21c1e0fa7666d24b4d6a55e099bc6ae55a2
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079754"
---
# <a name="ccustomsession-customsessh"></a>CCustomSession (CustomSess.H)

*Özel* Sess. H, OLE DB Session nesnesinin bildirimini ve uygulamasını içerir. Veri kaynağı nesnesi, oturum nesnesini oluşturur ve bir tüketici ile sağlayıcı arasındaki konuşmayı temsil eder. Bir veri kaynağı için birkaç eşzamanlı oturum açılabilir. `CCustomSession` devralma listesi aşağıdadır:

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSession
class ATL_NO_VTABLE CCustomSession :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IGetDataSourceImpl<CCustomSession>,
   public IOpenRowsetImpl<CCustomSession>,
   public ISessionPropertiesImpl<CCustomSession>,
   public IObjectWithSiteSessionImpl<CCustomSession>,
   public IDBSchemaRowsetImpl<CCustomSession>,
   public IDBCreateCommandImpl<CCustomSession, CCustomCommand>
```

Oturum nesnesi `IGetDataSource`, `IOpenRowset`, `ISessionProperties`ve `IDBCreateCommand`devralır. `IGetDataSource` arabirimi, bir oturumun onu oluşturan veri kaynağını almasına izin verir. Bu, oluşturduğunuz veri kaynağından veya veri kaynağının sağlayabilmesini sağlayan diğer bilgilerden Özellikler almanız gerekiyorsa yararlıdır. `ISessionProperties` arabirimi, oturum için tüm özellikleri işler. `IOpenRowset` ve `IDBCreateCommand` arabirimleri, veritabanı çalışmasını yapmak için kullanılır. Sağlayıcı komutları destekliyorsa `IDBCreateCommand` arabirimini uygular. Komutları yürütebilmesi için komut nesnesini oluşturmak için kullanılır. Sağlayıcı `IOpenRowset` nesnesini her zaman uygular. Sağlayıcıdan bir satır kümesi oluşturmak için kullanılır. Sağlayıcıdan bir varsayılan satır kümesidir (örneğin, `"select * from mytable"`).

Sihirbaz ayrıca üç oturum sınıfı üretir: `CCustomSessionColSchema`, `CCustomSessionPTSchema`ve `CCustomSessionTRSchema`. Bu oturumlar, şema satır kümeleri için kullanılır. Şema satır kümeleri, bir sorgu yürütmeden veya veri getirmeye gerek kalmadan, sağlayıcının tüketiciye meta veri döndürmesini sağlar. Verilerin getirilmesi, bir sağlayıcının yeteneklerini bulmadan çok daha hızlı olabilir.

OLE DB belirtimi, `IDBSchemaRowset` arabirimini uygulayan sağlayıcıların üç şema satır kümesi türünü desteklemesini gerektirir: DBSCHEMA_COLUMNS, DBSCHEMA_PROVIDER_TYPES ve DBSCHEMA_TABLES. Sihirbaz her şema satır kümesi için uygulamalar oluşturur. Sihirbaz tarafından oluşturulan her sınıf bir `Execute` yöntemi içerir. Bu `Execute` yönteminde, hangi tabloları, sütunları ve veri türlerini destekleyeceği hakkında sağlayıcıya veri döndürebilirsiniz. Bu veriler derleme zamanında bilinir.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)<br/>
