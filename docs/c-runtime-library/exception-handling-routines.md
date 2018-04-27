---
title: Özel durum işleme rutinleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- c.exceptions
dev_langs:
- C++
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3af35bc623b2646e370c9b72ab39fce6e6413081
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
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

[Kategorilere göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
