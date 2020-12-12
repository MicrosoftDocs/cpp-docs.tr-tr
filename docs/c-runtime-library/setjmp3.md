---
description: 'Hakkında daha fazla bilgi edinin: _setjmp3'
title: _setjmp3
ms.date: 11/04/2016
api_name:
- _setjmp3
api_location:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp3
- _setjmp3
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
ms.openlocfilehash: 07a84601a6f57eca3e7dc71638a964428579b1c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277087"
---
# <a name="_setjmp3"></a>_setjmp3

İç CRT işlevi. İşlevin yeni bir uygulamasıdır `setjmp` .

## <a name="syntax"></a>Sözdizimi

```
int _setjmp3(
   OUT jmp_buf env,
   int count,
   (optional parameters)
);
```

#### <a name="parameters"></a>Parametreler

*env*<br/>
dışı Durum bilgilerini depolamak için arabelleğin adresi.

*biriktirme*<br/>
'ndaki `DWORD`İçinde depolanan ek bilgi sayısı `optional parameters` .

*isteğe bağlı parametreler*<br/>
'ndaki Ek veriler, iç tarafından gönderilir `setjmp` . Birincisi, `DWORD` ek verileri yeniden getirmek ve kalıcı kayıt durumuna dönmek için kullanılan bir işlev işaretçisidir. İkincisi `DWORD` geri yüklenecek deneme düzeyidir. Daha fazla veri, içindeki genel veri dizisine kaydedilir `jmp_buf` .

## <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevi bir C++ programında kullanmayın. C++ desteklemeyen bir iç işlevdir. ' Nin nasıl kullanılacağı hakkında daha fazla bilgi için `setjmp` bkz. [setjmp/longjmp kullanma](../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[setjmp](../c-runtime-library/reference/setjmp.md)
