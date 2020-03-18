---
title: Hata işleme (CRT)
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
ms.openlocfilehash: d38aaf76a4901b12290782957db90049d815d278
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443314"
---
# <a name="error-handling-crt"></a>Hata işleme (CRT)

Program hatalarını işlemek için bu yordamları kullanın.

## <a name="error-handling-routines"></a>Hata işleme yordamları

|Yordam|Kullanım|
|-------------|---------|
|[onaylama](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu|Programlama mantığı hatalarını test etme; çalışma zamanı kitaplığının hem yayın hem de hata ayıklama sürümlerinde kullanılabilir.|
|[_ASSERT _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makrolar|**Onaylama**işlemine benzer ancak yalnızca çalışma zamanı kitaplığının hata ayıklama sürümlerinde mevcuttur.|
|[clearerr](../c-runtime-library/reference/clearerr.md)|Hata göstergesini sıfırlayın. Bir akışı **geri sarmayı** veya kapatmayı çağırmak, hata göstergesini de sıfırlar.|
|[_eof](../c-runtime-library/reference/eof.md)|Alt düzey g/ç 'de dosya sonu denetimi.|
|[feof](../c-runtime-library/reference/feof.md)|Dosya sonu için test. Dosya sonu, **_read** 0 döndürdüğünde de belirtilir.|
|[ferror](../c-runtime-library/reference/ferror.md)|Akış g/ç hataları için test.|
|[_RPT _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) makrolar|**Printf**öğesine benzer bir rapor oluşturun, ancak yalnızca çalışma zamanı kitaplığının hata ayıklama sürümlerinde kullanılabilir.|
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|C çalışma zamanının, programı sona erdirmek için bir hata iletisi yazdığı varsayılan olmayan bir konum belirlemesini **__error_mode** değiştirir.|
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Saf sanal işlev çağrısının işleyicisini ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

- [Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
