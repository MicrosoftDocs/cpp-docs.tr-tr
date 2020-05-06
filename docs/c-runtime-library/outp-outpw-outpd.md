---
title: outp, outpw, _outp, _outpw _outpd
description: Microsoft C çalışma zamanı kitaplığı 'nın (CRT) eski ve kaldırılmış outp, outpw, _outp, _outpw ve _outpd işlevlerini açıklar.
ms.date: 12/09/2019
api_name:
- _outpd
- _outp
- _outpw
- outp
- outpw
api_location:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _outpw
- _outpd
- _outp
- outp
- outpw
- outpd
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
ms.openlocfilehash: 3d0342ae94276c7875bcb737b0d1a64aabafd235
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825934"
---
# <a name="outp-outpw-_outp-_outpw-_outpd"></a>outp, outpw, _outp, _outpw _outpd

Bir bağlantı noktasında, bir bayt`outp`(, `_outp`), bir sözcüğe (`outpw`, `_outpw`) veya bir çift sözcüğe (`_outpd`) çıkış verir.

> [!IMPORTANT]
> Bu işlevler artık kullanılmıyor. Visual Studio 2015 ' den başlayarak bu dosyalar CRT 'da kullanılamaz. \
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```cpp
int _outp(
   unsigned short port,
   int databyte
);
unsigned short _outpw(
   unsigned short port,
   unsigned short dataword
);
unsigned long _outpd(
   unsigned short port,
   unsigned long dataword
);
```

### <a name="parameters"></a>Parametreler

*bağ*\
Bağlantı noktası numarası.

*databgh, dataword*\
Çıkış değerleri.

## <a name="return-value"></a>Dönüş Değeri

İşlevler, veri çıktısını döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

`_outp`, `_outpw`Ve `_outpd` işlevleri, belirtilen çıkış bağlantı noktasına sırasıyla bir bayt, bir sözcük ve bir çift sözcük yazar. *Bağlantı noktası* bağımsız değişkeni 0-65.535; aralığında işaretsiz bir tamsayı olabilir. *databayttan* 0-255 aralığında herhangi bir tamsayı olabilir; ve *dataword* , sırasıyla bir tamsayı, işaretsiz kısa tamsayı ve işaretsiz uzun tamsayı aralığında herhangi bir değer olabilir.

Bu işlevler doğrudan bir g/ç bağlantı noktasına yazdıklarından, Kullanıcı kodunda kullanılamaz. Bu işletim sistemlerinde g/ç bağlantı noktalarını kullanma hakkında daha fazla bilgi için, MSDN 'de "Win32 'de seri Iletişim" araması yapın.

`outp` Ve `outpw` adları, `_outp` ve `_outpw` işlevleri için eski, kullanım dışı adlardır. Daha fazla bilgi için bkz. [POSIX işlev adları](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_outp`|\<conio. h>|
|`_outpw`|\<conio. h>|
|`_outpd`|\<conio. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)\
[INP, ınpw, _inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)
