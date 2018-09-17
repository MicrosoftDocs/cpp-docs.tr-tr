---
title: _execute_onexit_table, _initialize_onexit_table, _register_onexit_function | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- _execute_onexit_table
- _initialize_onexit_table
- _register_onexit_function
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _execute_onexit_table
- process/_execute_onexit_table
- _initialize_onexit_table
- process/_initialize_onexit_table
- _register_onexit_function
- process/_register_onexit_function
dev_langs:
- C++
helpviewer_keywords:
- _execute_onexit_table function
- _initialize_onexit_table function
- _register_onexit_function function
ms.assetid: ad9e4149-d4ad-4fdf-aaaf-cf786fcb4473
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a54e3e5f5f040c80660bd12e6565cef82d09206
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720960"
---
# <a name="executeonexittable-initializeonexittable-registeronexitfunction"></a>_execute_onexit_table, _initialize_onexit_table, _register_onexit_function
Çıkış zaman çağrılacak rutinleri yönetir.  
  
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
[out içinde] Onexit işlevi tablosu işaretçisi.  
  
*İşlevi*<br/>
[in] Onexit işlevi tabloya eklenecek bir işlev işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa 0 döndürür. Aksi takdirde, negatif bir değer döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu, altyapı uygulama ayrıntılarını C çalışma zamanı desteklemek için kullanılır ve doğrudan kodunuzdan çağrılmamalıdır işlevlerdir. C çalışma zamanı kullanan bir *onexit işlevi tablo* yapılan çağrılar tarafından kayıtlı işlevleri dizisini temsil etmek için `atexit`, `at_quick_exit`, ve `_onexit`. Onexit işlevi tablo veri yapısını C çalışma zamanı bir donuk uygulama ayrıntısı olduğunu; veri üyelerinin anlamını ve sırası değişebilir. Bunlar dış kod tarafından incelenmelidir değil.  
  
 `_initialize_onexit_table` İşlevi onexit işlevi tablonun ilk değerini başlatır.  Bu işlev onexit işlevi tablo olarak geçirilmeden önce çağrılmalıdır `_register_onexit_function` veya `_execute_onexit_table`.  
  
 `_register_onexit_function` İşlevi bir işlev onexit işlevi tablonun sonuna ekler.  
  
 `_execute_onexit_table` İşlevi onexit işlevi tablodaki tüm işlevleri yürütür, tablosunu temizler ve ardından döndürür. Çağrısı yapıldıktan sonra `_execute_onexit_table`, tablo, geçerli olmayan bir durumda; yapılan bir çağrıyla yeniden gerekir `_initialize_onexit_table` yeniden kullanılmadan önce.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_initialize_onexit_table function`, `_register_onexit_function`, `_execute_onexit_table`|C, C++: \<process.h >|  
  
 `_initialize_onexit_table`, `_register_onexit_function`, Ve `_execute_onexit_table` Microsoft'a özgü işlevlerdir. Uyumluluk bilgileri için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [atexit](../c-runtime-library/reference/atexit.md)   
 [Çıkış, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)