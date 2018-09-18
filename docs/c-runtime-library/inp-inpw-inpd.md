---
title: _inp, _inpw, _inpd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _inp
- _inpw
- _inpd
apilocation:
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- inpd
- _inp
- _inpw
- _inpd
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 23e3f28ddb96bb34b38b3dd90ff6720edb1d9224
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041356"
---
# <a name="inp-inpw-inpd"></a>_inp, _inpw, _inpd

Girişler, bir bağlantı noktası, bir bayt (`_inp`), bir sözcük (`_inpw`), veya çift sözcüğe (`_inpd`).

> [!IMPORTANT]
>  Bu işlevler kullanım dışıdır. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz.

> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Bağlantı noktası*<br/>
G/ç bağlantı noktası numarası.

## <a name="return-value"></a>Dönüş Değeri

İşlevler döndürür bayt, kelime veya çift kelime okuma `port`. Döndürülen hata yok.

## <a name="remarks"></a>Açıklamalar

`_inp`, `_inpw`, Ve `_inpd` işlevleri okuma bir bayt, bir sözcük ve bir çift sözcük sırasıyla belirtilen giriş bağlantı noktasından. Giriş değeri 0 - 65,535 aralığında herhangi işaretsiz kısa tamsayı olabilir.

Bu işlevler doğrudan bir I/O bağlantı noktasından okunduğu için kullanıcı kodunda kullanılamaz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_inp`|\<conio.h >|
|`_inpw`|\<conio.h >|
|`_inpd`|\<conio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)<br/>
[_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)