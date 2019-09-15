---
title: _outp, _outpw, _outpd
ms.date: 11/04/2016
api_name:
- _outpd
- _outp
- _outpw
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
ms.openlocfilehash: d1e7028ae833e1358ce3199b7e7079535c84d135
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944127"
---
# <a name="_outp-_outpw-_outpd"></a>_outp, _outpw, _outpd

Bir bağlantı noktasında, bir bayt (`_outp`), bir sözcüğe (`_outpw`) veya bir çift sözcüğe (`_outpd`) çıkış verir.

> [!IMPORTANT]
>  Bu işlevler artık kullanılmıyor. Visual Studio 2015 ' den başlayarak, bu dosyalar CRT içinde kullanılamaz.

> [!IMPORTANT]
>  Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
*bağ*<br/>
Bağlantı noktası numarası.

*databgh, dataword*<br/>
Çıkış değerleri.

## <a name="return-value"></a>Dönüş Değeri

İşlevler, veri çıktısını döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

`_outp`, Veişlevleri`_outpd` , belirtilen çıkış bağlantı noktasına sırasıyla bir bayt, bir sözcük ve bir çift sözcük yazar. `_outpw` *Bağlantı noktası* bağımsız değişkeni 0-65.535; aralığında işaretsiz bir tamsayı olabilir. *databayttan* 0-255 aralığında herhangi bir tamsayı olabilir; ve *dataword* , sırasıyla bir tamsayı, işaretsiz kısa tamsayı ve işaretsiz uzun tamsayı aralığında herhangi bir değer olabilir.

Bu işlevler doğrudan bir g/ç bağlantı noktasına yazdıklarından, Kullanıcı kodunda kullanılamaz. Bu işletim sistemlerinde g/ç bağlantı noktalarını kullanma hakkında daha fazla bilgi için, MSDN 'de "Win32 'de seri Iletişim" araması yapın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_outp`|\<conio. h >|
|`_outpw`|\<conio. h >|
|`_outpd`|\<conio. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)<br/>
[_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)
