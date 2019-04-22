---
title: Dynaset'ler için ODBC Sürücü Gereksinimleri
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
ms.openlocfilehash: c44e34023ecdeb994ea3a60ea3b699cd5b1488a3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023834"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>Dynaset'ler için ODBC Sürücü Gereksinimleri

MFC ODBC veritabanı sınıfları içinde dinamik özellikler kümeleriyle dynaset'ler olan; Bunlar belirli yollarla veri kaynağı ile eşitlenmiş olarak kalır. ODBC sürücüsü Düzey 2 API uyumluluğu ile MFC dynaset'ler (ancak değil salt iletme kayıt kümeleri) gerektirir. Varsa sürücüsü, [veri kaynağı](../../data/odbc/data-source-odbc.md) düzeyi 1 API'sine uyan ayarlanırsa, hem güncelleştirilebilir ve salt okunur anlık görüntüler ve salt iletme kayıt kümeleri, ancak dinamik kümeleri kullanmaya devam edebilirsiniz. Ancak, genişletilmiş getirme ve anahtar kümesi temelli imleçler destekliyorsa, düzey 1 sürücü dynaset'ler destekleyebilir.

ODBC terminolojisinde, dinamik kümeler ve anlık görüntüleri için işaretçiler olarak adlandırılır. Bir İmleç konumuna kayıt izlemek için kullanılan bir mekanizmadır. Dynaset'ler için sürücü gereksinimleri hakkında daha fazla bilgi için bkz: [Dynaset](../../data/odbc/dynaset.md). İşaretçiler hakkında daha fazla bilgi için bkz: [açık veritabanı bağlantısı (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) SDK'sı MSDN belgelerinde.

> [!NOTE]
>  Güncelleştirilebilir kayıt kümeleri için ODBC sürücüsünün ya da konumlandırılmış update ifadeleriyle desteklemesi gerekir veya `::SQLSetPos` ODBC API işlevi. Her ikisi de desteklenir, MFC kullanıyorsa `::SQLSetPos` verimlilik için. Alternatif olarak, anlık görüntüler için güncelleştirilebilir için anlık görüntüler (statik imleçler ve konumlandırılmış update ifadeleriyle) gerekli destek sağlayan imleç kitaplığı kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)