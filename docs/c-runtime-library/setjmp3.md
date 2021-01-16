---
description: 'Hakkında daha fazla bilgi edinin: _setjmp3'
title: _setjmp3
ms.date: 1/14/2021
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 9d65f807c34d926485777d49156061196dfc0948
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243105"
---
# `_setjmp3`

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

*`env`*\
dışı Durum bilgilerini depolamak için arabelleğin adresi.

*`count`*\
'ndaki `DWORD`İçinde depolanan ek bilgi sayısı `optional parameters` .

*`optional parameters`*\
'ndaki Ek veriler, iç tarafından gönderilir `setjmp` . Birincisi, `DWORD` ek verileri yeniden getirmek ve kalıcı kayıt durumuna dönmek için kullanılan bir işlev işaretçisidir. İkincisi `DWORD` geri yüklenecek deneme düzeyidir. Daha fazla veri, içindeki genel veri dizisine kaydedilir `jmp_buf` .

## <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevi bir C++ programında kullanmayın. Bu, C++ desteklemeyen bir iç işlevdir. ' Nin nasıl kullanılacağı hakkında daha fazla bilgi için `setjmp` bkz. [setjmp/longjmp kullanma](../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik Işlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)\
[`setjmp`](../c-runtime-library/reference/setjmp.md)
