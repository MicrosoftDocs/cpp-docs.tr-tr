---
title: Sağlamlık
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: c70c9a2bf0b95063fa3f679ca6c3053d2a4f2df5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744578"
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

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](https://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)<br/>
