---
title: CCustomCommand (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- ccustomcommand
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: afa8571173117a23962eb84f6fa5b4cf2c3c46e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211763"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

`CCustomCommand` sınıfı, sağlayıcı komut nesnesinin uygulamasıdır. `IAccessor`, `ICommandText`ve `ICommandProperties` arabirimleri için uygulama sağlar. `IAccessor` arabirimi, satır kümesindeki bir ile aynıdır. Komut nesnesi, parametrelere yönelik bağlamaları belirtmek için erişimcisini kullanır. Satır kümesi nesnesi bunları çıkış sütunları için bağlamaları belirtmek üzere kullanır. `ICommandText` arabirimi, Command metin içeriğini eklemek belirtmek için kullanışlı bir yoldur. Bu örnek, daha sonra özel kod eklediğinde `ICommandText` arabirimini kullanır; Ayrıca `ICommand::Execute` yöntemini geçersiz kılar. `ICommandProperties` arabirimi komut ve satır kümesi nesneleri için tüm özellikleri işler.

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

`IAccessor` arabirimi, komutlarda ve satır kümelerinde kullanılan tüm bağlamaları yönetir. Tüketici, `DBBINDING` yapıları dizisiyle `IAccessor::CreateAccessor` çağırır. Her `DBBINDING` yapısı, sütun bağlamalarının nasıl ele alınacağını (tür ve uzunluk gibi) içeren bilgileri içerir. Sağlayıcı yapıları alır ve sonra verilerin nasıl aktarılacağını ve herhangi bir dönüştürmenin gerekli olup olmadığını belirler. `IAccessor` arabirimi, komutta herhangi bir parametreyi işlemek için komut nesnesinde kullanılır.

Komut nesnesi ayrıca bir `IColumnsInfo`uygulanmasını sağlar. OLE DB `IColumnsInfo` arabirimini gerektirir. Arabirim, tüketicinin komuttan parametreler hakkında bilgi almasına izin verir. Satır kümesi nesnesi, sağlayıcıya çıkış sütunları hakkında bilgi döndürmek için `IColumnsInfo` arabirimini kullanır.

Sağlayıcı ayrıca `IObjectWithSite`adlı bir arabirim içerir. `IObjectWithSite` arabirimi ATL 2,0 ' de uygulanmıştır ve uygulayıcının kendi alt öğesi hakkında bilgi almasına izin verir. Komut nesnesi, oluşturulan herhangi bir satır kümesi nesnesini kimin oluşturduğunu bildirmek için `IObjectWithSite` bilgilerini kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)
