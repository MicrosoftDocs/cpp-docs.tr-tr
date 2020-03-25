---
title: OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
ms.openlocfilehash: 3016126d09b39ec74f4acb758a2176be05052648
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210970"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma

OLE DB Service Component Manager, tüketici tarafından belirtilen özellikleri, tüketici tarafından istenen genişletilmiş işlevselliği karşılamak için bağımsız hizmet bileşenlerinin kullanılıp kullanılamayacağını öğrenmek için sağlayıcı tarafından desteklenen özelliklerle karşılaştırır. Örneğin, bir uygulama kaydırılabilir bir imleç isterse ve sağlayıcı yalnızca bir salt iletme imlecini destekliyorsa, hizmet Bileşen Yöneticisi kaydırılabilir işlevselliği sağlamak için Istemci Imleç altyapısı hizmeti bileşenini kullanır. Uygulamanın, sağlayıcının satır kümesinde varsayılan olarak desteklenen genişletilmiş işlevlere bağlı olması ve uygulamanın özelliği bu işlevselliği isteyecek şekilde açıkça ayarlanmamışsa, bu işlev Istemcinin döndürdüğü satır kümesinde görünmeyebilir İmleç altyapısı. Uygulamalar, birlikte kullanılabilmek üzere her zaman gerekli olan yerlerde Genişletilmiş işlevselliği isteyecek şekilde özelliklerinin ayarlanmış olması gerekir.

Bazı durumlarda, bireysel OLE DB hizmetlerinin bir sağlayıcının özellikleri hakkında varsayımlar yapan mevcut uygulamalarla düzgün çalışmasını sağlamak gerekebilir. OLE DB hizmetler tek tek Hizmetleri veya tüm hizmetleri, tek bir sağlayıcı kullanan bağlantı ya da tüm uygulamalar için devre dışı bırakma yeteneği sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Kaynak Havuzu ve Hizmetleri](../../data/oledb/ole-db-resource-pooling-and-services.md)
