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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: aa21854f6a8c4b58a510b16e824449a53b91f329
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218539"
---
# <a name="_set_new_mode"></a>_set_new_mode

**Malloc**için yeni bir işleyici modu ayarlar.

## <a name="syntax"></a>Söz dizimi

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Parametreler

*newhandlermode*<br/>
**Malloc**için yeni işleyici modu; geçerli değer 0 veya 1 ' dir.

## <a name="return-value"></a>Dönüş Değeri

**Malloc**için ayarlanan önceki işleyici modunu döndürür. 1 dönüş değeri, daha önce yeni işleyici yordamı olarak adlandırılan **malloc** , bellek ayırma hatası durumunda olduğunu gösterir; 0 dönüş değeri olmadığını gösterir. *Newhandlermode* bağımsız değişkeni 0 veya 1 değerine eşit değilse,-1 döndürür.

## <a name="remarks"></a>Açıklamalar

C++ **_set_new_mode** işlevi, [malloc](malloc.md)için yeni işleyici modunu ayarlar. Yeni işleyici modu, hata durumunda **malloc** 'ın [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamını çağırıp çağırmayacağını gösterir. Varsayılan olarak, **malloc** bellek ayırma hatası üzerine yeni işleyici yordamını çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylece **malloc** bellek ayıramadığında, **malloc** yeni işleyici yordamını **`new`** aynı nedenden dolayı başarısız olduğunda işlecin yaptığı şekilde çağırır. Daha fazla bilgi için bkz. *C++ dil başvurusundaki* [New](../../cpp/new-operator-cpp.md) ve [Delete](../../cpp/delete-operator-cpp.md) işleçleri. Varsayılanı geçersiz kılmak için şunu çağırın:

```cpp
_set_new_mode(1);
```

programınızın başlarında veya NewMode. obj ile bağlantılandırın (bkz. [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Bu işlev, parametresini doğrular. *Newhandlermode* 0 veya 1 ' den başka bir şeydir, Işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa <strong>_set_new_mode</strong> -1 döndürür ve **errno** öğesini olarak ayarlar `EINVAL` .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Süz](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
