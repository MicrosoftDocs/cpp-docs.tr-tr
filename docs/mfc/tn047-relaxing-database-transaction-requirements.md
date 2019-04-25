---
title: 'TN047: Veritabanı işlem gereksinimlerini gevşetme'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: 968420658a90c983d8e6c3eaf1e0c61603fc5441
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305352"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: Veritabanı işlem gereksinimlerini gevşetme

MFC ODBC veritabanı sınıfları işlem gereksinimlerini ele alınan, bu Teknik Not artık kullanımdan kalkmıştır. MFC 4.2 önce veritabanı sınıfları imleçler sonra kayıt kümeleri korunması gereken bir **CommitTrans** veya **geri alma** işlemi. ODBC sürücüsünü ve DBMS bu imleç koruma düzeyini desteklemiyor, veritabanı sınıfları işlemleri etkinleştirmediniz.

Veritabanı sınıfları, MFC 4.2 ile başlayarak, imleç korunması zorunlu kısıtlama rahat. Sürücü bunları destekliyorsa işlemleri etkinleştirilecektir. Bununla birlikte, artık etkisini işaretlemeniz gerekir bir **CommitTrans** veya **geri alma** açık kayıt kümeleri üzerinde işlem. Üye işlevleri [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) ve [CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
