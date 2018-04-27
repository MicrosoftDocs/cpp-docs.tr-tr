---
title: _get_FMA3_enable, _set_FMA3_enable | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
caps.latest.revision: 1
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84087e0883aef3de65081dd2337b8ec588bd1528
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="getfma3enable-setfma3enable"></a>_get_FMA3_enable, _set_FMA3_enable

Soyut matematik kayan nokta kitaplık işlevleri FMA3 yönergeleri derlenmiş kod X64 için kullanıp kullanmadığını belirten bir bayrak alır veya ayarlar platformlar.

## <a name="syntax"></a>Sözdizimi

```C
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```

### <a name="parameters"></a>Parametreler

*Bayrağı*<br/>
X64 soyut matematik kayan nokta kitaplığı işlevlere FMA3 uygulamaları etkinleştirmek için 1 olarak ayarlayın platformları, veya FMA3 yönergeleri kullanmayın uygulamaları kullanmak için 0.

## <a name="return-value"></a>Dönüş Değeri

Soyut matematik kayan nokta kitaplık işlevleri FMA3 uygulamaları etkinleştirilirse sıfır değeri. Aksi durumda, sıfır.

## <a name="remarks"></a>Açıklamalar

Kullanmak **_set_FMA3_enable** işlevini etkinleştirme veya devre dışı CRT Kitaplığı'nda soyut matematik kayan nokta işlevleri FMA3 yönergeleri kullanın. Dönüş değeri kullanın uygulamasında değişiklikten sonra yansıtır. CPU FMA3 yönergeleri desteklemiyorsa, bu işlev Kitaplığı'nda etkinleştiremiyor ve dönüş değeri sıfırdır. Kullanım **_get_FMA3_enable** kitaplığı geçerli durumunu almak için. Varsayılan olarak X64 platformları, CRT başlatma kodunu algılar CPU FMA3 yönergeleri destekler ve etkinleştirir veya kitaplık FMA3 uygulamalarında devre dışı bırakır olup olmadığını.

FMA3 uygulamaları farklı algoritmalar kullandığından, küçük farklar hesaplamalar sonuç observable FMA3 uygulamaları etkin veya devre dışı olduğunda veya yapın veya FMA3 desteklemeyen bilgisayarlar arasında olabilir. Daha fazla bilgi için bkz: [kayan nokta geçiş sorunları](../../porting/floating-point-migration-issues.md).

## <a name="requirements"></a>Gereksinimler

**_Set_FMA3_enable** ve **_get_FMA3_enable** işlevleri X64 kullanılabilir yalnızca CRT sürümleri.

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_FMA3_enable**, **_get_FMA3_enable**| C: \<math.h ><br />C++: \<cmath > veya \<math.h >|

**_Set_FMA3_enable** ve **_get_FMA3_enable** Microsoft belirli işlevlerdir. Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Kayan Nokta Geçiş Sorunları](../../porting/floating-point-migration-issues.md)<br/>
