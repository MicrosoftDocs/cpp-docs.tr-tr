---
title: Hata işleme (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.errors
dev_langs:
- C++
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f39fe3743c023bb0c4cb3130400e9bcb7b97db1b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704853"
---
# <a name="error-handling-crt"></a>Hata işleme (CRT)

Program hataları işlemek için bu yordamları kullanın.

## <a name="error-handling-routines"></a>Hata işleme rutinleri

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[Assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu|Mantık hataları programlama için test; Çalışma Zamanı Kitaplığı sürüm ve hata ayıklama sürümlerinde kullanılabilir.|
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroları|Benzer şekilde **assert**, ancak yalnızca çalışma zamanı kitaplığı hata ayıklama sürümlerinde kullanılabilir.|
|[clearerr](../c-runtime-library/reference/clearerr.md)|Hata göstergesi sıfırlayın. Çağırma **geri sarma** veya bir akış kapatılırken de hata göstergesi sıfırlar.|
|[_eof](../c-runtime-library/reference/eof.md)|Dosya düşük düzey g/ç sonunda olup olmadığını denetleyin.|
|[feof](../c-runtime-library/reference/feof.md)|Dosya sonu için test edin. Dosya sonu olduğu da ne zaman gösterilen **_read** 0 döndürür.|
|[ferror](../c-runtime-library/reference/ferror.md)|Akış g/ç hataları için test edin.|
|[_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) makroları|Benzer şekilde bir raporu oluşturmak **printf**, ancak yalnızca çalışma zamanı kitaplığı hata ayıklama sürümlerinde kullanılabilir.|
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Değiştirir **__error_mode** C çalışma zamanı hata iletisi büyük olasılıkla program sona erer bir hata için nereye yazdığını varsayılan olmayan bir konum belirlemek için.|
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Saf sanal işlev çağrısı için işleyici ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

- [Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
