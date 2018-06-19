---
title: Sağlamlık | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b76235187bad83eb638588cbbd179e93523fdf2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409530"
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

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
 [SetUnhandledExceptionFilter](http://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)<br/>
