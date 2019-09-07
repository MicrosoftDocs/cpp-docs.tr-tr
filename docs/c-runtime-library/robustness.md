---
title: Sağlamlık
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: 108b4c9dde08adf1a3c54c810f68be69bf150472
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739608"
---
# <a name="robustness"></a>Sağlamlık

Programınızın sağlamlığını artırmak için aşağıdaki C çalışma zamanı kitaplığı işlevlerini kullanın.

## <a name="run-time-robustness-functions"></a>Çalışma zamanı sağlamlık Işlevleri

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|**Yeni** operatör bellek ayıramazsa, denetimi hata işleme mekanizmanıza aktarır.|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Oluşturulmuş özel durumlar olarak C++ Win32 özel durumlarını (C yapılandırılmış özel durumlar) işler.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|[Terminate](../c-runtime-library/reference/terminate-crt.md)tarafından çağrılacak kendi sonlandırma işlevinizi kurar.|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|[Beklenmeyen](../c-runtime-library/reference/unexpected-crt.md)bir şekilde çağrılacak kendi sonlandırma işlevinizi kurar.|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setunhandledexceptionfilter)<br/>
