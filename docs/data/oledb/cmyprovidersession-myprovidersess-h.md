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
ms.openlocfilehash: 5cb462aba671e79450e9ee7b8447410252f8edc9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230587"
---
# <a name="ccustomsession-customsessh"></a>CCustomSession (CustomSess.H)

*Özel*Sess.H bildirimini ve uygulamasını için OLE DB oturum nesnesi içerir. Veri kaynağı nesnesinin oturum nesnesi oluşturur ve bir konuşma müşteri ve sağlayıcı arasında temsil eder. Bir veri kaynağı için birden fazla eşzamanlı oturum açılabilir. Devralma listesini `CCustomSession` izler:

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

Oturum nesnesi devraldığı `IGetDataSource`, `IOpenRowset`, `ISessionProperties`, ve `IDBCreateCommand`. `IGetDataSource` Arabirim oluşturulduğu veri kaynağından almak bir oturum sağlar. Bu özellikler, oluşturduğunuz veri kaynağı veya veri kaynağı diğer bilgileri almaya ihtiyacınız olduğunda yararlıdır. `ISessionProperties` Arabirimi oturumu için tüm özellikleri işler. `IOpenRowset` Ve `IDBCreateCommand` arabirimleri veritabanı işlerini yapmak için kullanılır. Sağlayıcı komutları destekliyorsa, onu uygulayan `IDBCreateCommand` arabirimi. Bu komutları yürütebilir komut nesnesi oluşturmak için kullanılır. Sağlayıcı her zaman uygulayan `IOpenRowset` nesne. Bir sağlayıcıdan bir satır kümesi oluşturmak için kullanılır. Varsayılan bir satır olduğundan (örneğin, `"select * from mytable"`) bir sağlayıcısı.

Sihirbaz aynı zamanda üç oturumu sınıflar oluşturur: `CCustomSessionColSchema`, `CCustomSessionPTSchema`, ve `CCustomSessionTRSchema`. Bu oturumlar şema satır kümeleri için kullanılır. Şema satır kümeleri sağlayıcısı meta verileri bir sorgu veya fetch veri yürütülecek olan tüketici Tüketiciye döndürülecek izin verir. Meta veriler getirilirken bir sağlayıcının özelliklerini bulma daha daha hızlı olabilir.

OLE DB belirtimi gerektiren uygulama sağlayıcıları `IDBSchemaRowset` arabirimi desteği üç şeması satır kümesi türleri: DBSCHEMA_COLUMNS DBSCHEMA_PROVIDER_TYPES ve DBSCHEMA_TABLES. Sihirbaz her şeması satır kümesi için uygulamaları oluşturur. Sihirbaz tarafından oluşturulan her bir sınıf içeren bir `Execute` yöntemi. Bu `Execute` yöntemi, hangi tablolar, sütunlar ve veri türleri hakkında size destek sağlayıcısı için veri döndürebilir. Bu veriler, derleme zamanında bilinir.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)<br/>
