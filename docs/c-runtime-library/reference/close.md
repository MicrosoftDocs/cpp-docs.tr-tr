---
title: _close | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _close
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
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _close
dev_langs:
- C++
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e49906a1ea0bf66400a6ac753c5d4041bc47217c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="close"></a>_close

Bir dosyayı kapatır.

## <a name="syntax"></a>Sözdizimi

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık olan dosyaya başvuran dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_close** dosya başarılı bir şekilde kapatıldı 0 döndürür. Dönüş değeri-1 hata gösterir.

## <a name="remarks"></a>Açıklamalar

**_Close** işlev ile ilişkili dosya kapatır *fd*.

Dosya tanımlayıcısı ve temel işletim sistemi dosya işleci kapatılır. Bu nedenle, çağırmak gerekli değildir **CloseHandle** dosyayı ilk olarak Win32 işlevi kullanılarak açılmışsa **CreateFile** ve kullanarak bir dosyaya tanımlayıcısı dönüştürülen **_open_osfhandle**.

Bu işlev parametrelerini doğrular. Varsa *fd* hatalı dosya tanımlayıcısı açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, -1 döndürür işlevleri ve **errno** ayarlanır **EBADF**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_close**|\<io.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [_kurulum Aç](open-wopen.md).

## <a name="see-also"></a>Ayrıca bkz.

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
