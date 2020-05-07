---
title: _get_fmode
ms.date: 4/2/2020
api_name:
- _get_fmode
- _o__get_fmode
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
- get_fmode
- _get_fmode
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
ms.openlocfilehash: 3e59e608f83874088b64d316c04053b94d8fbfdd
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909851"
---
# <a name="_get_fmode"></a>_get_fmode

Dosya g/ç işlemleri için varsayılan dosya çevirisi modunu alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_fmode(
   int * pmode
);
```

### <a name="parameters"></a>Parametreler

*pmode*<br/>
Geçerli varsayılan modla doldurulacak bir tamsayı işaretçisi: **_O_TEXT** veya **_O_BINARY**.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır döndürür; hatada hata kodu. *Pmode* **null**ise, geçersiz parametre işleyicisi [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

İşlevi [_fmode](../../c-runtime-library/fmode.md) genel değişkeninin değerini alır. Bu değişken, **_open**, **_pipe**, **fopen**ve [serbest açık](freopen-wfreopen.md)gibi alt düzey ve akış dosyası g/ç işlemleri için varsayılan dosya çevirisi modunu belirtir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<Stdlib. h>|\<fcntl. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Set_fmode](set-fmode.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[Metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
