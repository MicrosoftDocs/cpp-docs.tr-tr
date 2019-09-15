---
title: _get_fmode
ms.date: 11/04/2016
api_name:
- _get_fmode
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
ms.openlocfilehash: 03e07ea44aadec7c15352bb63fd25aa777ee9bfb
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955879"
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
Geçerli varsayılan mod ile doldurulacak tamsayı işaretçisi: **_O_text** veya **_O_binary**.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır döndürür; hatada hata kodu. *Pmode* **null**ise, geçersiz parametre işleyicisi [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

İşlevi, [_fmode](../../c-runtime-library/fmode.md) genel değişkeninin değerini alır. Bu değişken, hem düşük düzey hem de akış dosyası g/ç işlemleri için **_Aç**, **_pipe**, **fopen**ve [freopen](freopen-wfreopen.md)gibi varsayılan dosya çevirisi modunu belirtir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<Stdlib. h >|\<fcntl. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Set_fmode](set-fmode.md)içindeki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[Metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
