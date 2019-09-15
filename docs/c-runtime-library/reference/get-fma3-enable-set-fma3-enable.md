---
title: _get_FMA3_enable, _set_FMA3_enable
ms.date: 04/05/2018
api_name:
- _get_FMA3_enable
- _set_FMA3_enable
api_location:
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
- math/_get_FMA3_enable
- math/_set_FMA3_enable
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
ms.openlocfilehash: e18db90779ed59a6ca6976f69a5993d94d61c6bc
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955930"
---
# <a name="_get_fma3_enable-_set_fma3_enable"></a>_get_FMA3_enable, _set_FMA3_enable

Hareketli kayan nokta kitaplığı işlevlerinin x64 platformları için derlenmiş kodda FMA3 yönergelerini kullanıp kullanmadığını belirten bir bayrak alır veya ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```

### <a name="parameters"></a>Parametreler

*bayrağıyla*<br/>
X64 platformlarındaki kayan nokta kitaplığı işlevlerinin FMA3 uygulamalarını etkinleştirmek için 1 olarak veya FMA3 yönergelerini kullanmayan uygulamaları kullanmak için 0 olarak ayarlayın.

## <a name="return-value"></a>Dönüş Değeri

Kayan nokta kitaplığı işlevlerinin FMA3 uygulamaları etkinleştirilmişse sıfır olmayan bir değer. Aksi takdirde, sıfır.

## <a name="remarks"></a>Açıklamalar

CRT kitaplığındaki tranmanzara Math kayan nokta işlevlerinde FMA3 yönergelerinin kullanımını etkinleştirmek veya devre dışı bırakmak için **_set_FMA3_enable** işlevini kullanın. Dönüş değeri, değişiklikten sonra kullanımda olan uygulamayı yansıtır. CPU FMA3 yönergelerini desteklemiyorsa, bu işlev kitaplıkta etkinleştirilemez ve dönüş değeri sıfırdır. Kitaplığın geçerli durumunu almak için **_get_FMA3_enable** kullanın. Varsayılan olarak, x64 platformlarında CRT başlangıç kodu, CPU 'nun FMA3 talimatlarını destekleyip desteklemediğini algılar ve kitaplıktaki FMA3 uygulamalarını etkinleştirip devre dışı bırakır.

FMA3 uygulamaları farklı algoritmalar kullandığından, FMA3 uygulamaları etkinleştirildiğinde veya devre dışı bırakıldığında ya da FMA3 desteği olmayan bilgisayarlar arasında hesaplamalar sonucu içindeki hafif farklar observable olabilir. Daha fazla bilgi için bkz. [kayan nokta geçiş sorunları](../../porting/floating-point-migration-issues.md).

## <a name="requirements"></a>Gereksinimler

**_Set_FMA3_enable** ve **_GET_FMA3_ENABLE** Işlevleri yalnızca CRT 'nin x64 sürümlerinde kullanılabilir.

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_FMA3_enable**, **_get_FMA3_enable**| C: \<Math. h ><br />C++: \<cmath > veya \<Math. h >|

**_Set_FMA3_enable** ve **_get_FMA3_enable** işlevleri Microsoft 'a özgüdür. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Kayan Nokta Geçiş Sorunları](../../porting/floating-point-migration-issues.md)<br/>
