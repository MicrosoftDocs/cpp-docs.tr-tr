---
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
ms.openlocfilehash: f239d95c0dfd50f765b6f23d7874f01dce085054
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171001"
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
Yerel ayar tanımlayıcısı. Yerel ayar, dize eşleme veya sıralama anahtarı oluşturma için bir bağlam sağlar. Bir uygulama, bir yerel ayar tanımlayıcısı oluşturmak için `MAKELCID` makrosunu kullanabilir.

*dwMapFlags*<br/>
Dize eşleme veya sıralama anahtarı oluşturma sırasında kullanılacak dönüşümün türü.

*lpSrcStr*<br/>
İşlevin, sıralama anahtar üretimi için eşlendiği veya kullandığı kaynak dize işaretçisi. Bu parametrenin bir Unicode dize olduğu varsayılır.

*cchSrc*<br/>
`lpSrcStr` parametresi tarafından işaret edilen dizenin karakter cinsinden boyutu. Bu sayı null sonlandırıcıyı içerebilir veya içermez.

-1 `cchSrc` değeri, `lpSrcStr` tarafından işaret edilen dizenin null sonlandırılacağını belirtir. Böyle bir durum söz konusu ise ve bu işlev dize eşleme modunda kullanılıyorsa, işlev dizenin kendisinin uzunluğunu hesaplar ve null-`*lpDestStr`' de depolanan eşlenmiş dizeyi sonlandırır.

*lpDestStr*<br/>
İşlevin eşlenen dizeyi veya sıralama anahtarını depoladığı bir arabelleğe yönelik uzun işaretçi.

*cchDest*<br/>
`lpDestStr`tarafından işaret edilen arabelleğin karakter cinsinden boyutu.

## <a name="return-value"></a>Dönüş Değeri

`cchDest` değeri sıfır değilse, karakter sayısı veya `LCMAP_SORTKEY` belirtilirse, arabelleğin yazılması başarıyı gösterir. Bu sayı, null Sonlandırıcı için oda içerir.

`cchDest` değeri sıfırsa, arabelleğin karakter cinsinden boyutu veya `LCMAP_SORTKEY` belirtilmişse, çevrilmiş dizeyi veya sıralama anahtarını almak için gerekli, başarıyı gösterir. Bu boyut, null Sonlandırıcı için oda içerir.

Sıfır hatayı gösterir. Genişletilmiş hata bilgilerini almak için `GetLastError` işlevini çağırın.

## <a name="remarks"></a>Açıklamalar

`cchSrc` sıfırdan büyükse ve `lpSrcStr` null ile sonlandırılmış bir dizeyse `__crtLCMapStringW`, `cchSrc` dizenin uzunluğuna göre ayarlanır. `__crtLCMapStringW`, `LCMapString` işlevinin geniş dize (Unicode) sürümünü belirtilen parametrelerle çağırır. Bu işlevin parametreleri ve dönüş değeri hakkında daha fazla bilgi için, bkz. [LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__crtLCMapStringW|awint. h|
