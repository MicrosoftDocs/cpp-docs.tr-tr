---
title: Özel Durum İşleme Rutinleri
ms.date: 11/04/2016
f1_keywords:
- c.exceptions
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
ms.openlocfilehash: 8def356793906074e6fc4b8d7a139ce1915a5f9b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749145"
---
# <a name="exception-handling-routines"></a>Özel Durum İşleme Rutinleri

Program yürütülmesi sırasında beklenmedik olaylardan kurtarmaya için C++ özel durum işleme işlevlerini kullanın.

## <a name="exception-handling-functions"></a>Özel durum işleme işlevleri

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 işlemek özel durumlar (C yapısal özel durumlarını) C++ olarak belirlenmiş özel durumlar|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Kendi sonlandırma yordamı çağrılacak yükleme **Sonlandır**|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Kendi sonlandırma işlevi çağrılacak yükleme **beklenmeyen**|
|[sonlandırma](../c-runtime-library/reference/terminate-crt.md)|Özel durum oluştuktan sonra belirli koşullar altında otomatik olarak çağrılır. **Sonlandırmak** işlev çağrılarında **iptal** veya bir işlevi kullanarak, belirttiğiniz **set_terminate**|
|[beklenmeyen](../c-runtime-library/reference/unexpected-crt.md)|Çağrıları **sonlandırmak** veya bir işlevi kullanarak, belirttiğiniz **set_unexpected**. **Beklenmeyen** işlevi, geçerli Microsoft C++ özel durum işleme uygulaması kullanılamıyor|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
