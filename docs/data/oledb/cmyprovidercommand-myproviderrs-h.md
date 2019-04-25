---
title: CCustomCommand (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
- ccustomcommand
- customrs.h
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: b10d7bccae6fa9b86d072b8e13791f23516b2c63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230725"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

`CCustomCommand` Sınıfı sağlayıcısı komut nesnesi uygulamasıdır. Uygulamasını sağlar `IAccessor`, `ICommandText`, ve `ICommandProperties` arabirimleri. `IAccessor` Arabirimi olan bir satır kümesi ile aynı. Komut nesnesi erişimci bağlamaları parametreleri belirtmek için kullanır. Satır kümesi nesnesi çıkış sütunları bağlamalarda belirtmek için bunları kullanır. `ICommandText` Arabirimi, bir komut belirtmede kullanışlı bir yoludur. Bu örnekte `ICommandText` özel kod eklediğinde, daha sonra arabirim; ayrıca geçersiz kılar `ICommand::Execute` yöntemi. `ICommandProperties` Arabirimi komut ve satır kümesi nesneler için tüm özellikler işler.

```cpp
// CCustomCommand
class ATL_NO_VTABLE CCustomCommand :
class ATL_NO_VTABLE CCustomCommand :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IAccessorImpl<CCustomCommand>,
   public ICommandTextImpl<CCustomCommand>,
   public ICommandPropertiesImpl<CCustomCommand>,
   public IObjectWithSiteImpl<CCustomCommand>,
   public IConvertTypeImpl<CCustomCommand>,
   public IColumnsInfoImpl<CCustomCommand>
```

`IAccessor` Arabirimi komutları ve satır kümeleri kullanılan tüm bağlantıları yönetir. Tüketici çağrıları `IAccessor::CreateAccessor` bir `DBBINDING` yapıları. Her `DBBINDING` yapısı (türde ve uzunluktaki gibi) sütun bağlamaları nasıl işleneceğini hakkında bilgileri içerir. Sağlayıcı, yapıları alır ve ardından verileri nasıl transfer ve herhangi bir dönüştürme gerekli olup belirler. `IAccessor` Arabirimi command nesnesinde komut tüm parametreleri işlemek için kullanılır.

Komut nesnesi de bir uygulamasını sağlar `IColumnsInfo`. OLE DB gerektirir `IColumnsInfo` arabirimi. Tüketici komutu parametreleri hakkında bilgi almak arabirim sağlar. Satır kümesi nesnesi kullanan `IColumnsInfo` sağlayıcıya çıkış sütunları hakkında bilgi döndürmek için arabirim.

Sağlayıcı adlı bir arabirim de içeren `IObjectWithSite`. `IObjectWithSite` Arabirimi ATL 2. 0'da uygulanmıştır ve kendi hakkında bilgileri, Alta geçirmek uygulayan sağlar. Komut nesnesi kullanır `IObjectWithSite` herhangi bildirmek için bilgi oluşturulan kimin oluşturduğunu hakkında rowset nesneleri.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)