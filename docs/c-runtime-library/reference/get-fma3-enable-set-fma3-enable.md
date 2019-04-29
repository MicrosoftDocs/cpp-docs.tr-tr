---
title: _get_FMA3_enable, _set_FMA3_enable
ms.date: 04/05/2018
apiname:
- _get_FMA3_enable
- _set_FMA3_enable
apilocation:
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
- math/_get_FMA3_enable
- math/_set_FMA3_enable
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
ms.openlocfilehash: 19eabc3b5a11246d5b0056bdafbb169e2a7de9f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332201"
---
# <a name="getfma3enable-setfma3enable"></a>_get_FMA3_enable, _set_FMA3_enable

Aşkın matematik kitaplığı kayan nokta işlevleri FMA3 yönergeleri derlenmiş kodda X64 için kullanıp kullanmadığını belirten bir bayrak alır veya ayarlar platformlar.

## <a name="syntax"></a>Sözdizimi

```C
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```

### <a name="parameters"></a>Parametreler

*Bayrağı*<br/>
Aşkın matematik kitaplığı kayan nokta işlevleri X64 FMA3 uygulamalarını etkinleştirmek için 1 olarak ayarlayın platformları veya FMA3 yönergeleri kullanmayın uygulamaları kullanmak için 0.

## <a name="return-value"></a>Dönüş Değeri

Aşkın matematik kitaplığı kayan nokta işlevleri FMA3 uygulamaları etkinleştirilirse sıfır olmayan değer. Aksi takdirde sıfır.

## <a name="remarks"></a>Açıklamalar

Kullanma **_set_FMA3_enable** etkinleştirme veya devre dışı FMA3 aşkın matematik kayan nokta işlevleri CRT Kitaplığı'ndaki yönergeleri kullanımını işlevi. Dönüş değeri kullan uygulamasında değişiklikten sonra yansıtır. CPU FMA3 talimatları desteklemiyor, bu işlevi kitaplıkta etkinleştiremez ve döndürülen değer sıfırdır. Kullanım **_get_FMA3_enable** kitaplığı geçerli durumunu almak için. Varsayılan olarak X64 platformlar, CRT başlatma kodunu CPU FMA3 yönergeleri destekler ve sağlar veya algılar kitaplığı FMA3 uygulamalarında devre dışı bırakır olup olmadığını.

FMA3 uygulamaları farklı algoritmalar kullandığından, gözlemlenebilir FMA3 uygulamaları etkin veya devre dışı olduğunda veya FMA3 desteklemez veya bilgisayarlar arasında hesaplamalar sonucunu küçük farklılıklar olabilir. Daha fazla bilgi için [kayan nokta geçiş sorunları](../../porting/floating-point-migration-issues.md).

## <a name="requirements"></a>Gereksinimler

**_Set_FMA3_enable** ve **_get_FMA3_enable** işlevleri bulunan ve yalnızca içinde X64 CRT sürümleri.

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_FMA3_enable**, **_get_FMA3_enable**| C: \<math.h ><br />C++: \<cmath > veya \<math.h >|

**_Set_FMA3_enable** ve **_get_FMA3_enable** Microsoft'a özgü işlevlerdir. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Kayan Nokta Geçiş Sorunları](../../porting/floating-point-migration-issues.md)<br/>
