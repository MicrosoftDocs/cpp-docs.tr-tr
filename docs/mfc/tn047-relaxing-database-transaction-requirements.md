---
title: "TN047: Veritabanı işlem gereksinimlerini gevşetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.data
dev_langs: C++
helpviewer_keywords: TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4d8e5e50aea253f92187d936d7b9c684a33fec69
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: Veritabanı İşlem Gereksinimlerini Gevşetme
MFC ODBC veritabanı sınıfları hareket gereksinimlerini ele alınan, bu Teknik Not artık kullanılmıyor. MFC 4.2 önce veritabanı sınıfları imleçler kayıt kümeleri sonra korunması gereken bir **CommitTrans** veya **geri alma** işlemi. ODBC sürücüsü ve DBMS bu düzeyde bir imleç korunması desteklememektedir, veritabanı sınıfları işlemleri etkinleştirmediniz.  
  
 Veritabanı sınıfları MFC 4.2 ile başlayarak, imleç korunması kılmanın kısıtlama rahat. Sürücü bunları destekliyorsa işlemleri etkinleştirilecek. Bununla birlikte, artık etkisini denetlemelisiniz bir **CommitTrans** veya **geri alma** açık kayıt kümeleri işlemi. Üye işlevleri bkz [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) ve [CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)

