---
title: _setmaxstdio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _setmaxstdio
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
- setmaxstdio
- _setmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c0f54f43b0abb5fff2d13233847b45acdb5f0be
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="setmaxstdio"></a>_setmaxstdio

Aynı anda açık dosyaları sayısı için üst sınır ayarlar **stdio** düzeyi.

## <a name="syntax"></a>Sözdizimi

```C
int _setmaxstdio(
   int newmax
);
```

### <a name="parameters"></a>Parametreler

*newmax*<br/>
Aynı anda açık dosyaları sayısı için yeni maksimum **stdio** düzeyi.

## <a name="return-value"></a>Dönüş Değeri

Döndürür *newmax* başarılıysa; Aksi takdirde -1.

Varsa *newmax* olan değerinden **_IOB_ENTRIES** ya da açıklandığı gibi en yüksek sayısı tanıtıcısı geçersiz parametre işleyicisi işletim sisteminde kullanılabilir çağrılır sonra büyük [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev dönüşleri -1 ve kümelerini yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Setmaxstdio** işlevi değişiklikler, aynı anda açık olabilir dosya sayısı için maksimum değeri **stdio** düzeyi.

C çalışma zamanı g/ç şimdi önceki sürümlerde Win32 platformları pek çok fazla açık dosyalar destekler. 2.048 dosyaları için aynı anda en açık olabilir [lowio düzeyi](../../c-runtime-library/low-level-i-o.md) (diğer bir deyişle, açılır ve yoluyla erişilen **_kurulum Aç**, **_read**, **_write**, g/ç işlevlerin ailesi vb.). En çok 512 dosyaları aynı anda en açık olabilir [stdio düzeyi](../../c-runtime-library/stream-i-o.md) (diğer bir deyişle, açılır ve yoluyla erişilen **fopen**, **fgetc**, **fputc** vb. ailesi işlevlerini). 512 açık dosyaları sınırının **stdio** düzeyi yoluyla 2.048 maksimum artırılmasını **_setmaxstdio** işlevi.

Çünkü **stdio**-gibi işlevler, düzey **fopen**, üstünde oluşturulmuş **lowio** işlevleri, en fazla 2.048; sayısı üst sınırı aynı anda C çalışma zamanı kitaplığı erişilen dosyaların açın.

> [!NOTE]
> Bu üst sınır ötesindedir belirli Win32 platform ve yapılandırması tarafından desteklenen olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz: [_getmaxstdio](getmaxstdio.md) kullanma örneği için **_setmaxstdio**.

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
