---
title: OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
ms.openlocfilehash: c5eaff8b3b37096eeca8777b6ba8bb91e01d7cd2
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265210"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma

OLE DB hizmet bileşeni Yöneticisi, bireysel hizmet bileşenlerinin genişletilmiş işlevselliği tüketici tarafından istenen karşılamak için kullanılabilir olup olmadığını belirlemek için sağlayıcı tarafından desteklenen özellikler tüketiciye tarafından belirtilen özellikleri karşılaştırır. Örneğin, kaydırılabilir bir imleç bir uygulama ister ve sağlayıcı yalnızca yalnızca ileri yönlü bir imleç destekliyorsa, hizmet bileşeni Yöneticisi istemci imleci altyapısı hizmet bileşeni kaydırılabilir işlevselliği sağlamak için kullanır. Uygulama işlevselliği varsayılan sağlayıcının satır kümesi tarafından desteklenen bağlı ve uygulamayı açıkça değil işlevleri, işlevlerini istemci tarafından döndürülen satır görünmeyebilir olduğunu istemek için özelliklerini ayarlayın İmleç Altyapısı. Kullanılabilmelidir, uygulamalar her zaman genişletilmiş işlevselliği açıkça isteyecek şekilde ayarlamanız gerekir gerektiğinde.

Bazı durumlarda, sağlayıcı özellikleri hakkında varsayımlar de var olan uygulamalarla birlikte çalışmak için tek tek OLE DB hizmetleri devre dışı bırakmak gerekli olabilir. OLE DB hizmetleri bireysel hizmetlerin veya bağlantı tarafından bağlantı olarak veya tek bir sağlayıcıyı kullanan tüm uygulamalar için tüm hizmetleri devre dışı bırakma olanağı sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Kaynak Havuzu ve Hizmetleri](../../data/oledb/ole-db-resource-pooling-and-services.md)