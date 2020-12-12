---
description: 'Hakkında daha fazla bilgi edinin: _ITERATOR_DEBUG_LEVEL'
title: _ITERATOR_DEBUG_LEVEL
ms.date: 11/04/2016
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
ms.openlocfilehash: 769b7f3a8eecd3c994ee82b67385f080f0945f33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306644"
---
# <a name="_iterator_debug_level"></a>_ITERATOR_DEBUG_LEVEL

_ITERATOR_DEBUG_LEVEL makrosu, [işaretlenmiş yineleyiciler](../standard-library/checked-iterators.md) ve [hata ayıklama Yineleyici desteğinin](../standard-library/debug-iterator-support.md) etkin olup olmadığını denetler. Bu makro, eski _SECURE_SCL ve makroları _HAS_ITERATOR_DEBUGGING işlevlerinin yerini alır ve birleştirir.

## <a name="macro-values"></a>Makro değerleri

Aşağıdaki tabloda _ITERATOR_DEBUG_LEVEL makrosunun olası değerleri özetlenmektedir.

|Derleme modu|Makro değeri|Açıklama|
|----------------------|----------------|-----------------|
|**Hata ayıklama**|||
||0|İşaretli yineleyiciler devre dışı bırakır ve Yineleyici hata ayıklamayı devre dışı bırakır|
||1|Denetlenen yineleyiciler sağlar ve Yineleyici hata ayıklamayı devre dışı bırakır.|
||2 (varsayılan)|Yineleyici hata ayıklamayı sağlar; denetlenen yineleyiciler ilgili değildir.|
|**Sürüm**|||
||0 (varsayılan)|İşaretli yineleyiciler devre dışı bırakır.|
||1|İşaretli yineleyiciler etkinleştirilir; Yineleyici hata ayıklama ilgili değildir.|

Yayın modunda, _ITERATOR_DEBUG_LEVEL 2 olarak belirtirseniz derleyici bir hata oluşturur.

## <a name="remarks"></a>Açıklamalar

_ITERATOR_DEBUG_LEVEL makrosu, [hata ayıklama Yineleyici desteğinin](../standard-library/debug-iterator-support.md) etkin olup olmadığını [işaretlenen yineleyiciler](../standard-library/checked-iterators.md) ve hata ayıklama modunda olup olmadığını denetler. _ITERATOR_DEBUG_LEVEL 1 veya 2 olarak tanımlanmışsa, denetlenen yineleyiciler kapsayıcılarınızın sınırlarının üzerine yazılmadığından emin olun. _ITERATOR_DEBUG_LEVEL 0 ise yineleyiciler denetlenmez. _ITERATOR_DEBUG_LEVEL 1 olarak tanımlandığında, güvenli olmayan hiçbir Yineleyici kullanımı bir çalışma zamanı hatasına neden olur ve program sonlandırılır. _ITERATOR_DEBUG_LEVEL 2 olarak tanımlandığında, güvenli olmayan Yineleyici kullanımı bir onaylama ve hata ayıklayıcıya kesintiye uğramanızı sağlayan bir çalışma zamanı hata iletişim kutusu sağlar.

_ITERATOR_DEBUG_LEVEL makro _SECURE_SCL ve _HAS_ITERATOR_DEBUGGING makrolarına benzer işlevleri desteklediğinden, belirli bir durumda hangi makro ve makro değerinin kullanılması kesin olmayabilir. Karışıklık oluşmasını önlemek için yalnızca _ITERATOR_DEBUG_LEVEL makrosunu kullanmanızı öneririz. Bu tabloda, var olan koddaki _SECURE_SCL ve _HAS_ITERATOR_DEBUGGING çeşitli değerleri için kullanılacak eşdeğer _ITERATOR_DEBUG_LEVEL makro değeri açıklanmaktadır.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (Yayın varsayılanı)|0 (devre dışı)|0 (devre dışı)|
|1|1 (etkin)|0 (devre dışı)|
|2 (hata ayıklama varsayılanı)|(ilgili değil)|1 (hata ayıklama modunda etkin)|

Denetlenen yineleyiciler hakkında uyarıların devre dışı bırakılması hakkında daha fazla bilgi için bkz. [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

### <a name="example"></a>Örnek

_ITERATOR_DEBUG_LEVEL makroya ilişkin bir değer belirtmek için, komut satırında tanımlamak üzere bir [/d](../build/reference/d-preprocessor-definitions.md) derleyici seçeneği kullanın veya `#define` C++ standart kitaplık üstbilgileri kaynak dosyalarınıza dahil etmeden önce kullanın. Örneğin, komut satırında, hata ayıklama modunda *Sample. cpp* derlemek ve hata ayıklama Yineleyici desteğini kullanmak için _ITERATOR_DEBUG_LEVEL makro tanımını belirtebilirsiniz:

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

Bir kaynak dosyasında, yineleyiciler tanımlayan standart kitaplık başlıklarından önce makroyu belirtin.

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>Ayrıca bkz.

[İşaretli yineleyiciler](../standard-library/checked-iterators.md)\
[Hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md)\
[Güvenli Kitaplıklar: C++ standart kitaplığı](../standard-library/safe-libraries-cpp-standard-library.md)
