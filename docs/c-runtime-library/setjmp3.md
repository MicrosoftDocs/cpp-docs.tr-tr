---
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
ms.openlocfilehash: d7120ddd10322d0b7391608fd388d9f45c1600e8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957805"
---
# <a name="_setjmp3"></a>_setjmp3

İç CRT işlevi. `setjmp` İşlevin yeni bir uygulamasıdır.

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
'ndaki İçinde depolanan ek `DWORD`bilgi sayısı. `optional parameters`

*isteğe bağlı parametreler*<br/>
'ndaki Ek veriler, `setjmp` iç tarafından gönderilir. Birincisi `DWORD` , ek verileri yeniden getirmek ve kalıcı kayıt durumuna dönmek için kullanılan bir işlev işaretçisidir. İkincisi `DWORD` geri yüklenecek deneme düzeyidir. Daha fazla veri, `jmp_buf`içindeki genel veri dizisine kaydedilir.

## <a name="return-value"></a>Dönüş Değeri

Her zaman 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevi bir C++ programda kullanmayın. Bu, desteklenmeyen C++bir iç işlevdir. ' Nin nasıl kullanılacağı `setjmp`hakkında daha fazla bilgi için bkz. [setjmp/longjmp kullanma](../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[setjmp](../c-runtime-library/reference/setjmp.md)
