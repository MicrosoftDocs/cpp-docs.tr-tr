---
title: "Ne tür erişimci kullanacağınızı belirleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 28173b18e1f2ab6e7c916679d5fa5a27c08caaeb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="determining-which-type-of-accessor-to-use"></a>Ne Tür Erişimci Kullanacağınızı Belirleme
Derleme zamanında veya çalışma zamanında bir satır kümesi veri türlerinde belirleyebilirsiniz.  
  
 Derleme zamanında veri türleri belirlemeniz gerekiyorsa, statik erişimci kullanın (gibi `CAccessor`). El ile veya ATL OLE DB Tüketici Sihirbazı kullanarak veri türlerini belirleyebilirsiniz.  
  
 Çalışma zamanında veri türleri belirlemeniz gerekiyorsa, dinamik kullanın (`CDynamicAccessor` veya alt) veya el ile erişimci (`CManualAccessor`). Bu durumlarda, çağırabilirsiniz `GetColumnInfo` içinden belirleyebilirsiniz türleri sütun bağlama bilgilerini döndürülecek satır kümesi üzerinde.  
  
 Aşağıdaki tabloda Tüketici Şablonları sağlanan erişimciler türlerini listeler. Her erişimci avantajları ve dezavantajları vardır. Durumunuza bağlı olarak, bir erişimci türü gereksinimlerinize uygun.  
  
|Erişimci sınıfı|Bağlama|Parametre|Yorum|  
|--------------------|-------------|---------------|-------------|  
|`CAccessor`|Kullanarak bir kullanıcı kaydı oluşturma `COLUMN_ENTRY` makroları. Makrolar veri üyesi erişimcisi bu kayıtta bağlayın. Satır kümesi oluşturduğunuzda, sütunlar bağlanamaz.|Kullanarak Evet, bir **PARAM_MAP** makrosu girişi. Bağlandıktan parametreleri bağlanamaz.|Küçük miktarda kod nedeniyle Hızlı erişimcisi.|  
|`CDynamicAccessor`|Otomatik.|Hayır.|Bir satır kümesi veri türünü bilmiyorsanız yararlıdır.|  
|`CDynamicParameterAccessor`|Otomatik, ancak [geçersiz](../../data/oledb/overriding-a-dynamic-accessor.md).|Evet, sağlayıcı destekliyorsa `ICommandWithParameters`. Parametreler otomatik olarak bağlı.|Daha yavaş `CDynamicAccessor` ancak genel saklı yordamları çağırmak için kullanışlıdır.|  
|**CDynamicStringAccessor[A,W]**|Otomatik.|Hayır.|Dize veri olarak veri deposundan erişilen verileri alır.|  
|`CManualAccessor`|Kullanılarak el ile `AddBindEntry`.|Kullanarak el ile `AddParameterEntry`.|Çok hızlı; Parametreler ve sütunlar yalnızca bir kez bağlanmış. Kullanmak için veri türünü belirler. (Bkz [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) örnek bir örnek için.) Daha fazla kod gerektirir `CDynamicAccessor` veya `CAccessor`. OLE DB doğrudan çağırma gibi daha fazladır.|  
|`CXMLAccessor`|Otomatik.|Hayır.|Dize veri olarak veri deposundan erişilen verileri alır ve olarak XML etiketli veri biçimleri.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri Kullanma](../../data/oledb/using-accessors.md)