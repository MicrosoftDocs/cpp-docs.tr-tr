---
title: _get_fmode
ms.date: 11/04/2016
apiname:
- _get_fmode
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
- get_fmode
- _get_fmode
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
ms.openlocfilehash: dc4740b20ab7283dd8b9f73f458eaba34e582832
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328051"
---
# <a name="getfmode"></a>_get_fmode

Dosya g/ç işlemleri için varsayılan dosya çevirisi modu alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_fmode(
   int * pmode
);
```

### <a name="parameters"></a>Parametreler

*pmode*<br/>
Geçerli varsayılan modu ile doldurulacak bir tamsayı işaretçisi: **_O_TEXT** veya **_o_bınary**.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır döndürür; bir hata kodu. Varsa *pmode* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **EINVAL**.

## <a name="remarks"></a>Açıklamalar

İşlev değerini alır [_fmode](../../c-runtime-library/fmode.md) genel değişkeni. Bu değişken, alt düzey her ikisi için varsayılan dosya çevirisi modu belirtir ve dosya g/ç işlemleri gibi akış **_aç**, **_pipe**, **fopen**, ve [ freopen](freopen-wfreopen.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<stdlib.h >|\<fcntl.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bakın [_set_fmode](set-fmode.md).

## <a name="see-also"></a>Ayrıca bkz.

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[Metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
