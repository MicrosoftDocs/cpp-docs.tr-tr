---
description: 'Hakkında daha fazla bilgi edinin: TN047: veritabanı Işlem gereksinimlerini gevşetme'
title: 'TN047: Veritabanı İşlem Gereksinimlerini Gevşetme'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: 6f356db75df93466bc392e555246a363e6b52187
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215124"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: Veritabanı İşlem Gereksinimlerini Gevşetme

Bu teknik notun, MFC ODBC veritabanı sınıflarının işlem gereksinimlerini tartışan artık kullanılmıyor. MFC 4,2 ' den önce veritabanı sınıfları, bir **CommitTrans** veya **Rollback** işleminden sonra kayıt kümelerinde, imleçlerin korunması gerekir. ODBC sürücüsü ve DBMS bu imleç koruma düzeyini desteklemiyorsa, veritabanı sınıfları işlemleri etkinleştirmedi.

MFC 4,2 ' den başlayarak, veritabanı sınıfları imleç saklama gerekliliği için gevşek bir kısıtlama gerektirir. Sürücü bunları destekliyorsa, işlemler etkinleştirilir. Ancak, artık açık kayıt kümelerinde bir **CommitTrans** veya **Rollback** işleminin etkisini kontrol etmeniz gerekir. Daha fazla bilgi için bkz. [CDatabase:: GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) ve [CDatabase:: GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) üye işlevleri.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
