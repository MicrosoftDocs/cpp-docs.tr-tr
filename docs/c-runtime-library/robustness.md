---
title: Sağlamlık | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 235eafb6fefb644ce5097b07b6cd55d91adf31aa
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="robustness"></a>Sağlamlık

Aşağıdaki C çalışma zamanı kitaplığı işlevleri programınızı'ların sağlamlığını artırmak için kullanın.

## <a name="run-time-robustness-functions"></a>Çalışma zamanı sağlamlık işlevleri

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Varsa, hata işleme mekanizması aktarır denetim **yeni** işleci başarısız bellek ayıramadı.|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Tanıtıcıları Win32 özel durumlar (C yapılandırılmış özel durum) olarak C++ özel durum belirtilmiş.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Çağrılacak kendi sonlandırma işlev yükler [sonlandırmak](../c-runtime-library/reference/terminate-crt.md).|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Çağrılacak kendi sonlandırma işlev yükler [beklenmeyen](../c-runtime-library/reference/unexpected-crt.md).|

## <a name="see-also"></a>Ayrıca Bkz.

[Kategorilere göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
 [SetUnhandledExceptionFilter](http://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)<br/>
