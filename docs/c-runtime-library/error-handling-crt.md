---
title: Hata işleme (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.errors
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
ms.openlocfilehash: 7b3a5676c9297b1d7805f92b3a15cc71518ecd65
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551225"
---
# <a name="error-handling-crt"></a>Hata işleme (CRT)

Program hataları işlemek için bu yordamları kullanın.

## <a name="error-handling-routines"></a>Hata işleme rutinleri

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[Assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu|Programlama mantığı hatalarını sınayın. Çalışma Zamanı Kitaplığı sürüm ve hata ayıklama sürümlerinde kullanılabilir.|
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroları|Benzer şekilde **assert**, ancak yalnızca çalışma zamanı kitaplığı hata ayıklama sürümleri kullanılabilir.|
|[clearerr](../c-runtime-library/reference/clearerr.md)|Hata göstergesini sıfırlama. Çağırma **rewind** veya bir akış kapatılırken de hata göstergesi sıfırlar.|
|[_eof](../c-runtime-library/reference/eof.md)|Dosya düşük düzey g/ç sonunda olup olmadığını denetleyin.|
|[feof](../c-runtime-library/reference/feof.md)|Test için dosya sonu. Dosya sonu olup da zaman belirtilen **_read** 0 döndürür.|
|[ferror](../c-runtime-library/reference/ferror.md)|Akış g/ç hataları için test edin.|
|[_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) makroları|Benzer şekilde bir rapor oluşturma **printf**, ancak yalnızca çalışma zamanı kitaplığı hata ayıklama sürümleri kullanılabilir.|
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Değiştirir **__error_mode** C çalışma zamanı hata iletisi büyük olasılıkla program sona erecek bir hata için nereye yazdığını, varsayılan olmayan bir konum belirlemek için.|
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Saf sanal işlev çağrısı için işleyici ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

- [Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
