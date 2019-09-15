---
title: _execute_onexit_table, _initialize_onexit_table, _register_onexit_function
ms.date: 11/04/2016
api_name:
- _execute_onexit_table
- _initialize_onexit_table
- _register_onexit_function
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _execute_onexit_table
- process/_execute_onexit_table
- _initialize_onexit_table
- process/_initialize_onexit_table
- _register_onexit_function
- process/_register_onexit_function
helpviewer_keywords:
- _execute_onexit_table function
- _initialize_onexit_table function
- _register_onexit_function function
ms.assetid: ad9e4149-d4ad-4fdf-aaaf-cf786fcb4473
ms.openlocfilehash: bf8c61e467796c7bfaedff6918bfbf598ada528e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944382"
---
# <a name="_execute_onexit_table-_initialize_onexit_table-_register_onexit_function"></a>_execute_onexit_table, _initialize_onexit_table, _register_onexit_function

Çıkış zamanında çağrılacak yordamları yönetir.

## <a name="syntax"></a>Sözdizimi

```
int _initialize_onexit_table(
    _onexit_table_t* table
    );

int _register_onexit_function(
    _onexit_table_t* table,
    _onexit_t        function
    );

int _execute_onexit_table(
    _onexit_table_t* table
    );
```

#### <a name="parameters"></a>Parametreler

*tablosundan*<br/>
[in, out] OnExit işlevi tablosuna yönelik işaretçi.

*çalışmayacaktır*<br/>
'ndaki OnExit işlev tablosuna eklenecek bir işlevin işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür. Aksi takdirde, negatif bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, C çalışma zamanını desteklemek için kullanılan altyapı uygulama ayrıntılardır ve doğrudan kodunuzdan çağrılmamalıdır. C çalışma zamanı,, ve `_onexit`çağrıları `atexit` `at_quick_exit`tarafından kaydedilen işlevlerin dizisini temsil eden bir *OnExit işlev tablosu* kullanır. OnExit işlev tablosu veri yapısı, C çalışma zamanının donuk bir uygulama ayrıntısıyla yapılır; veri üyelerinin sırası ve anlamı değişebilir. Bunlar harici kod tarafından denetlenmemelidir.

`_initialize_onexit_table` İşlevi OnExit işlevi tablosunu ilk değerine başlatır.  OnExit işlev tablosu ya `_register_onexit_function` `_execute_onexit_table`da öğesine geçirilmeden önce bu işlevin çağrılması gerekir.

`_register_onexit_function` İşlevi OnExit işlevi tablosunun sonuna bir işlev ekler.

`_execute_onexit_table` İşlevi OnExit işlev tablosundaki tüm işlevleri yürütür, tabloyu temizler ve sonra döndürür. Bir çağrısından `_execute_onexit_table`sonra, tablo geçerli olmayan bir durumda; yeniden `_initialize_onexit_table` kullanılmadan önce bir çağrısıyla yeniden başlatılması gerekir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_initialize_onexit_table function`, `_register_onexit_function`, `_execute_onexit_table`|C, C++: \<Process. h >|

`_initialize_onexit_table`, `_register_onexit_function`Ve işlevleri`_execute_onexit_table` Microsoft 'a özgüdür. Uyumluluk bilgileri için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)
