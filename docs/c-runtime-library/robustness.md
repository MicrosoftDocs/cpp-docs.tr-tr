---
description: 'Daha fazla bilgi edinin: sağlamlık'
title: Sağlamlık
ms.date: 11/04/2016
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: 7dfe3d40eae4c67f45d4332ce22255a44c33f728
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284518"
---
# <a name="robustness"></a>Sağlamlık

Programınızın sağlamlığını artırmak için aşağıdaki C çalışma zamanı kitaplığı işlevlerini kullanın.

## <a name="run-time-robustness-functions"></a>Run-Time sağlamlık Işlevleri

|İşlev|Kullanın|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Operatör bellek ayıramazsa, denetimi hata işleme mekanizmanıza aktarır **`new`** .|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 özel durumlarını (C yapılandırılmış özel durumlar) C++ ile yazılmış özel durumlar olarak işler.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|[Terminate](../c-runtime-library/reference/terminate-crt.md)tarafından çağrılacak kendi sonlandırma işlevinizi kurar.|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|[Beklenmeyen](../c-runtime-library/reference/unexpected-crt.md)bir şekilde çağrılacak kendi sonlandırma işlevinizi kurar.|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setunhandledexceptionfilter)<br/>
