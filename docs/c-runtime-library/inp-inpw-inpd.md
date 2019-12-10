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
ms.openlocfilehash: 48e0e58d2886c5a8bb90a86c81cb785d364666e8
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988718"
---
# <a name="inp-_inp-inpw-_inpw-_inpd"></a>INP, _inp, ınpw, _inpw, _inpd

Bir bağlantı noktasından, bir bayt (`inp`, `_inp`), bir sözcük (`inpw`, `_inpw`) veya bir çift sözcükten (`_inpd`) girişler.

> [!IMPORTANT]
> Bu işlevler artık kullanılmıyor. Visual Studio 2015 ' den başlayarak, bu dosyalar CRT içinde kullanılamaz.  
> Bu API, Windows Çalışma Zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

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

*bağlantı noktası*\
I/O bağlantı noktası numarası.

## <a name="return-value"></a>Dönüş Değeri

İşlevler `port`'tan okunan bayt, kelime veya çift kelime geri döndürür. Döndürülen hata yok.

## <a name="remarks"></a>Açıklamalar

`_inp`, `_inpw` ve `_inpd` işlevleri belirtilen giriş bağlantı noktasından sırasıyla bir bayt, bir sözcük ve bir çift sözcük okur. Giriş değeri 0-65.535 aralığında işaretsiz bir kısa tamsayı olabilir.

Bu işlevler doğrudan bir g/ç bağlantı noktasından okunduğu için Kullanıcı kodunda kullanılamaz.

`inp` ve `inpw` adları `_inp` ve `_inpw` işlevleri için eski, kullanım dışı adlardır. Daha fazla bilgi için bkz. [POSIX işlev adları](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).

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

[Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)\
[outp, outpw, _outp, _outpw _outpd](../c-runtime-library/outp-outpw-outpd.md)
