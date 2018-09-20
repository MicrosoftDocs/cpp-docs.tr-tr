---
title: 'TN047: Veritabanı işlem gereksinimlerini gevşetme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96f3116f503ffa0ffc461ea2c1a0bdaf8947a0be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427023"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: Veritabanı İşlem Gereksinimlerini Gevşetme

MFC ODBC veritabanı sınıfları işlem gereksinimlerini ele alınan, bu Teknik Not artık kullanımdan kalkmıştır. MFC 4.2 önce veritabanı sınıfları imleçler sonra kayıt kümeleri korunması gereken bir **CommitTrans** veya **geri alma** işlemi. ODBC sürücüsünü ve DBMS bu imleç koruma düzeyini desteklemiyor, veritabanı sınıfları işlemleri etkinleştirmediniz.

Veritabanı sınıfları, MFC 4.2 ile başlayarak, imleç korunması zorunlu kısıtlama rahat. Sürücü bunları destekliyorsa işlemleri etkinleştirilecektir. Bununla birlikte, artık etkisini işaretlemeniz gerekir bir **CommitTrans** veya **geri alma** açık kayıt kümeleri üzerinde işlem. Üye işlevleri [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) ve [CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

