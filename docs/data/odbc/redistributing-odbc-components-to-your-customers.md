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
ms.openlocfilehash: 1a6ec6f5fdd3c32080d357ca58d31ccea271b7a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330082"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>ODBC Bileşenlerini Müşterilerinize Yeniden Dağıtma

ODBC Yöneticisi programları işlevselliğini uygulamanıza eklemenize, kullanıcılarınıza bu programları çalıştırmak dosyaları da dağıtmanız gerekir. Bu ODBC dosyaları Visual C++ CD-ROM \OS\System dizininde bulunur. Redistrb.wri dosya ve lisans sözleşmesini aynı dizinde yeniden dağıtabilirsiniz ODBC dosyaların bir listesini içerir.

Dağıtmayı planladığınız herhangi bir ODBC sürücüleri için belgelerine bakın. Hangi DLL'lerin ve diğer dosyaları göndermeye belirlemeniz gerekir. Ayrıca okumalıdır [ODBC bileşenlerini müşterilerinize yeniden dağıtma](../../data/odbc/redistributing-odbc-components-to-your-customers.md), ODBC bileşenleri yeniden dağıtma açıklanır.

Ayrıca, çoğu durumda başka bir dosya eklemek gerekir. ODBC imleç kitaplığı Odbccr32.dll var. Bu kitaplık, düzey 1 sürücüleri İleri ve geri gezinme özelliği sağlar. Ayrıca, anlık görüntüleri destekleme yeteneği sağlar. ODBC İmleç Kitaplığı hakkında daha fazla bilgi için bkz: [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).

Aşağıdaki konular, ODBC ile veritabanı sınıflarını kullanma hakkında daha fazla bilgi sağlar:

- [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC: ODBC Veri Kaynağını Yapılandırma](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC: ODBC API İşlevlerini Doğrudan Çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>Ayrıca bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)<br/>
[ODBC Yöneticisi](../../data/odbc/odbc-administrator.md)