---
title: __getmainargs, __wgetmainargs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __wgetmainargs
- __getmainargs
apilocation:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __wgetmainargs
- __getmainargs
dev_langs:
- C++
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c323780308d71158bf717898a05f3454fabf0c3d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030254"
---
# <a name="getmainargs-wgetmainargs"></a>__getmainargs, __wgetmainargs

Komut satırı Ayrıştırmada çağırır ve bağımsız değişkenleri kopyalar `main()` geçirilen işaretçileri üzerinden geri.

## <a name="syntax"></a>Sözdizimi

```cpp
int __getmainargs(
    int * _Argc,
   char *** _Argv,
   char *** _Env,
   int _DoWildCard,
_startupinfo * _StartInfo);

int __wgetmainargs (
   int *_Argc,
   wchar_t ***_Argv,
   wchar_t ***_Env,
   int _DoWildCard,
   _startupinfo * _StartInfo)

```

#### <a name="parameters"></a>Parametreler

`_Argc`<br/>
İçinde izleyen bağımsız değişkenlerin sayısı içeren bir tamsayı `argv`. `argc` parametresi her zaman 1'e eşit veya daha büyüktür.

`_Argv`<br/>
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kural olarak, `argv[0]` ile programın çağrıldığı komuttur, argv [1] ilk komut satırı bağımsız değişkeni ve benzeri argv [argc] tarihine kadar her zaman **NULL**. İlk komut satırı bağımsız değişkeni her zaman olduğu `argv[1]` ve sonuncu `argv[argc - 1]`.

`_Env`<br/>
Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisi. Bu dizi tarafından sonlandırılır bir **NULL** giriş.

`_DoWildCard`<br/>
Bir tamsayı, komut satırı bağımsız değişkenleri joker karakter kümesi 1 genişletir veya 0 olarak ayarlanırsa, hiçbir şey yapmaz.

`_StartInfo`<br/>
CRT DLL'ye geçirilecek diğer bilgiler.

## <a name="return-value"></a>Dönüş Değeri

başarılıysa 0; işlem başarısız olursa negatif değer.

## <a name="remarks"></a>Açıklamalar

Kullanım `__getmainargs` olmayan geniş karakter platformlarda ve `__wgetmainargs` platformlarında geniş karakter (Unicode).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__getmainargs|internal.h|
|__wgetmainargs|internal.h|