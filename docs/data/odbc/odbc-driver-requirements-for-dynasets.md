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
ms.openlocfilehash: 4c436764649a1aa418e12300809482b45224dd46
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86403848"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>Dynaset'ler için ODBC Sürücü Gereksinimleri

MFC ODBC veritabanı sınıflarında dinamik özelliklere sahip kayıt kümeleri vardır; veri kaynağıyla belirli yollarla eşitlenmiş olarak kalırlar. MFC dinamik kümeleri (ancak ileriye doğru kayıt kümeleri değil), düzey 2 API uyumluluğu olan bir ODBC sürücüsü gerektirir. [Veri kaynağınıza](../../data/odbc/data-source-odbc.md) ait sürücü düzey 1 API kümesine uygunsa, yalnızca güncelleştirilebilir ve salt okunurdur ve salt-kayıt kümelerini ve yalnızca yukarı kayıt kümelerini kullanmaya devam edebilirsiniz. Ancak, düzey 1 bir sürücü genişletilmiş getirme ve anahtar kümesi temelli imleçler destekliyorsa dinamik kümeleri destekleyebilir.

ODBC terminolojisinde, dinamik kümeler ve anlık görüntüler imleçler olarak adlandırılır. İmleç bir kayıt kümesindeki konumunu izlemek için kullanılan bir mekanizmadır. Dinamik kümeler için sürücü gereksinimleri hakkında daha fazla bilgi için bkz. [Dynaset](../../data/odbc/dynaset.md). İmleçler hakkında daha fazla bilgi için bkz. [açık veritabanı bağlantısı (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) belgeleri.

> [!NOTE]
> Güncelleştirilebilir kayıt kümeleri için, ODBC sürücünüzün konumlandırılmış Update deyimlerini veya `::SQLSetPos` ODBC API işlevini desteklemesi gerekir. Her ikisi de destekleniyorsa, MFC `::SQLSetPos` verimlilik için kullanır. Alternatif olarak, anlık görüntüler için, güncelleştirilebilir anlık görüntüler (statik imleçler ve konumlandırılmış güncelleştirme deyimleri) için gerekli desteği sağlayan imleç kitaplığını kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[ODBC temelleri](../../data/odbc/odbc-basics.md)
