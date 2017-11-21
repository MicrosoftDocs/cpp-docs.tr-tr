---
title: CMyProviderRowset (MyProviderRS.H) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e8a099ed08075877b7ca611e15994c2d68c25137
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmyproviderrowset-myproviderrsh"></a>CMyProviderRowset (MyProviderRS.H)
Sihirbaz satır kümesi nesnesi için bir giriş oluşturur. Bu durumda, adlı `CMyProviderRowset`. `CMyProviderRowset` Sınıfı olarak adlandırılan bir OLE DB sağlayıcısı sınıfından devralan `CRowsetImpl`, satır kümesi nesnesi için tüm gerekli arabirimlerini uygular. Aşağıdaki kod için devralma zincirini gösterir `CRowsetImpl`:  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T > >  
```  
  
 `CRowsetImpl`Ayrıca kullanır `IAccessor` ve `IColumnsInfo` arabirimleri. Bu arabirimleri tablolardaki çıktı alanları için kullanır. Sınıfı için uygulama sağlar **IRowsetIdentity**, tüketicinin iki satır aynı olup olmadığını belirlemesine izin verir. `IRowsetInfo` Arabirimi özelliklerini satır kümesi nesnesi uygular. **IConvertType** arabirim tüketici tarafından istenen veri türleri ve sağlayıcı tarafından kullanılan arasındaki farklılıkları çözümlemesine izin verir.  
  
 `IRowset` Arabirimi aslında veri almayı işler. Tüketici ilk olarak adlandırılan bir yöntem çağırır `GetNextRows` olarak bilinen bir satır için bir işleyiciyi döndürmek için bir **HROW**. Daha sonra tüketici çağırır **'yı** alanıyla **HROW** istenen verileri almak için.  
  
 `CRowsetImpl`Ayrıca çok şablon parametresi alır. Bu parametreleri belirlemenize izin nasıl `CRowsetImpl` sınıfı verilerini işler. `ArrayType` Bağımsız değişkeni, hangi depolama mekanizmasını satır verileri depolamak için kullanılan belirlemenize olanak verir. **RowClass** parametresi belirtir hangi sınıfı içeren bir **HROW**.  
  
 **RowsetInterface** parametresi de kullanmanıza olanak verir `IRowsetLocate` veya `IRowsetScroll` arabirimi. `IRowsetLocate` Ve `IRowsetScroll` her ikisi devral arabirimleri `IRowset`. Bu nedenle, OLE DB sağlayıcı şablonları Bu arabirimler için özel olarak işlenmesi sağlamanız gerekir. Bu arabirimleri birini kullanmak istiyorsanız, bu parametreyi kullanmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sağlayıcı Sihirbazı tarafından oluşturulan dosyalar](../../data/oledb/provider-wizard-generated-files.md)