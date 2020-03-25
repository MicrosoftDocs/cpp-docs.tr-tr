---
title: ODBC Bileşenlerini Müşterilerinize Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
ms.openlocfilehash: 0d4d3948add665c54be3d3b0596a7a6fc0e414f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212738"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>ODBC Bileşenlerini Müşterilerinize Yeniden Dağıtma

ODBC Yöneticisi programlarının işlevselliğini uygulamanıza eklerseniz, bu programları çalıştıran dosyaları kullanıcılarınıza da dağıtmanız gerekir. Bu ODBC dosyaları, Visual C++ CD-ROM ' un \OS\System dizininde bulunur. Redistrb. wri dosyası ve lisans sözleşmesi aynı dizinde yeniden dağılayabilmeniz için bir ODBC dosyaları listesi içerir.

Teslim etmek istediğiniz tüm ODBC sürücüleri için belgelere başvurun. Hangi dll 'Lerin ve diğer dosyaların sevk edilecek olduğunu belirlemeniz gerekir. Ayrıca, ODBC bileşenlerinin nasıl yeniden dağıtılacağını açıklayan, [MÜŞTERILERINIZE ODBC bileşenlerini yeniden dağıtma](../../data/odbc/redistributing-odbc-components-to-your-customers.md)konusunu da okumalısınız.

Ayrıca, çoğu durumda başka bir dosya dahil etmeniz gerekir. ODBCCR32. dll, ODBC Imleç kitaplığı. Bu kitaplık, 1. düzey sürücülere ileri ve geri kaydırma özelliği verir. Ayrıca, anlık görüntüleri destekleme özelliği de sağlar. ODBC Imleç kitaplığı hakkında daha fazla bilgi için bkz. [ODBC: ODBC Imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).

Aşağıdaki konularda, veritabanı sınıflarıyla ODBC kullanma hakkında daha fazla bilgi sağlanmaktadır:

- [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC: ODBC Veri Kaynağını Yapılandırma](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC: ODBC API İşlevlerini Doğrudan Çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>Ayrıca bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)<br/>
[ODBC Yöneticisi](../../data/odbc/odbc-administrator.md)
