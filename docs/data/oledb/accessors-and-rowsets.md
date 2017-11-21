---
title: "Erişimciler ve satır kümeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accessors [C++]
- OLE DB consumer templates, rowset support
- OLE DB consumer templates, accessors
- rowsets [C++], accessing
- bulk rowsets
- CAccessorRowset class, accessor types
- single rowsets
- CArrayRowset class, accessors
- CBulkRowset class, accessors
- array rowsets
- CAccessorBase class
- CRowset class, accessors and rowsets
- accessors [C++], rowsets
- rowsets [C++], supported types
ms.assetid: edc9c8b3-1a2d-4c2d-869f-7e058c631042
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0514524c3f96791c05b3d3ae33b8196deb7e554
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="accessors-and-rowsets"></a>Erişimciler ve Satır Kümeleri
Ve veri almak için OLE DB Şablonları erişimci ve satır aracılığıyla kullanın [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) sınıfı. Bu sınıf, farklı türlerde çoklu erişimci işleyebilir.  
  
## <a name="accessor-types"></a>Erişimci türleri  
 Tüm erişimciler türetin [CAccessorBase](../../data/oledb/caccessorbase-class.md). `CAccessorBase`parametre ve sütun bağlama sağlar.  
  
 Aşağıdaki şekilde erişimci türleri gösterilmektedir.  
  
 ![Erişimci türleri](../../data/oledb/media/vcaccessortypes.gif "vcaccessortypes")  
Erişimci sınıfları  
  
-   [CAccessor](../../data/oledb/caccessor-class.md) tasarım zamanında veritabanı kaynağının yapısını biliyorsanız, bu erişimciyi kullanın. `CAccessor`statik olarak arabellek içeren bir veritabanı kaydını veri kaynağına bağlar.  
  
-   [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) tasarım zamanında veritabanının yapısını bilmiyorsanız, bu erişimciyi kullanın. `CDynamicAccessor`çağrıları `IColumnsInfo::GetColumnInfo` veritabanı sütun bilgileri alınamıyor. Oluşturur ve erişimci ve arabellek yönetir.  
  
-   [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) Bilinmeyen komut türlerini yönetmek için bu erişimciyi kullanın. Komutları hazırladığınızda `CDynamicParameterAccessor` parametre bilgileri edinebilirsiniz `ICommandWithParameters` sağlayıcı destekliyorsa, arabirim `ICommandWithParameters`.  
  
-   [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md), ve [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md) veritabanı şeması hiçbir bilgiye sahip olduğunda bu sınıfların kullanın. `CDynamicStringAccessorA`verileri ANSI dizeleri olarak alır; `CDynamicStringAccessorW` verileri Unicode dizeleri olarak alır.  
  
-   [CManualAccessor](../../data/oledb/cmanualaccessor-class.md) Bu sınıf ile sağlayıcı türü dönüştürebilirsiniz isteyip istemediğinizi hangi veri türlerini kullanabilirsiniz. Sonuç sütunlarının ve komut parametreleri işler.  
  
 OLE DB Şablon erişimci türleri desteği aşağıdaki tabloda özetlenmiştir.  
  
|Erişimci türü|Dinamik|Params işleme|Arabellek|Çoklu Erişimci|  
|-------------------|-------------|--------------------|------------|------------------------|  
|`CAccessor`|Hayır|Evet|Kullanıcı|Evet|  
|`CDynamicAccessor`|Evet|Hayır|OLE DB Şablonları|Hayır|  
|`CDynamicParameterAccessor`|Evet|Evet|OLE DB Şablonları|Hayır|  
|`CDynamicStringAccessor[A,W]`|Evet|Hayır|OLE DB Şablonları|Hayır|  
|`CManualAccessor`|Evet|Evet|Kullanıcı|Evet|  
  
## <a name="rowset-types"></a>Satır kümesi türleri  
 OLE DB Şablonları üç tür satır kümeleri (yukarıdaki şekle bakın) destekler: tek satır kümeleri (tarafından uygulanan [CRowset](../../data/oledb/crowset-class.md)), toplu satır kümeleri (tarafından uygulanan [CBulkRowset](../../data/oledb/cbulkrowset-class.md)) ve dizi satır kümeleri (uygulanmadı tarafından [CArrayRowset](../../data/oledb/carrayrowset-class.md)). Tek bir satır işleyici tek satır kümeleri fetch `MoveNext` olarak adlandırılır. Toplu satır kümeleri birden çok satır işleyiciler getirebilir. Dizi satır kümeleri dizi sözdizimi kullanılarak erişilebilir satır kümeleri ' dir.  
  
 Aşağıdaki şekilde satır kümesi türleri gösterilmektedir.  
  
 ![RowsetType grafik](../../data/oledb/media/vcrowsettypes.gif "vcrowsettypes")  
Satır kümesi sınıfları  
  
 [Şema satır kümeleri](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) yapmak veri verilere erişmek saklar, ancak bunun yerine access meta verileri adlı veri depolama alanı hakkında bilgi. Şema satır kümeleri genellikle veritabanı yapısı derleme zamanında bilinmiyor ve çalışma zamanında alınan durumlarda kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)