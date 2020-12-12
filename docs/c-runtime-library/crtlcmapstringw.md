---
description: 'Hakkında daha fazla bilgi edinin: __crtLCMapStringW'
title: __crtLCMapStringW
ms.date: 11/04/2016
api_name:
- __crtLCMapStringW
api_location:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __crtLCMapStringW
helpviewer_keywords:
- __crtLCMapStringW
ms.assetid: 45b4ac0e-438c-4fa3-b4d1-34195f4467d9
ms.openlocfilehash: 57b3f7e961de94d8a3dbd045a1fa1d74681cbfdc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246778"
---
# <a name="__crtlcmapstringw"></a>__crtLCMapStringW

Bir karakter dizesini diğerine eşleyerek, belirtilen bir yerel ayara bağımlı dönüştürmeyi gerçekleştiriyor. Bu işlev, giriş dizesi için bir sıralama anahtarı oluşturmak için de kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
int __crtLCMapStringW(
   LCID    Locale,
   DWORD   dwMapFlags,
   LPCWSTR lpSrcStr,
   int     cchSrc,
   LPWSTR  lpDestStr,
   int     cchDest)
```

#### <a name="parameters"></a>Parametreler

*Ayarlar*<br/>
Yerel ayar tanımlayıcısı. Yerel ayar, dize eşleme veya sıralama anahtarı oluşturma için bir bağlam sağlar. Bir uygulama, `MAKELCID` bir yerel ayar tanımlayıcısı oluşturmak için makroyu kullanabilir.

*dwMapFlags*<br/>
Dize eşleme veya sıralama anahtarı oluşturma sırasında kullanılacak dönüşümün türü.

*lpSrcStr*<br/>
İşlevin, sıralama anahtar üretimi için eşlendiği veya kullandığı kaynak dize işaretçisi. Bu parametrenin bir Unicode dize olduğu varsayılır.

*cchSrc*<br/>
Parametresi tarafından işaret edilen dizenin karakter cinsinden boyutu `lpSrcStr` . Bu sayı null sonlandırıcıyı içerebilir veya içermez.

`cchSrc`-1 değeri, tarafından işaret edilen dizenin `lpSrcStr` null sonlandırılacağını belirtir. Böyle bir durum söz konusu ise ve bu işlev dize eşleme modunda kullanılıyorsa, işlev dizenin kendisinin uzunluğunu hesaplar ve null-ile depolanan eşlenmiş dizeyi sonlandırır `*lpDestStr` .

*lpDestStr*<br/>
İşlevin eşlenen dizeyi veya sıralama anahtarını depoladığı bir arabelleğe yönelik uzun işaretçi.

*cchDest*<br/>
Tarafından işaret edilen arabelleğin karakter cinsinden boyutu `lpDestStr` .

## <a name="return-value"></a>Dönüş Değeri

Değeri `cchDest` sıfır değilse, belirtilen karakter sayısı veya bayt sayısı, `LCMAP_SORTKEY` arabelleğe yazıldığında başarıyı gösterir. Bu sayı, null Sonlandırıcı için oda içerir.

Değeri `cchDest` sıfırsa, arabelleğin karakter cinsinden boyutu veya `LCMAP_SORTKEY` belirtilmişse, çevrilmiş dizeyi veya sıralama anahtarını almak için gerekli olan, başarıyı gösterir. Bu boyut, null Sonlandırıcı için oda içerir.

Sıfır hatayı gösterir. Genişletilmiş hata bilgilerini almak için `GetLastError` işlevini çağırın.

## <a name="remarks"></a>Açıklamalar

`cchSrc`Sıfırdan büyükse ve `lpSrcStr` null ile sonlandırılmış bir dizeyse, `__crtLCMapStringW` `cchSrc` dize uzunluğuna ayarlanır. Ardından `__crtLCMapStringW` , belirtilen parametrelerle işlevin geniş dize (Unicode) sürümünü çağırır `LCMapString` . Bu işlevin parametreleri ve dönüş değeri hakkında daha fazla bilgi için, bkz. [LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__crtLCMapStringW|awint. h|
