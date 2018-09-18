---
title: CMyProviderCommand (MyProviderRS.H) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 919455c1f0e1bae0491226e2f2d0f53bb35f7ad8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046608"
---
# <a name="cmyprovidercommand-myproviderrsh"></a>CMyProviderCommand (MyProviderRS.H)

`CMyProviderCommand` Sınıfı sağlayıcısı komut nesnesi uygulamasıdır. Uygulamasını sağlar `IAccessor`, `ICommandText`, ve `ICommandProperties` arabirimleri. `IAccessor` Arabirimi olan bir satır kümesi ile aynı. Komut nesnesi erişimci bağlamaları parametreleri belirtmek için kullanır. Satır kümesi nesnesi çıkış sütunları bağlamalarda belirtmek için bunları kullanır. `ICommandText` Arabirimi, bir komut belirtmede kullanışlı bir yoludur. Bu örnekte `ICommandText` özel kod eklediğinde, daha sonra arabirim; ayrıca geçersiz kılar `ICommand::Execute` yöntemi. `ICommandProperties` Arabirimi komut ve satır kümesi nesneler için tüm özellikler işler.  
  
```cpp  
// CMyProviderCommand  
class ATL_NO_VTABLE CMyProviderCommand :   
class ATL_NO_VTABLE CMyProviderCommand :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IAccessorImpl<CMyProviderCommand>,  
   public ICommandTextImpl<CMyProviderCommand>,  
   public ICommandPropertiesImpl<CMyProviderCommand>,  
   public IObjectWithSiteImpl<CMyProviderCommand>,  
   public IConvertTypeImpl<CMyProviderCommand>,  
   public IColumnsInfoImpl<CMyProviderCommand>  
```  
  
`IAccessor` Arabirimi komutları ve satır kümeleri kullanılan tüm bağlantıları yönetir. Tüketici çağrıları `IAccessor::CreateAccessor` bir `DBBINDING` yapıları. Her `DBBINDING` yapısı (türde ve uzunluktaki gibi) sütun bağlamaları nasıl işleneceğini hakkında bilgileri içerir. Sağlayıcı, yapıları alır ve ardından verileri nasıl transfer ve herhangi bir dönüştürme gerekli olup belirler. `IAccessor` Arabirimi command nesnesinde komut tüm parametreleri işlemek için kullanılır.  
  
Komut nesnesi de bir uygulamasını sağlar `IColumnsInfo`. OLE DB gerektirir `IColumnsInfo` arabirimi. Tüketici komutu parametreleri hakkında bilgi almak arabirim sağlar. Satır kümesi nesnesi kullanan `IColumnsInfo` sağlayıcıya çıkış sütunları hakkında bilgi döndürmek için arabirim.  
  
Sağlayıcı adlı bir arabirim de içeren `IObjectWithSite`. `IObjectWithSite` Arabirimi ATL 2. 0'da uygulanmıştır ve kendi hakkında bilgileri, Alta geçirmek uygulayan sağlar. Komut nesnesi kullanır `IObjectWithSite` herhangi bildirmek için bilgi oluşturulan kimin oluşturduğunu hakkında rowset nesneleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)