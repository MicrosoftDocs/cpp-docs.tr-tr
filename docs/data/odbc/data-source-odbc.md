---
title: Veri kaynağı (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 39c017113d6f3da0041b5e460666af955c27b0fa
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066155"
---
# <a name="data-source-odbc"></a>Veri Kaynağı (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Veritabanı bağlamında, bir özel veri kümesi, verileri ve bir veri kaynağı adını kullanarak açıklanan veri kaynağının konumunu erişmek için gereken bilgileri bir veri kaynağıdır. Sınıf ile çalışmak için [CDatabase](../../mfc/reference/cdatabase-class.md), veri kaynağı aracılığıyla açık veritabanı bağlantısı (ODBC) yönetici yapılandırılmış olması gerekir. Yerel bir dizinde bir Microsoft Access dosyası ya da ağ üzerinden Microsoft SQL Server çalıştıran uzak bir veritabanı veri kaynakları örnekleridir. Uygulamanızda herhangi bir veri kaynağı bir ODBC sürücüsüne sahip erişebilir.

Bir veya daha fazla veri kaynağı tek seferde uygulamanızda etkin olabilir, her tarafından temsil edilen bir `CDatabase` nesne. Birden fazla bağlantı herhangi bir veri kaynağına da sahip olabilirsiniz. Yüklediğiniz sürücüleri ve, ODBC sürücüleri özelliklerine bağlı olarak yerel veri kaynakları için de uzaktan bağlanabilirsiniz. Veri kaynakları ve ODBC Yöneticisi hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md) ve [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md).

Aşağıdaki konularda, veri kaynakları hakkında daha fazla açıklanır:

- [Veri Kaynağı: Bağlantıları Yönetme (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)

- [Veri Kaynağı: Veri Kaynağının Şemasını Belirleme (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)