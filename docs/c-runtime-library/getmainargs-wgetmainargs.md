---
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
ms.openlocfilehash: dbf186fa699e8faf85385fd322482a4373b3fd60
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940342"
---
# <a name="__getmainargs-__wgetmainargs"></a>__getmainargs, __wgetmainargs

Komut satırı ayrıştırmayı çağırır ve geçirilen işaretçilerle bağımsız değişkenleri `main()` geri kopyalar.

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
İçinde `argv`izleyen bağımsız değişkenlerin sayısını içeren bir tamsayı. `argc` parametresi her zaman 1'e eşit veya daha büyüktür.

`_Argv`<br/>
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kural gereği, `argv[0]` programın çağrıldığı komuttur, argv [1] ilk komut satırı bağımsız değişkenidir ve bu nedenle, argv [argc] tarihine kadar her zaman **null**olur. İlk komut satırı bağımsız değişkeni her zaman `argv[1]` ve en son `argv[argc - 1]`bir ' dır.

`_Env`<br/>
Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisi. Bu dizi, **null** bir girdi tarafından sona erdirildi.

`_DoWildCard`<br/>
1 olarak ayarlandıysa komut satırı bağımsız değişkenlerinde joker karakterleri genişler veya 0 olarak ayarlanırsa hiçbir şey yapmaz.

`_StartInfo`<br/>
CRT DLL 'ye geçirilecek diğer bilgiler.

## <a name="return-value"></a>Dönüş Değeri

başarılı olursa 0; başarısız olursa negatif bir değer.

## <a name="remarks"></a>Açıklamalar

Geniş `__getmainargs` olmayan karakter platformlarında ve `__wgetmainargs` geniş karakter (Unicode) platformlarında kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__getmainargs|iç. h|
|__wgetmainargs|iç. h|