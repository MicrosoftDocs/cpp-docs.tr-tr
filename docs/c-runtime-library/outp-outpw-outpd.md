---
title: _outp, _outpw, _outpd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _outpd
- _outp
- _outpw
apilocation:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- _outpw
- _outpd
- _outp
- outpd
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 604fe4a5fd3daa2cfef7698cd044c7edc56232b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069645"
---
# <a name="outp-outpw-outpd"></a>_outp, _outpw, _outpd

Bağlantı noktasında, bayt çıktıları (`_outp`), bir sözcük (`_outpw`), veya çift sözcüğe (`_outpd`).

> [!IMPORTANT]
>  Bu işlevler kullanım dışıdır. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz.

> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```

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

#### <a name="parameters"></a>Parametreler
*Bağlantı noktası*<br/>
Bağlantı noktası numarası.

*databyte, dataword*<br/>
Çıkış değerleri.

## <a name="return-value"></a>Dönüş Değeri

İşlevler veri çıkışını geri döndürür. Döndürülen hata yok.

## <a name="remarks"></a>Açıklamalar

`_outp`, `_outpw`, Ve `_outpd` işlevler yazma bir bayt, bir sözcük ve bir çift sözcük sırasıyla belirtilen çıkış bağlantı noktasına. *Bağlantı noktası* bağımsız değişkeni de aralık 0 - 65,535; herhangi bir işaretsiz tamsayı. *databyte* 0 - 255 aralığında herhangi bir tamsayı olabilir ve *dataword* aralığında bir tamsayı, işaretsiz kısa tamsayı ve bir işaretsiz uzun tamsayı değerdeki sırasıyla olabilir.

Bu işlevler doğrudan bir g/ç bağlantı noktasına yazıldığı için kullanıcı kodunda kullanılamaz. Bu işletim sistemlerindeki g/ç bağlantı noktalarını kullanma hakkında daha fazla bilgi için MSDN'de "seri iletişimleri"Win32'de arayın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_outp`|\<conio.h >|
|`_outpw`|\<conio.h >|
|`_outpd`|\<conio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)<br/>
[_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)