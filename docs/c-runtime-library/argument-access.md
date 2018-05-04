---
title: Bağımsız değişken erişimi | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.arguments
dev_langs:
- C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38d4031fcfba793a99688b6fd1cc91a3f1519989
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="argument-access"></a>Bağımsız değişken erişimi

**Va_arg**, **va_end**, ve **va_start** makroları bağımsız değişken sayısı değişken olduğunda işlev bağımsız değişkenleri erişim sağlar. Bu makroları tanımlanan \<stdarg.h > ANSI/ISO C uyumluluğu için hem de \<varargs.h > UNIX sistem V ile uyumluluk için.

## <a name="argument-access-macros"></a>Bağımsız değişken erişimi makroları

|Makrosu|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-----------|-------------------------------|
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Bağımsız değişken listesinden almak|
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|İşaretçi Sıfırla|
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Bağımsız değişken listesi başlangıcına işaretçisi ayarlanmaya|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
