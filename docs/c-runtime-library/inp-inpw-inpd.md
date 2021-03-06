---
title: INP, _inp, ınpw, _inpw, _inpd
description: Microsoft C çalışma zamanı kitaplığı 'nın (CRT) eski ve kaldırılmış INP, _inp, ınpw, _inpw ve _inpd işlevlerini açıklar.
ms.date: 12/09/2019
api_name:
- inp
- inpw
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
- inp
- inpw
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
ms.openlocfilehash: aafcd633b2ee04c9ced1520d4ecd1520475d0fea
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556482"
---
# <a name="inp-_inp-inpw-_inpw-_inpd"></a>INP, _inp, ınpw, _inpw, _inpd

Bir bağlantı noktasından, bir bayta ( `inp` , `_inp` ), bir sözcüğe ( `inpw` , `_inpw` ) veya bir çift sözcüğe ( `_inpd` ) giriş.

> [!IMPORTANT]
> Bu işlevler artık kullanılmıyor. Visual Studio 2015 ' den başlayarak bu dosyalar CRT 'da kullanılamaz. \
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Söz dizimi

```cpp
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

### <a name="parameters"></a>Parametreler

*bağ*\
G/ç bağlantı noktası numarası.

## <a name="return-value"></a>Dönüş Değeri

İşlevler, öğesinden okunan Byte, Word veya Double sözcüklerini döndürür `port` . Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

`_inp`, `_inpw` Ve işlevleri, `_inpd` belirtilen giriş bağlantı noktasından sırasıyla bir bayt, bir sözcük ve bir çift sözcük okur. Giriş değeri 0-65.535 aralığında işaretsiz bir kısa tamsayı olabilir.

Bu işlevler doğrudan bir g/ç bağlantı noktasından okunduğu için Kullanıcı kodunda kullanılamaz.

`inp`Ve `inpw` adları, ve işlevleri için eski, kullanım dışı adlardır `_inp` `_inpw` . Daha fazla bilgi için bkz. [POSIX işlev adları](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_inp`|\<conio.h>|
|`_inpw`|\<conio.h>|
|`_inpd`|\<conio.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)\
[outp, outpw, _outp, _outpw _outpd](../c-runtime-library/outp-outpw-outpd.md)
