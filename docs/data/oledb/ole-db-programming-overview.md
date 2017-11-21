---
title: "OLE DB programlamaya genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Universal Data Access
- OLE DB, about OLE DB
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1f3d97dda514b3cdb0773adb3d7830e611bca3d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ole-db-programming-overview"></a>OLE DB Programlamaya Genel Bakış
OLE DB yüksek performanslı, COM tabanlı veritabanı teknolojisidir. Formun, depolandığı bakılmaksızın verilere erişmek için genel bir yol sağlar. Tipik iş durumda çok büyük miktarda bilgi dışında şirket veritabanlarını depolanır. Bu bilgiler, dosya sistemlerinde (örneğin, FAT veya NTFS) dizine-sıralı dosyaları, kişisel veritabanları (örneğin, erişimi), elektronik tablolar (örneğin, Excel), proje planlama uygulamaları (örneğin, Proje) ve e-posta (örneğin, Outlook) bulunur. Veri deposunda bir OLE DB sağlayıcısı olduğu sürece OLE DB veri deposu herhangi bir tür aynı şekilde erişmenize olanak sağlar.
  
 OLE DB, DBMS olsun olmasın çeşitli veri kaynaklarına erişim uygulamalar geliştirmenize olanak sağlar. OLE DB, verilen veri kaynağı için uygun DBMS işlevselliğini destekleyen COM arabirimleri kullanarak evrensel erişimi mümkün kılar. COM hizmetlerin gereksiz yinelenmesini azaltır ve yalnızca veri kaynakları arasında aynı zamanda diğer uygulamalar arasında birlikte çalışabilirlik ekranı.  
  
## <a name="benefits-of-com"></a>COM yararları  
 COM böyle durumlarda budur. OLE DB, COM arabirimleri kümesidir. Tekdüzen arabirimleri kümesi veri erişerek bir veritabanı bileşenler Matrisine bir matris düzenleyebilirsiniz.  
  
 COM belirtimine dayalı olarak, OLE DB katan ve tutarlı, yeniden kullanılabilir kısımlarını DBMS işlevselliğini kapsülleyen arabirimleri genişletilebilir ve sürdürülebilir bir koleksiyonunu tanımlar. Bu arabirimleri satır kapsayıcıları, sorgu işlemcileri ve çeşitli bilgi kaynakları Tekdüzen işlem erişimi etkinleştirme işlem düzenleyicileri gibi DBMS bileşenlerinin sınırlarını tanımlayın.  
 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB programlama](../../data/oledb/ole-db-programming.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Şablonları](../../data/oledb/ole-db-templates.md)