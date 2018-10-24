---
title: Erişimciler ve satır kümeleri | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c3247cd3b5844df76b8a115a3f28a76874db2a16
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990184"
---
# <a name="accessors-and-rowsets"></a>Erişimciler ve Satır Kümeleri

Ve veri almak için OLE DB Şablonları erişimci ve bir satır kümesi aracılığıyla kullanın [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) sınıfı. Bu sınıf, farklı türlerde birden çok erişimci başa çıkabilir.  
  
## <a name="accessor-types"></a>Erişimci türleri  

Türetilen tüm erişimcileri [CAccessorBase](../../data/oledb/caccessorbase-class.md). `CAccessorBase` hem parametrenin hem de sütun bağlama sağlar.  
  
Aşağıdaki şekilde erişimci türleri gösterilmektedir.  
  
![Erişimci türleri](../../data/oledb/media/vcaccessortypes.gif "vcaccessortypes")  
Erişimci sınıfları  
  
- [CAccessor](../../data/oledb/caccessor-class.md) veritabanı kaynak yapısı tasarım zamanında bildiğinizde bu erişimci kullanın. `CAccessor` statik olarak arabellek içeren bir veritabanı kaydı veri kaynağına bağlar.  
  
- [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) tasarım zamanında veritabanının yapısını bilmediğinizde bu erişimci kullanın. `CDynamicAccessor` çağrıları `IColumnsInfo::GetColumnInfo` veritabanı sütun bilgileri alınamıyor. Bu, oluşturur ve bir erişimci ve arabellek yönetir.  
  
- [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) bu erişimci Bilinmeyen komut türlerini yönetmek için kullanın. Komutları hazırlarken `CDynamicParameterAccessor` parametre bilgilerini alabilirsiniz `ICommandWithParameters` sağlayıcı destekliyorsa, arabirim `ICommandWithParameters`.  
  
- [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md), ve [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md) veritabanı şeması hiçbir bilgiye sahip olduğunda bu sınıfları kullanın. `CDynamicStringAccessorA` verileri ANSI dizelerini alır; `CDynamicStringAccessorW` verileri Unicode dize olarak alır.  
  
- [CManualAccessor](../../data/oledb/cmanualaccessor-class.md) bu sınıfla, istediğiniz sağlayıcının türüne dönüştürebilir, hangi veri türlerini kullanabilirsiniz. Bu, hem sonuç sütunları hem de komut parametreleri işler.  
  
OLE DB Şablon erişimci türleri desteği aşağıdaki tabloda özetlenmiştir.  
  
|Erişimci türü|Dinamik|Params işleme|Arabellek|Çoklu Erişimci|  
|-------------------|-------------|--------------------|------------|------------------------|  
|`CAccessor`|Hayır|Evet|Kullanıcı|Evet|  
|`CDynamicAccessor`|Evet|Hayır|OLE DB Şablonları|Hayır|  
|`CDynamicParameterAccessor`|Evet|Evet|OLE DB Şablonları|Hayır|  
|`CDynamicStringAccessor[A,W]`|Evet|Hayır|OLE DB Şablonları|Hayır|  
|`CManualAccessor`|Evet|Evet|Kullanıcı|Evet|  
  
## <a name="rowset-types"></a>Satır kümesi türleri  

OLE DB Şablonları satır kümeleri (bkz. Yukarıdaki şekil) üç tür destekler: tek satır kümeleri (tarafından uygulanan [CRowset](../../data/oledb/crowset-class.md)), toplu satır kümeleri (tarafından uygulanan [CBulkRowset](../../data/oledb/cbulkrowset-class.md)) ve dizi satır kümeleri (uygulanmış tarafından [CArrayRowset](../../data/oledb/carrayrowset-class.md)). Tek bir satır işleyici tek kümeleri `MoveNext` çağrılır. Toplu satır kümeleri, birden çok satır işleyicilerini getirebilir. Dizi satır kümeleri dizi sözdizimi kullanılarak erişilebilir satır var.  
  
Aşağıdaki şekilde satır kümesi türleri gösterilmektedir.  
  
![RowsetType grafik](../../data/oledb/media/vcrowsettypes.gif "vcrowsettypes")  
Satır kümesi sınıfları  
  
[Şema satır kümeleri](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) yoksa veri erişim verileri depolamak ancak bunun yerine access olarak adlandırılan meta veri deposu hakkında bilgi. Şema satır kümeleri genellikle veritabanı yapısı derleme zamanında bilinen değildir ve çalışma zamanında alınmalıdır durumlarda kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)