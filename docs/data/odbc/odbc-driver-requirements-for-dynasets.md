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
ms.openlocfilehash: c612e8ea91882a6e744a8f47afe0decbeba85358
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367210"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>Dynaset'ler için ODBC Sürücü Gereksinimleri

MFC ODBC veritabanı sınıflarında, dynasets dinamik özelliklere sahip kayıt kümeleri; belirli şekillerde veri kaynağı ile senkronize kalır. MFC dynasets (ancak yalnızca ileri kayıt kümeleri) Düzey 2 API uyumlu bir ODBC sürücüsü gerektirir. [Veri kaynağınızın](../../data/odbc/data-source-odbc.md) sürücüsü Düzey 1 API kümesine uyuyorsa, dynasets değil, hem güncelleştirilebilir hem de salt okunur anlık görüntüleri ve yalnızca ileri kayıt kümelerini kullanabilirsiniz. Ancak, Düzey 1 sürücüsü genişletilmiş getir ve tuş takımı yla çalışan imleçleri destekliyorsa dinamitleri destekleyebilir.

ODBC terminolojisinde, dinamitler ve anlık görüntülerimleç olarak adlandırılır. İmleç, bir kayıt kümesindeki konumunu izlemek için kullanılan bir mekanizmadır. Dinamitler için sürücü gereksinimleri hakkında daha fazla bilgi için [Dynaset'e](../../data/odbc/dynaset.md)bakın. İmleçler hakkında daha fazla bilgi için MSDN belgelerindeki [Açık Veritabanı Bağlantısı (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) SDK'ya bakın.

> [!NOTE]
> Güncelleştirilebilir kayıt kümeleri için, ODBC sürücünüzün konumlandırılmış güncelleştirme deyimlerini veya `::SQLSetPos` ODBC API işlevini desteklemesi gerekir. Her ikisi de desteklenirse, MFC verimlilik için kullanır. `::SQLSetPos` Alternatif olarak, anlık görüntüler için güncelleştirilebilir anlık görüntüler (statik imleçler ve konumlandırılmış güncelleştirme deyimleri) için gerekli desteği sağlayan imleç kitaplığını kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)
