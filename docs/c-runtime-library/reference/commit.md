---
description: 'Hakkında daha fazla bilgi edinin: _commit'
title: _commit
ms.date: 4/2/2020
api_name:
- _commit
- _o__commit
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _commit
- commit
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
ms.openlocfilehash: 9ec0a6dad2e1dc7531d99e386adf41e4c444b8d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260689"
---
# <a name="_commit"></a>_commit

Bir dosyayı doğrudan diske boşaltır.

## <a name="syntax"></a>Sözdizimi

```C
int _commit(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık dosyaya başvuran dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

Dosya başarıyla diske başarıyla temizleniyorsa **_commit** 0 döndürür. -1 ' in dönüş değeri bir hatayı gösterir.

## <a name="remarks"></a>Açıklamalar

**_Commit** işlevi, işletim sistemini *FD* ile ilişkili dosyayı diske yazmaya zorlar. Bu çağrı, işletim sisteminin kararından değil, belirtilen dosyanın hemen temizlendiğinden emin olmanızı sağlar.

*FD* geçersiz bir dosya tanımlayıcısıdır, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev-1 döndürür ve **errno** , **EBADF** olarak ayarlanır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**_commit**|\<io.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_write](write.md)<br/>
