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
ms.openlocfilehash: c66710fe31b5a657a4976bea7f0aa52aac3e3825
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837092"
---
# <a name="outp-outpw-_outp-_outpw-_outpd"></a>outp, outpw, _outp, _outpw _outpd

Bir bağlantı noktasında, bir bayt ( `outp` , `_outp` ), bir sözcüğe ( `outpw` , `_outpw` ) veya bir çift sözcüğe ( `_outpd` ) çıkış verir.

> [!IMPORTANT]
> Bu işlevler artık kullanılmıyor. Visual Studio 2015 ' den başlayarak bu dosyalar CRT 'da kullanılamaz. \
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Söz dizimi

```cpp
int _outp(
   unsigned short port,
   int data_byte
);
unsigned short _outpw(
   unsigned short port,
   unsigned short data_word
);
unsigned long _outpd(
   unsigned short port,
   unsigned long data_word
);
```

### <a name="parameters"></a>Parametreler

*bağ*\
Bağlantı noktası numarası.

*data_byte, data_word*\
Çıkış değerleri.

## <a name="return-value"></a>Dönüş Değeri

İşlevler, veri çıktısını döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

`_outp`, `_outpw` Ve işlevleri, `_outpd` belirtilen çıkış bağlantı noktasına sırasıyla bir bayt, bir sözcük ve bir çift sözcük yazar. *Bağlantı noktası* bağımsız değişkeni, 0-65.535 aralığında işaretsiz bir tamsayı olabilir. *data_byte* 0-255 aralığında herhangi bir tamsayı olabilir. *data_word* tamsayı, işaretsiz kısa tamsayı ve sırasıyla işaretsiz uzun tamsayı aralığında herhangi bir değer olabilir.

Bu işlevler doğrudan bir g/ç bağlantı noktasına yazdıklarından, Kullanıcı modu Windows kodunda kullanılamaz.

Windows işletim sisteminde g/ç bağlantı noktalarını kullanma hakkında daha fazla bilgi için bkz. [seri iletişimler](/previous-versions/ff802693(v=msdn.10)).

`outp`Ve `outpw` adları, ve işlevleri için eski, kullanım dışı adlardır `_outp` `_outpw` . Daha fazla bilgi için bkz. [POSIX işlev adları](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_outp`|\<conio.h>|
|`_outpw`|\<conio.h>|
|`_outpd`|\<conio.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)\
[`inp`, `inpw`, `_inp`, `_inpw`, `_inpd`](../c-runtime-library/inp-inpw-inpd.md)
