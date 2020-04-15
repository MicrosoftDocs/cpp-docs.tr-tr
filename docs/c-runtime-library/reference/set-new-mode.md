---
title: _set_new_mode
ms.date: 4/2/2020
api_name:
- _set_new_mode
- _o__set_new_mode
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: 3a27717d65714de54f477e4e2b3f243c4631fd8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332317"
---
# <a name="_set_new_mode"></a>_set_new_mode

**Malloc**için yeni bir işleyici modu ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Parametreler

*newhandlermode*<br/>
**Malloc**için yeni işleyici modu ; geçerli değer 0 veya 1'dir.

## <a name="return-value"></a>Dönüş Değeri

Malloc için ayarlanan önceki işleyici modunu **döndürür.** 1'in geri dönüş değeri, belleğin tahsis edilmemesi üzerine, **malloc'un** daha önce yeni işleyici yordamı olarak adlandırdığını gösterir; 0'ın getiri değeri olmadığını gösterir. Yeni *handlermode* bağımsız değişkeni 0 veya 1'e eşit değilse , -1 döndürür.

## <a name="remarks"></a>Açıklamalar

C++ **_set_new_mode** işlevi [malloc](malloc.md)için yeni işleyici modunu ayarlar. Yeni işleyici modu, hata, **malloc** [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamı aramak olup olmadığını gösterir. Varsayılan olarak, **malloc** bellek tahsis başarısız yeni işleyici yordamı aramaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylece **malloc** bellek ayırmayı başaramayınca, **malloc** **yeni** işleyici yordamını yeni işlecinin aynı nedenle başarısız olduğu gibi çağırır. Daha fazla bilgi için *C++ Dil Başvurusu'ndaki* [yeni](../../cpp/new-operator-cpp.md) ve [silme işleçlerini](../../cpp/delete-operator-cpp.md) görün. Varsayılanı geçersiz kılmak için şu çağrıyı

```cpp
_set_new_mode(1);
```

programınızın başında veya Newmode.obj ile bağlantı [(Bkz. Bağlantı Seçenekleri](../../c-runtime-library/link-options.md)).

Bu işlev parametresini doğrular. *Yeni handlermode* 0 veya 1 dışında bir şey ise, işlev [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağırır. Yürütmenin devam etmesine izin verilirse, <strong>_set_new_mode</strong> -1 `EINVAL`döndürür ve **errno'ya** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Ücret -siz](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
