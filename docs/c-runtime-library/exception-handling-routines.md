---
title: Özel durum işleme rutinleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.exceptions
dev_langs:
- C++
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eea92c5bfdb54b6c15ae2ae643b2d23b397a3bf6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="exception-handling-routines"></a>Özel Durum İşleme Rutinleri

Program yürütülmesi sırasında beklenmeyen olaylarından kurtarmak için C++ özel durum işleme işlevlerini kullanın.

## <a name="exception-handling-functions"></a>Özel durum işleme işlevleri

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 işlemek özel durumlar (C yapılandırılmış özel durum) C++ olarak yazılan özel durumlar|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Kendi sonlandırma yordamı çağrılacak yüklemek **Sonlandır**|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Çağrılacak kendi sonlandırma işlev yüklemek **beklenmeyen**|
|[Sonlandırma](../c-runtime-library/reference/terminate-crt.md)|Özel durum oluşturulduktan sonra otomatik olarak belirli koşullar altında çağrılır. **Sonlandırmak** işlev çağrıları **abort** veya işlev kullanarak belirtin **set_terminate**|
|[beklenmeyen](../c-runtime-library/reference/unexpected-crt.md)|Çağrıları **sonlandırmak** veya işlev kullanarak belirtin **set_unexpected**. **Beklenmeyen** işlevi, geçerli Microsoft C++ özel durum işleme uygulamasında kullanılamıyor|

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
