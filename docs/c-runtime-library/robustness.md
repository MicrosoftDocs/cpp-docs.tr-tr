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
ms.openlocfilehash: a369698e0fcfc97b9713e0e1e5059115cce81dc7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104068"
---
# <a name="robustness"></a>Sağlamlık

Programın sağlamlığını artırmak için aşağıdaki C çalışma zamanı kitaplık işlevleri kullanın.

## <a name="run-time-robustness-functions"></a>Çalışma zamanı sağlamlık işlevleri

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Varsa, hata işleme mekanizması aktarır denetim **yeni** işleci başarısız bellek ayrılamadı.|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Tanıtıcıları Win32 özel durumlar (C yapısal özel durumlarını) olarak C++ özel durumları yazdınız.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Kendi sonlandırma işlevi çağrılacak yükler [sonlandırmak](../c-runtime-library/reference/terminate-crt.md).|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Kendi sonlandırma işlevi çağrılacak yükler [beklenmeyen](../c-runtime-library/reference/unexpected-crt.md).|

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](https://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)<br/>
