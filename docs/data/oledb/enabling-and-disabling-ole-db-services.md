---
title: Etkinleştirme ve devre dışı bırakma OLE DB hizmetleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6edd507edc21d58d17435b1d31d918a965db624a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100740"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma

OLE DB hizmet bileşeni Yöneticisi bu genişletilmiş işlevselliği tüketici tarafından istenen karşılamak için tek tek hizmet bileşenleri çağırılabilir olup olmadığını belirlemek için sağlayıcı tarafından desteklenen tüketiciye tarafından belirtilen özellikleri karşılaştırır. Örneğin, kaydırılabilir bir imleç bir uygulama ister ve sağlayıcı yalnızca yalnızca ileri yönlü bir imleç destekliyorsa, kaydırılabilir işlevselliği sağlamak için istemci imleci altyapısı hizmet bileşeni hizmet bileşeni Yöneticisi çağırır. Uygulama işlevselliği varsayılan sağlayıcının satır kümesi tarafından desteklenen bağlı ve uygulamayı açıkça oluşturmazsa işlevleri, işlevlerini istemci tarafından döndürülen satır görünmeyebilir olduğunu istemek için özellikleri ayarlayın. İmleç Altyapısı. Kullanılabilmelidir, uygulamalar her zaman genişletilmiş işlevselliği açıkça isteyecek şekilde ayarlamanız gerekir gerektiğinde.  
  
Bazı durumlarda, sağlayıcı özellikleri hakkında varsayımlar de var olan uygulamalarla birlikte çalışmak için tek tek OLE DB hizmetleri devre dışı bırakmak gerekli olabilir. OLE DB hizmetleri bireysel hizmetlerin veya bağlantı tarafından bağlantı olarak veya tek bir sağlayıcıyı kullanan tüm uygulamalar için tüm hizmetleri devre dışı bırakma olanağı sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Kaynak Havuzu ve Hizmetleri](../../data/oledb/ole-db-resource-pooling-and-services.md)