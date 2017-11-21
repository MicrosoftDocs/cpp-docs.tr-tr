---
title: CMyProviderCommand (MyProviderRS.H) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 68846352d3e6b407a4ec7ef6b7993969371a89de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmyprovidercommand-myproviderrsh"></a>CMyProviderCommand (MyProviderRS.H)
`CMyProviderCommand` Sınıfı sağlayıcı komut nesnesinin uygulamasıdır. Uygulamasını sağlar `IAccessor`, `ICommandText`, ve **ICommandProperties** arabirimleri. `IAccessor` Arabirimidir satır kümesindeki bir ile aynı. Komut nesnesi erişimcisi parametreleri için bağlamaları belirlemek için kullanır. Satır kümesi nesnesi bunları çıktı sütun için bağlamaları belirlemek için kullanır. `ICommandText` Bir komut belirtmede yararlı bir şekilde bir arabirimdir. Bu örnekte `ICommandText` özel kod eklediğinde daha sonra arabirim; ayrıca geçersiz kılar `ICommand::Execute` yöntemi. **ICommandProperties** arabirimi tüm özellikler komutu ve satır kümesi nesneleri için işler.  
  
```  
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
  
 `IAccessor` Arabirimi komutları ve satır kümeleri kullanılan tüm bağlamaları yönetir. Tüketici çağrıları **DBBINDING** dizisi ile **IAccessor::CreateAccessor'ı** yapıları. Her **IAccessor::CreateAccessor'ı** yapısı (türünü ve uzunluğu gibi) sütun bağlamaları nasıl işleneceğini hakkında bilgiler içerir. Sağlayıcı yapıları alır ve verileri nasıl aktarılması gerektiğini ve dönüştürmenin gerekli olup belirler. `IAccessor` Arabirimi command nesnesinde komut tüm parametreleri işlemek için kullanılır.  
  
 Komut nesnesi ayrıca bir uygulamasını sağlar `IColumnsInfo`. OLE DB gerektirir `IColumnsInfo` arabirimi. Tüketici komuttan parametreleri hakkında bilgi almak arabirim sağlar. Satır kümesi nesnesi kullanan `IColumnsInfo` sağlayıcıya çıktı sütunları hakkında bilgi döndürmek için arabirim.  
  
 Sağlayıcı ayrıca adlı bir arabirim içerir `IObjectWithSite`. `IObjectWithSite` Arabirimi ATL 2. 0'da uygulanmıştır ve kendi alt kendi hakkında bilgileri geçirmek uygulayan sağlar. Komut nesnesi kullanır `IObjectWithSite` herhangi bildirmek için bilgi oluşturulan oluşturan kişiye hakkında rowset nesneleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sağlayıcı Sihirbazı tarafından oluşturulan dosyalar](../../data/oledb/provider-wizard-generated-files.md)