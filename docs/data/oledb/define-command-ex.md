---
title: DEFINE_COMMAND_EX | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEFINE_COMMAND_EX
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND_EX macro
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dae66cd7458eafd613c34fb03ac4b12f0962271f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="definecommandex"></a>DEFINE_COMMAND_EX
Satır kümesi kullanırken oluşturmak için kullanılan komut belirtir [CCommand](../../data/oledb/ccommand-class.md) sınıfı. Unicode ve ANSI uygulamaları destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
DEFINE_COMMAND_EX(x, wszCommand)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Kullanıcı kayıt (komut) sınıfı adı.  
  
 `wszCommand`  
 [in] Satır kümesi kullanırken oluşturmak için kullanılan komut dizesini [CCommand](../../data/oledb/ccommand-class.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Komut metni belirtmezseniz, varsayılan olarak belirttiğiniz komut dizesi kullanılacak [CCommand::Open](../../data/oledb/ccommand-open.md) yöntemi.  
  
 Bu makrosu uygulama türü ne olursa olsun, Unicode dizelerini kabul eder. Bu makrosu üzerinden tercih edilir [DEFINE_COMMAND](../../data/oledb/define-command.md) Unicode desteklediğinden, ANSI uygulamaları yanı sıra.  
  
## <a name="example"></a>Örnek  
 Bkz: [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)