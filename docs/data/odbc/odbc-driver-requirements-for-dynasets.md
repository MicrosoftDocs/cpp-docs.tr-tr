---
title: Dynaset'ler için ODBC sürücü gereksinimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e59e14f9dbd69104e4ae79de5f6f57de24267706
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064257"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>Dynaset'ler için ODBC Sürücü Gereksinimleri

MFC ODBC veritabanı sınıfları içinde dinamik özellikler kümeleriyle dynaset'ler olan; Bunlar belirli yollarla veri kaynağı ile eşitlenmiş olarak kalır. ODBC sürücüsü Düzey 2 API uyumluluğu ile MFC dynaset'ler (ancak değil salt iletme kayıt kümeleri) gerektirir. Varsa sürücüsü, [veri kaynağı](../../data/odbc/data-source-odbc.md) düzeyi 1 API'sine uyan ayarlanırsa, hem güncelleştirilebilir ve salt okunur anlık görüntüler ve salt iletme kayıt kümeleri, ancak dinamik kümeleri kullanmaya devam edebilirsiniz. Ancak, genişletilmiş getirme ve anahtar kümesi temelli imleçler destekliyorsa, düzey 1 sürücü dynaset'ler destekleyebilir.

ODBC terminolojisinde, dinamik kümeler ve anlık görüntüleri için işaretçiler olarak adlandırılır. Bir İmleç konumuna kayıt izlemek için kullanılan bir mekanizmadır. Dynaset'ler için sürücü gereksinimleri hakkında daha fazla bilgi için bkz: [Dynaset](../../data/odbc/dynaset.md). İşaretçiler hakkında daha fazla bilgi için bkz: [açık veritabanı bağlantısı (ODBC)](/previous-versions/windows/desktop/ms710252) SDK'sı MSDN belgelerinde.

> [!NOTE]
>  Güncelleştirilebilir kayıt kümeleri için ODBC sürücüsünün ya da konumlandırılmış update ifadeleriyle desteklemesi gerekir veya `::SQLSetPos` ODBC API işlevi. Her ikisi de desteklenir, MFC kullanıyorsa `::SQLSetPos` verimlilik için. Alternatif olarak, anlık görüntüler için güncelleştirilebilir için anlık görüntüler (statik imleçler ve konumlandırılmış update ifadeleriyle) gerekli destek sağlayan imleç kitaplığı kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)