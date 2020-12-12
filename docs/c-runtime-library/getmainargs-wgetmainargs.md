---
description: 'Hakkında daha fazla bilgi edinin: __getmainargs __wgetmainargs'
title: __getmainargs, __wgetmainargs
ms.date: 11/04/2016
api_name:
- __wgetmainargs
- __getmainargs
api_location:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __wgetmainargs
- __getmainargs
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
ms.openlocfilehash: 6f06f83a72d037df6a0973b24ac92ecade6c21eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181754"
---
# <a name="__getmainargs-__wgetmainargs"></a>__getmainargs, __wgetmainargs

Komut satırı ayrıştırmayı çağırır ve `main()` geçirilen işaretçilerle bağımsız değişkenleri geri kopyalar.

## <a name="syntax"></a>Sözdizimi

```cpp
int __getmainargs(
    int * _Argc,
   char *** _Argv,
   char **_ _Env,
   int _DoWildCard,
_startupinfo _ _StartInfo);

int __wgetmainargs (
   int *_Argc,
   wchar_t ***_Argv,
   wchar_t **__Env,
   int _DoWildCard,
   _startupinfo _ _StartInfo)
```

#### <a name="parameters"></a>Parametreler

`_Argc`<br/>
İçinde izleyen bağımsız değişkenlerin sayısını içeren bir tamsayı `argv` . `argc` parametresi her zaman 1'e eşit veya daha büyüktür.

`_Argv`<br/>
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kural gereği, `argv[0]` programın çağrıldığı komuttur, argv [1] ilk komut satırı bağımsız değişkenidir ve bu nedenle, argv [argc] tarihine kadar her zaman **null** olur. İlk komut satırı bağımsız değişkeni her zaman `argv[1]` ve en son bir ' dır `argv[argc - 1]` .

`_Env`<br/>
Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisi. Bu dizi, **null** bir girdi tarafından sona erdirildi.

`_DoWildCard`<br/>
1 olarak ayarlandıysa komut satırı bağımsız değişkenlerinde joker karakterleri genişler veya 0 olarak ayarlanırsa hiçbir şey yapmaz.

`_StartInfo`<br/>
CRT DLL 'ye geçirilecek diğer bilgiler.

## <a name="return-value"></a>Dönüş Değeri

başarılı olursa 0; başarısız olursa negatif bir değer.

## <a name="remarks"></a>Açıklamalar

`__getmainargs`Geniş olmayan karakter platformlarında ve `__wgetmainargs` geniş karakter (Unicode) platformlarında kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__getmainargs|iç. h|
|__wgetmainargs|iç. h|
