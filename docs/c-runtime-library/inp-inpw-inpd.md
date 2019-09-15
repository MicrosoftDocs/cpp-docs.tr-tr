---
title: _inp, _inpw, _inpd
ms.date: 11/04/2016
api_name:
- _inp
- _inpw
- _inpd
api_location:
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- inpd
- _inp
- _inpw
- _inpd
helpviewer_keywords:
- inp function
- inpw function
- ports, I/O routines
- inpd function
- _inp function
- _inpd function
- I/O [CRT], port
- _inpw function
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
ms.openlocfilehash: 4668002fdf709e3e425ac379f136e228250896d4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944987"
---
# <a name="_inp-_inpw-_inpd"></a>_inp, _inpw, _inpd

Bir bağlantı noktasından, bir bayta (`_inp`), bir sözcüğe (`_inpw`) veya bir çift sözcüğe (`_inpd`) ait girişler.

> [!IMPORTANT]
>  Bu işlevler artık kullanılmıyor. Visual Studio 2015 ' den başlayarak, bu dosyalar CRT içinde kullanılamaz.

> [!IMPORTANT]
>  Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```
int _inp(
   unsigned short port
);
unsigned short _inpw(
   unsigned short port
);
unsigned long _inpd(
   unsigned short port
);
```

#### <a name="parameters"></a>Parametreler

*bağ*<br/>
G/ç bağlantı noktası numarası.

## <a name="return-value"></a>Dönüş Değeri

İşlevler, öğesinden `port`okunan Byte, Word veya Double sözcüklerini döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

`_inp`, Veişlevleri`_inpd` , belirtilen giriş bağlantı noktasından sırasıyla bir bayt, bir sözcük ve bir çift sözcük okur. `_inpw` Giriş değeri 0-65.535 aralığında işaretsiz bir kısa tamsayı olabilir.

Bu işlevler doğrudan bir g/ç bağlantı noktasından okunduğu için Kullanıcı kodunda kullanılamaz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_inp`|\<conio. h >|
|`_inpw`|\<conio. h >|
|`_inpd`|\<conio. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)<br/>
[_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)
