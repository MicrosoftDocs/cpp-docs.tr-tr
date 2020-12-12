---
description: 'Daha fazla bilgi edinin: OLE DB hizmetleri etkinleştirme ve devre dışı bırakma'
title: OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
ms.openlocfilehash: a2a3e51b69a0051b6a231d14c18f3b1f416fb547
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317668"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma

OLE DB Service Component Manager, tüketici tarafından belirtilen özellikleri, tüketici tarafından istenen genişletilmiş işlevselliği karşılamak için bağımsız hizmet bileşenlerinin kullanılıp kullanılamayacağını öğrenmek için sağlayıcı tarafından desteklenen özelliklerle karşılaştırır. Örneğin, bir uygulama kaydırılabilir bir imleç isterse ve sağlayıcı yalnızca bir salt iletme imlecini destekliyorsa, hizmet Bileşen Yöneticisi kaydırılabilir işlevselliği sağlamak için Istemci Imleç altyapısı hizmeti bileşenini kullanır. Uygulama, sağlayıcının satır kümesinde varsayılan olarak desteklenen genişletilmiş işlevlere bağlı ise ve uygulama özelliği bu işlevselliği isteyecek şekilde açıkça ayarlanmamışsa, bu işlev Istemci Imleç altyapısının döndürdüğü satır kümesinde görünmeyebilir. Uygulamalar, birlikte kullanılabilmek üzere her zaman gerekli olan yerlerde Genişletilmiş işlevselliği isteyecek şekilde özelliklerinin ayarlanmış olması gerekir.

Bazı durumlarda, bireysel OLE DB hizmetlerinin bir sağlayıcının özellikleri hakkında varsayımlar yapan mevcut uygulamalarla düzgün çalışmasını sağlamak gerekebilir. OLE DB hizmetler tek tek Hizmetleri veya tüm hizmetleri, tek bir sağlayıcı kullanan bağlantı ya da tüm uygulamalar için devre dışı bırakma yeteneği sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak havuzu ve Hizmetleri OLE DB](../../data/oledb/ole-db-resource-pooling-and-services.md)
