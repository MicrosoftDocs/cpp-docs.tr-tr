---
title: DEFINE_COMMAND | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- DEFINE_COMMAND
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND macro
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51f975b0477d29fbb35880c796f52612456c32c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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