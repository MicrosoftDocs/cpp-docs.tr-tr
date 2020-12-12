---
description: 'Daha fazla bilgi edinin: veri kaynağı (ODBC)'
title: Veri Kaynağı (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
ms.openlocfilehash: 655ba48414a733c6f2704d51c0e2bf1d4edf3ff4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255684"
---
# <a name="data-source-odbc"></a>Veri Kaynağı (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Veritabanı koşullarında, veri kaynağı belirli bir veri kümesidir, bu verilere erişmek için gereken bilgiler ve veri kaynağının konumu veri kaynağı adı kullanılarak açıklanabilir. [CDatabase](../../mfc/reference/cdatabase-class.md)sınıfı ile çalışmak için veri kaynağı, açık veritabanı BAĞLANTıSı (ODBC) Yöneticisi aracılığıyla yapılandırdığınız bir olmalıdır. Veri kaynaklarına örnek olarak, bir ağ üzerinde Microsoft SQL Server çalıştıran uzak bir veritabanı veya yerel bir dizindeki Microsoft Access dosyası sayılabilir. Uygulamanızdan, ODBC sürücünüze sahip olduğunuz herhangi bir veri kaynağına erişebilirsiniz.

Uygulamanızda tek seferde etkin bir veya daha fazla veri kaynağınız olabilir ve her biri bir nesne tarafından temsil edilir `CDatabase` . Ayrıca, herhangi bir veri kaynağına yönelik birden çok eş zamanlı bağlantınız olabilir. Yüklemiş olduğunuz sürücülere ve ODBC sürücülerinizin özelliklerine bağlı olarak, uzak sunucuya ve yerel veri kaynaklarına da bağlanabilirsiniz. Veri kaynakları ve ODBC Yöneticisi hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md) ve [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md).

Aşağıdaki konularda veri kaynakları hakkında daha fazla bilgi açıklanmaktadır:

- [Veri kaynağı: bağlantıları yönetme (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)

- [Veri kaynağı: veri kaynağının şemasını belirleme (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
