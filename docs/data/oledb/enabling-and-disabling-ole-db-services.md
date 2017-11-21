---
title: "Etkinleştirme ve devre dışı bırakma OLE DB hizmetleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9cbbef3b1f83b1b39c92ef689d5924b8962f32b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma
OLE DB hizmet bileşeni Yöneticisi bu bireysel hizmet bileşenlerinin tüketici tarafından istenen genişletilmiş işlevselliği karşılamak için çağrılıp çağrılmadığını belirlemek için sağlayıcı tarafından desteklenen tüketici tarafından belirtilen özellikleri karşılaştırılmaktadır. Örneğin, bir uygulama kaydırılabilir imleç isterse ve sağlayıcı yalnızca salt iletme imleç destekliyorsa, hizmet bileşeni Yöneticisi kaydırılabilir işlevselliği sağlamak için İstemci İmleç Altyapısı hizmeti bileşeni çağırır. Uygulama, varsayılan sağlayıcının satır kümesi olarak desteklenen genişletilmiş işlevsellik güvenmek ve uygulama açıkça işlevselliği işlevselliği istemci tarafından döndürülen satır kümesi görünmeyebilir, istek için özellikleri ayarlanmadı İmleç Altyapısı. Kullanılabilmelidir, uygulamaları her zaman açık genişletilmiş işlevsellik isteyecek şekilde ayarlaması gereken gerektiğinde.  
  
 Bazı durumlarda, varsayımlarda bir sağlayıcısı özellikleri hakkında da varolan uygulamalarla birlikte çalışmak için ayrı ayrı OLE DB hizmetlerini devre dışı bırakmak gerekli olabilir. OLE DB hizmetleri tek tek Hizmetleri veya bağlantı bağlantı temelinde veya tek bir sağlayıcıyı kullanan tüm uygulamalar için tüm hizmetleri devre dışı bırakma özelliği sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB kaynak havuzu ve Hizmetleri](../../data/oledb/ole-db-resource-pooling-and-services.md)