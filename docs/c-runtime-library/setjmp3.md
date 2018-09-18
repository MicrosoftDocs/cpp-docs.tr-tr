---
title: _setjmp3 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _setjmp3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- setjmp3
- _setjmp3
dev_langs:
- C++
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22416f4036d79f9e9b7c95f1cf9098e450533f39
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054278"
---
# <a name="setjmp3"></a>_setjmp3

İç CRT işlevi. Yeni bir uygulamasını `setjmp` işlevi.

## <a name="syntax"></a>Sözdizimi

```
int _setjmp3(
   OUT jmp_buf env,
   int count,
   (optional parameters)
);
```

#### <a name="parameters"></a>Parametreler

*Env*<br/>
[out] Durum bilgilerini depolamak için arabellek adresi.

*Sayısı*<br/>
[in] Ek sayısı `DWORD`s depolanan bilgilerin `optional parameters`.

*İsteğe bağlı parametreler*<br/>
[in] Tarafından ek veri gönderilen `setjmp` iç. İlk `DWORD` ek veri bırakma ve için bir kalıcı döndürmek için kullanılan bir işlev işaretçisi kayıt durumu olan. İkinci `DWORD` geri yüklenmesi deneyin düzeyidir. Genel veri dizideki herhangi bir veri kaydedilir `jmp_buf`.

## <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlev, bir C++ programında kullanmayın. C++ desteklemez iç bir işlevdir. Nasıl kullanılacağı hakkında daha fazla bilgi için `setjmp`, bkz: [setjmp/longjmp kullanma](../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca Bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[setjmp](../c-runtime-library/reference/setjmp.md)