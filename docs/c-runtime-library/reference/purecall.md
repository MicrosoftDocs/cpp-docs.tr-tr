---
title: _purecall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _purecall
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- purecall
- _purecall
dev_langs:
- C++
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3095f6fee4458af5a12662886fdc6b9d81fe07f5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="purecall"></a>_purecall

Varsayılan saf sanal işlev çağrısı hata işleyicisi. Derleyici saf sanal üye işlevi çağrıldığında, bu işlev çağrısı için kod oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Açıklamalar

**_Purecall** Microsoft Visual C++ Derleyici Microsoft'a özgü uygulama ayrıntılarını işlevdir. Bu işlev kodunuz tarafından doğrudan çağrılması amaçlanmamıştır ve ortak üstbilgi bildirim vardır. C çalışma zamanı kitaplığı ortak verilmesini olduğundan burada belgelenmiştir.

Hiçbir uygulama içerdiğinden saf sanal işlevi çağrısı bir hatadır. Derleyici çağırmak için kod oluşturur **_purecall** saf sanal işlevi çağrıldığında hata işleyici işlevi. Varsayılan olarak, **_purecall** program sonlandırır. Sonlandırma önce **_purecall** işlevi çağıran bir **_purecall_handler** bir işlem için ayarlanmışsa işlev. Saf sanal işlev çağrısı, bunları hata ayıklama veya Raporlama amaçları için yakalamak için kendi hata işleyici işlevi yükleyebilirsiniz. Kendi hata işleyicisini kullanmak için olan bir işlev oluşturun **_purecall_handler** imza, ardından [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) geçerli işleyici yapma.

## <a name="requirements"></a>Gereksinimler

**_Purecall** işlevi bir üstbilgi bildirimi sahip değil. **_Purecall_handler** typedef tanımlanmış \<stdlib.h >.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
