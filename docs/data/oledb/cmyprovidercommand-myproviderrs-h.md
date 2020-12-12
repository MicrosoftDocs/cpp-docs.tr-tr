---
description: 'Daha fazla bilgi edinin: CCustomCommand (CustomRS. H)'
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
ms.openlocfilehash: 35b0e1a1628920a85343a52ce4a003302468884b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170509"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

`CCustomCommand`Sınıfı, sağlayıcı komut nesnesinin uygulamasıdır. `IAccessor`, `ICommandText` , Ve arabirimleri için uygulama sağlar `ICommandProperties` . `IAccessor`Arabirim, satır kümesindeki bir ile aynıdır. Komut nesnesi, parametrelere yönelik bağlamaları belirtmek için erişimcisini kullanır. Satır kümesi nesnesi bunları çıkış sütunları için bağlamaları belirtmek üzere kullanır. `ICommandText`Arabirim, bir Command metin içeriğini eklemek belirtmek için kullanışlı bir yoldur. Bu örnek, `ICommandText` daha sonra özel kod eklediğinde arabirimi kullanır; bu da yöntemi geçersiz kılar `ICommand::Execute` . `ICommandProperties`Arabirim, komut ve satır kümesi nesneleri için tüm özellikleri işler.

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

`IAccessor`Arabirim, komutlarda ve satır kümelerinde kullanılan tüm bağlamaları yönetir. Tüketici `IAccessor::CreateAccessor` bir yapı dizisi ile çağrı yapılır `DBBINDING` . Her `DBBINDING` Yapı, sütun bağlamalarının nasıl işlenmesi gerektiği hakkında bilgi içerir (örneğin, tür ve uzunluk). Sağlayıcı yapıları alır ve sonra verilerin nasıl aktarılacağını ve herhangi bir dönüştürmenin gerekli olup olmadığını belirler. Arabirim, komutta `IAccessor` herhangi bir parametreyi işlemek için komut nesnesinde kullanılır.

Komut nesnesi de bir uygulamasını sağlar `IColumnsInfo` . OLE DB arabirimi gerektirir `IColumnsInfo` . Arabirim, tüketicinin komuttan parametreler hakkında bilgi almasına izin verir. Satır kümesi nesnesi, `IColumnsInfo` sağlayıcıya çıkış sütunları hakkında bilgi döndürmek için arabirimini kullanır.

Sağlayıcı adlı bir arabirim de içerir `IObjectWithSite` . `IObjectWithSite`Arabirim, ATL 2,0 ' de uygulanmıştır ve uygulayıcının kendi alt öğesi hakkında bilgi almasına izin verir. Komut nesnesi, `IObjectWithSite` oluşturulan herhangi bir satır kümesi nesnesini kimin oluşturduğunu bildirmek için bu bilgileri kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Wizard-Generated dosyaları](../../data/oledb/provider-wizard-generated-files.md)
