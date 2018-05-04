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
ms.openlocfilehash: 1e1f4ebf40bc242d0daf98bbc85c2ea3d1295043
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="executeonexittable-initializeonexittable-registeronexitfunction"></a>_execute_onexit_table, _initialize_onexit_table, _register_onexit_function
Çıkış zaman çağrılacak yordamları yönetir.  
  
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
 [ınout] `table`  
 Onexit işlevi tablonun işaretçi.  
  
 [in] `function`  
 Onexit işlevi tabloya eklemek için bir işlev işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, 0 döndürür. Aksi takdirde, negatif bir değer döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu, altyapı uygulama ayrıntılarını C çalışma zamanı desteklemek için kullanılır ve doğrudan kodunuzdan çağrılmamalıdır işlevlerdir. C çalışma zamanı modülünü kullanan bir *onexit işlevi tablo* yapılan çağrılar tarafından kayıtlı işlevleri dizisini temsil etmek için `atexit`, `at_quick_exit`, ve `_onexit`. Onexit işlevi tablo veri C çalışma zamanı donuk uygulama ayrıntılarını yapısıdır; veri üyeleri anlamını ve sırası değişebilir. Bunlar dış kod tarafından incelenmelidir değil.  
  
 `_initialize_onexit_table` İşlevi onexit işlevi tablonun ilk değerine başlatır.  Onexit işlevi tablo olarak geçmeden önce bu işlevi çağrılmalıdır `_register_onexit_function` veya `_execute_onexit_table`.  
  
 `_register_onexit_function` İşlevi onexit işlevi tablonun sonuna bir işlev ekler.  
  
 `_execute_onexit_table` İşlevi tüm işlevleri onexit işlevi tabloda yürütür, tablosunu temizler ve ardından döndürür. Çağrı sonra `_execute_onexit_table`, tablo geçerli olmayan bir durumda; için yapılan bir çağrı tarafından yeniden gerekir `_initialize_onexit_table` yeniden kullanılmadan önce.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_initialize_onexit_table function`, `_register_onexit_function`, `_execute_onexit_table`|C, C++: \<process.h >|  
  
 `_initialize_onexit_table`, `_register_onexit_function`, Ve `_execute_onexit_table` Microsoft belirli işlevlerdir. Uyumluluk bilgileri için bkz: [Uyumluluk](../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [atexit](../c-runtime-library/reference/atexit.md)   
 [Çıkış, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)