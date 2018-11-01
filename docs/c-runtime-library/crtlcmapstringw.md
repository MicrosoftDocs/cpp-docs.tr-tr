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
ms.openlocfilehash: 0c3752baba05e18903c32919505d702081d09dca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468425"
---
# <a name="crtlcmapstringw"></a>__crtLCMapStringW

Bir karakter dizesinin başka bir belirtilen yerel ayara bağımlı dönüştürmesi gerçekleştiriliyor eşler. Bu işlev, giriş dizesi için bir sıralama anahtarı oluşturmak için de kullanılabilir.

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
Yerel ayar tanımlayıcısı. Yerel ayar sıralama anahtarı oluşturma ve dize eşleme için bir bağlam sağlar. Bir uygulamanın kullanabileceği `MAKELCID` bir yerel ayar tanımlayıcısı oluşturmak için.

*dwMapFlags*<br/>
Dize eşlemesi veya sıralama anahtarı oluşturma sırasında kullanılacak dönüştürme türü.

*lpSrcStr*<br/>
İşlev eşler veya sıralama anahtar oluşturmak için kullandığı bir kaynak dize işaretçisi. Bu parametre, bir Unicode dizesi olduğu varsayılır.

*cchSrc*<br/>
Tarafından işaret edilen dizenin karakter cinsinden boyutu `lpSrcStr` parametresi. Bu sayı, null Sonlandırıcı dahil etmek veya eklemeniz gerekmez.

A `cchSrc` -1 değerini belirtir dize tarafından gösterilen `lpSrcStr` null sonlandırılmıştır. Bu durumda ve bu işlev, dize eşleme modunda kullanılıyorsa, işlev dizenin uzunluğu kendisi hesaplar ve null-içinde depolanan eşleştirilen dizeyi sonlandıran `*lpDestStr`.

*lpDestStr*<br/>
Uzun işaretçisi işlev eşlenen dize veya sıralama anahtarı depolayan arabellek.

*cchDest*<br/>
İşaret ettiği arabelleğin karakter cinsinden boyutu `lpDestStr`.

## <a name="return-value"></a>Dönüş Değeri

Varsa değerini `cchDest` sıfır karakter veya bayt sayısı, `LCMAP_SORTKEY` belirtilen, yazılan arabellek başarılı olduğunu gösterir. Bu sayı, açmak için bir null Sonlandırıcı içerir.

Varsa değerini `cchDest` sıfır, karakter veya bayt arabellek boyutu durumunda olduğundan `LCMAP_SORTKEY` belirtilen, çevrilmiş almak için gereken dize veya sıralama anahtarı başarı gösterir. Bu boyut, bir null Sonlandırıcı yer içerir.

Sıfır hata gösterir. Genişletilmiş hata bilgilerini almak için arama `GetLastError` işlevi.

## <a name="remarks"></a>Açıklamalar

Varsa `cchSrc` sıfırdan büyük ve `lpSrcStr` null ile sonlandırılmış bir dize ise `__crtLCMapStringW` ayarlar `cchSrc` dize uzunluğu. Ardından `__crtLCMapStringW` geniş dize (Unicode) sürümünü çağırır `LCMapString` işlevi belirtilen parametrelere sahip. Parametreler ve bu işlevin dönüş değeri hakkında daha fazla bilgi için bkz: [LCMapString](/windows/desktop/api/winnls/nf-winnls-lcmapstringa).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__crtLCMapStringW|awint.h|