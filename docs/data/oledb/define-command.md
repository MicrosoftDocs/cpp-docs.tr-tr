---
title: DEFINE_COMMAND | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEFINE_COMMAND
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND macro
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f95fafbd9a63c5bf31add8bad1a8757bdcb60ae1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="definecommand"></a>DEFINE_COMMAND
Satır kümesi kullanırken oluşturmak için kullanılan komut belirtir [CCommand](../../data/oledb/ccommand-class.md) sınıfı. Yalnızca belirtilen uygulama türü (ANSI veya Unicode) eşleşen dize türlerini kabul eder.  
  
> [!NOTE]
>  Kullanmanız önerilir [defıne_command_ex](../../data/oledb/define-command-ex.md) yerine `DEFINE_COMMAND`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
DEFINE_COMMAND(x, szCommand)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Kullanıcı kayıt (komut) sınıfı adı.  
  
 `szCommand`  
 [in] Satır kümesi kullanırken oluşturmak için kullanılan komut dizesini [CCommand](../../data/oledb/ccommand-class.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Komut metni belirtmezseniz, varsayılan olarak belirttiğiniz komut dizesi kullanılacak [CCommand::Open](../../data/oledb/ccommand-open.md) yöntemi.  
  
 Unicode olarak uygulamanızı varsa bu makrosu ANSI olarak uygulamanızı varsa ANSI dizelerini veya Unicode dizelerini kabul eder. Kullanmanız önerilir [defıne_command_ex](../../data/oledb/define-command-ex.md) yerine `DEFINE_COMMAND`, önceki ANSI veya Unicode uygulama türü ne olursa olsun, Unicode dizelerini kabul eder.  
  
## <a name="example"></a>Örnek  
 Bkz: [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)