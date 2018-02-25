---
title: "Etkinleştirme ve devre dışı bırakma OLE DB hizmetleri | Microsoft Docs"
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
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dd98513201ef13f62a6eaf4a8ead90375df0f5ee
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma
OLE DB hizmet bileşeni Yöneticisi bu bireysel hizmet bileşenlerinin tüketici tarafından istenen genişletilmiş işlevselliği karşılamak için çağrılıp çağrılmadığını belirlemek için sağlayıcı tarafından desteklenen tüketici tarafından belirtilen özellikleri karşılaştırılmaktadır. Örneğin, bir uygulama kaydırılabilir imleç isterse ve sağlayıcı yalnızca salt iletme imleç destekliyorsa, hizmet bileşeni Yöneticisi kaydırılabilir işlevselliği sağlamak için İstemci İmleç Altyapısı hizmeti bileşeni çağırır. Uygulama, varsayılan sağlayıcının satır kümesi olarak desteklenen genişletilmiş işlevsellik güvenmek ve uygulama açıkça işlevselliği işlevselliği istemci tarafından döndürülen satır kümesi görünmeyebilir, istek için özellikleri ayarlanmadı İmleç Altyapısı. Kullanılabilmelidir, uygulamaları her zaman açık genişletilmiş işlevsellik isteyecek şekilde ayarlaması gereken gerektiğinde.  
  
 Bazı durumlarda, varsayımlarda bir sağlayıcısı özellikleri hakkında da varolan uygulamalarla birlikte çalışmak için ayrı ayrı OLE DB hizmetlerini devre dışı bırakmak gerekli olabilir. OLE DB hizmetleri tek tek Hizmetleri veya bağlantı bağlantı temelinde veya tek bir sağlayıcıyı kullanan tüm uygulamalar için tüm hizmetleri devre dışı bırakma özelliği sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Kaynak Havuzu ve Hizmetleri](../../data/oledb/ole-db-resource-pooling-and-services.md)