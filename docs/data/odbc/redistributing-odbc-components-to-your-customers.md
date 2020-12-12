---
description: 'Daha fazla bilgi edinin: ODBC bileşenlerini müşterilerinize yeniden dağıtma'
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
ms.openlocfilehash: 02840156d648507065e0cadb1b8fa2b9c8146a7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204322"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>ODBC Bileşenlerini Müşterilerinize Yeniden Dağıtma

ODBC Yöneticisi programlarının işlevselliğini uygulamanıza eklerseniz, bu programları çalıştıran dosyaları kullanıcılarınıza da dağıtmanız gerekir. Bu ODBC dosyaları Visual C++ CD-ROM ' un \OS\System dizininde bulunur. Redistrb. wri dosyası ve lisans sözleşmesi aynı dizinde yeniden dağılayabilmeniz için bir ODBC dosyaları listesi içerir.

Teslim etmek istediğiniz tüm ODBC sürücüleri için belgelere başvurun. Hangi dll 'Lerin ve diğer dosyaların sevk edilecek olduğunu belirlemeniz gerekir. Ayrıca, ODBC bileşenlerinin nasıl yeniden dağıtılacağını açıklayan, [MÜŞTERILERINIZE ODBC bileşenlerini yeniden dağıtma](../../data/odbc/redistributing-odbc-components-to-your-customers.md)konusunu da okumalısınız.

Ayrıca, çoğu durumda başka bir dosya dahil etmeniz gerekir. Odbccr32.dll, ODBC Imleç kitaplığı ' dır. Bu kitaplık, 1. düzey sürücülere ileri ve geri kaydırma özelliği verir. Ayrıca, anlık görüntüleri destekleme özelliği de sağlar. ODBC Imleç kitaplığı hakkında daha fazla bilgi için bkz. [ODBC: ODBC Imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).

Aşağıdaki konularda, veritabanı sınıflarıyla ODBC kullanma hakkında daha fazla bilgi sağlanmaktadır:

- [ODBC: ODBC Imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC: ODBC veri kaynağını yapılandırma](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC: ODBC API Işlevlerini doğrudan çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>Ayrıca bkz.

[ODBC temelleri](../../data/odbc/odbc-basics.md)<br/>
[ODBC Yöneticisi](../../data/odbc/odbc-administrator.md)
