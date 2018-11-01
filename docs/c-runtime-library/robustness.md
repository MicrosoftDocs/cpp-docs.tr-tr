---
title: Sağlamlık
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: 9244ba430efab01cd82b8ad773ad669470d67cff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454710"
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
