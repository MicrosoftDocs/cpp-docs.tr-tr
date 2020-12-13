---
description: 'Daha fazla bilgi edinin: özel durum Işleme yordamları'
title: Özel Durum İşleme Rutinleri
ms.date: 11/04/2016
f1_keywords:
- c.exceptions
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
ms.openlocfilehash: d241c3ef7f32a96f08d4ad499887963fda031967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331100"
---
# <a name="exception-handling-routines"></a>Özel Durum İşleme Rutinleri

Program yürütme sırasında beklenmeyen olaylardan kurtarmak için C++ özel durum işleme işlevlerini kullanın.

## <a name="exception-handling-functions"></a>Exception-Handling Işlevleri

|İşlev|Kullanın|
|--------------|---------|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|C++ özel durum türü olarak Win32 özel durumlarını (C yapılandırılmış özel durumlar) işleme|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|**Sonlandır** tarafından çağrılacak kendi sonlandırma yordamınıza sahip olun|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|**Beklenmeyen** bir şekilde çağrılacak kendi sonlandırma işlevinizi yükler|
|[sonlandırmayı](../c-runtime-library/reference/terminate-crt.md)|Özel durum oluşturulduktan sonra belirli koşullarda otomatik olarak çağırılır. **Terminate** işlevi, bir **iptali** veya **set_terminate** kullanarak belirlediğiniz bir işlevi çağırır|
|[bek](../c-runtime-library/reference/unexpected-crt.md)|Aramalar veya **set_unexpected** kullanarak belirlediğiniz bir işlevi **sonlandırır** . **Beklenmeyen** Işlev geçerli Microsoft C++ özel durum işleme uygulamasında kullanılmıyor|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
