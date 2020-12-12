---
description: 'Hakkında daha fazla bilgi edinin: _execute_onexit_table, _initialize_onexit_table, _register_onexit_function'
title: _execute_onexit_table, _initialize_onexit_table, _register_onexit_function
ms.date: 4/2/2020
api_name:
- _execute_onexit_table
- _initialize_onexit_table
- _register_onexit_function
- _o__execute_onexit_table
- _o__initialize_onexit_table
- _o__register_onexit_function
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 5bd0449c4b353c6a417e145f864b07794ae40ca3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300079"
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

*table*<br/>
[in, out] OnExit işlevi tablosuna yönelik işaretçi.

*çalışmayacaktır*<br/>
'ndaki OnExit işlev tablosuna eklenecek bir işlevin işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür. Aksi takdirde, negatif bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, C çalışma zamanını desteklemek için kullanılan altyapı uygulama ayrıntılardır ve doğrudan kodunuzdan çağrılmamalıdır. C çalışma zamanı,, ve çağrıları tarafından kaydedilen işlevlerin dizisini temsil eden bir *OnExit işlev tablosu* kullanır `atexit` `at_quick_exit` `_onexit` . OnExit işlev tablosu veri yapısı, C çalışma zamanının donuk bir uygulama ayrıntısıyla yapılır; veri üyelerinin sırası ve anlamı değişebilir. Bunlar harici kod tarafından denetlenmemelidir.

`_initialize_onexit_table`İşlevi OnExit işlevi tablosunu ilk değerine başlatır.  OnExit işlev tablosu ya da öğesine geçirilmeden önce bu işlevin çağrılması gerekir `_register_onexit_function` `_execute_onexit_table` .

`_register_onexit_function`İşlevi OnExit işlevi tablosunun sonuna bir işlev ekler.

`_execute_onexit_table`İşlevi OnExit işlev tablosundaki tüm işlevleri yürütür, tabloyu temizler ve sonra döndürür. Bir çağrısından sonra `_execute_onexit_table` , tablo geçerli olmayan bir durumda; `_initialize_onexit_table` yeniden kullanılmadan önce bir çağrısıyla yeniden başlatılması gerekir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_initialize_onexit_table function`, `_register_onexit_function`, `_execute_onexit_table`|C, C++: \<process.h>|

`_initialize_onexit_table`, `_register_onexit_function` Ve `_execute_onexit_table` işlevleri Microsoft 'a özgüdür. Uyumluluk bilgileri için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)
