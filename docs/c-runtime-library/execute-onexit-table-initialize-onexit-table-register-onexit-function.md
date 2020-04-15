---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: a1e35d9e86a43e48849373a1cf1aa07febcd0e33
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351650"
---
# <a name="_execute_onexit_table-_initialize_onexit_table-_register_onexit_function"></a>_execute_onexit_table, _initialize_onexit_table, _register_onexit_function

Çıkış saatinde çağrılacak yordamları yönetir.

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

*Tablo*<br/>
[içinde, dışarı] Çıkış işlev tablosuna işaretçi.

*Işlev*<br/>
[içinde] Çıkış işlev tablosuna eklemek için bir işlev işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, 0 döndürür. Aksi takdirde, negatif bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler C çalışma saatini desteklemek için kullanılan altyapı uygulama ayrıntılarıdır ve doğrudan kodunuzdan çağrılmamalıdır. C çalışma zamanı, aramalar tarafından kaydedilen işlevlerin dizisini `atexit`temsil `at_quick_exit`etmek `_onexit`için bir *çıkış işlev tablosu* kullanır . Onexit işlevi tablosu veri yapısı C çalışma zamanının opak bir uygulama ayrıntısI; veri üyelerinin sırası ve anlamı değişebilir. Bunlar dış kod tarafından denetlenmemelidir.

İşlev, `_initialize_onexit_table` çıkış işlev tablosunu başlangıç değerine doğru başlataz.  Bu işlev, çıkış işlevi tablosu ya da `_register_onexit_function` `_execute_onexit_table`.

İşlev, `_register_onexit_function` bir işlevi çıkış işlev tablosunun sonuna ekler.

İşlev, `_execute_onexit_table` onexit işlev tablosundaki tüm işlevleri yürütür, tabloyu temizler ve sonra döndürür. Bir çağrıdan `_execute_onexit_table`sonra , tablo geçerli olmayan bir durumda; yeniden kullanılmadan `_initialize_onexit_table` önce bir arama ile yeniden başlatılması gerekir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_initialize_onexit_table function`, `_register_onexit_function`, `_execute_onexit_table`|C, C++: \<process.h>|

, `_initialize_onexit_table` `_register_onexit_function`ve `_execute_onexit_table` işlevler Microsoft'a özgüdir. Uyumluluk bilgileri için [bkz.](../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)
