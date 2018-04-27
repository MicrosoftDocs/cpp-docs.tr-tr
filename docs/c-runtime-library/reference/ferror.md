---
title: ferror | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ferror
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
- ferror
dev_langs:
- C++
helpviewer_keywords:
- ferror function
- streams, testing for errors
- errors [C++], testing for stream
ms.assetid: 528a34bc-f2aa-4c3f-b89a-5b148e6864f7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3baec1f3f8775b422aa9e0e5da3a6eb3e738e74b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="ferror"></a>ferror

Testler için bir akış üzerinde bir hata oluştu.

## <a name="syntax"></a>Sözdizimi

```C
int ferror(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Herhangi bir hata oluştu, *akış*, **ferror** 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür. Akış ise **NULL**, **ferror** açıklandığı gibi geçersiz bir parametre işleyiciyi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve 0 döndürür.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Ferror** yordamına (işlev olarak hem bir makrosu olarak uygulanan) testleri bir okuma veya hata ile ilişkili dosya yazma için *akış*. Bir hata oluştu, akış için hata göstergesi Akış kapalı veya rewound kadar veya kadar ayarlanmış kalır **clearerr** karşı çağrılır.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**ferror**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [feof](feof.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
