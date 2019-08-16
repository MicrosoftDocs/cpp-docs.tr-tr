---
title: __crtLCMapStringW
ms.date: 11/04/2016
apiname:
- __crtLCMapStringW
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __crtLCMapStringW
helpviewer_keywords:
- __crtLCMapStringW
ms.assetid: 45b4ac0e-438c-4fa3-b4d1-34195f4467d9
ms.openlocfilehash: e79ac5d4072595ef1034a0483b9edc8eada916d8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500224"
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

*locale*<br/>
Yerel ayar tanımlayıcısı. Yerel ayar, dize eşleme veya sıralama anahtarı oluşturma için bir bağlam sağlar. Bir uygulama, `MAKELCID` bir yerel ayar tanımlayıcısı oluşturmak için makroyu kullanabilir.

*dwMapFlags*<br/>
Dize eşleme veya sıralama anahtarı oluşturma sırasında kullanılacak dönüşümün türü.

*lpSrcStr*<br/>
İşlevin, sıralama anahtar üretimi için eşlendiği veya kullandığı kaynak dize işaretçisi. Bu parametrenin bir Unicode dize olduğu varsayılır.

*cchSrc*<br/>
`lpSrcStr` Parametresi tarafından işaret edilen dizenin karakter cinsinden boyutu. Bu sayı null sonlandırıcıyı içerebilir veya içermez.

`lpSrcStr` -1 `cchSrc` değeri, tarafından işaret edilen dizenin null sonlandırılacağını belirtir. Böyle bir durum söz konusu ise ve bu işlev dize eşleme modunda kullanılıyorsa, işlev dizenin kendisinin uzunluğunu hesaplar ve null-ile depolanan `*lpDestStr`eşlenmiş dizeyi sonlandırır.

*lpDestStr*<br/>
İşlevin eşlenen dizeyi veya sıralama anahtarını depoladığı bir arabelleğe yönelik uzun işaretçi.

*cchDest*<br/>
Tarafından `lpDestStr`işaret edilen arabelleğin karakter cinsinden boyutu.

## <a name="return-value"></a>Dönüş Değeri

Değeri `cchDest` sıfır değilse, belirtilen karakter sayısı veya `LCMAP_SORTKEY` bayt sayısı, arabelleğe yazıldığında başarıyı gösterir. Bu sayı, null Sonlandırıcı için oda içerir.

Değeri `cchDest` sıfırsa, arabelleğin karakter cinsinden boyutu veya `LCMAP_SORTKEY` belirtilmişse, çevrilmiş dizeyi veya sıralama anahtarını almak için gerekli olan, başarıyı gösterir. Bu boyut, null Sonlandırıcı için oda içerir.

Sıfır hatayı gösterir. Genişletilmiş hata bilgilerini almak için `GetLastError` işlevini çağırın.

## <a name="remarks"></a>Açıklamalar

Sıfırdan büyükse ve `lpSrcStr` null ile sonlandırılmış bir dizeyse, `__crtLCMapStringW` dize uzunluğuna ayarlanır `cchSrc`. `cchSrc` Ardından `__crtLCMapStringW` ,`LCMapString` belirtilen parametrelerle işlevin geniş dize (Unicode) sürümünü çağırır. Bu işlevin parametreleri ve dönüş değeri hakkında daha fazla bilgi için, bkz. [LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__crtLCMapStringW|awint. h|