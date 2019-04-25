---
title: _ITERATOR_DEBUG_LEVEL
ms.date: 11/04/2016
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
ms.openlocfilehash: a584fe5a97e251205e750507b27e53e6e7b9a20e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224200"
---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL

_Iterator_debug_level makro denetimleri olmadığını [işaretli yineleyiciler](../standard-library/checked-iterators.md) ve [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md) etkinleştirilir. Bu makronun yerini alır ve eski _SECURE_SCL ve _HAS_ITERATOR_DEBUGGING makroları işlevselliğini bir araya getirir.

## <a name="macro-values"></a>Makro değerleri

_Iterator_debug_level makro için olası değerler aşağıdaki tabloda özetlenmiştir.

|Derleme modu|Makro değeri|Açıklama|
|----------------------|----------------|-----------------|
|**Hata ayıklama**|||
||0|İşaretli yineleyiciler devre dışı bırakır ve hata ayıklama yineleyici devre dışı bırakır.|
||1.|İşaretli yineleyiciler sağlar ve hata ayıklama yineleyici devre dışı bırakır.|
||2 (varsayılan)|Hata ayıklama yineleyici sağlar; işaretli yineleyiciler ilgili değildir.|
|**Sürüm**|||
||0 (varsayılan)|Yineleyiciler işaretli devre dışı bırakır.|
||1.|Etkinleştirir işaretli yineleyiciler; hata ayıklama yineleyici ilgili değildir.|

2 olarak _ıterator_debug_level belirtirseniz yayın modunda, derleyici bir hata oluşturur.

## <a name="remarks"></a>Açıklamalar

_Iterator_debug_level makro denetimleri olmadığını [işaretli yineleyiciler](../standard-library/checked-iterators.md) etkinleştirilebilir ve hata ayıklama modunda olan, ister [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md) etkinleştirilir. _Iterator_debug_level 1 veya 2 tanımlanmışsa, işaretli yineleyiciler kapsayıcılarınızı sınırlarının geçersiz kılınmamasını emin olun. Yineleyiciler _ıterator_debug_level 0 ise, denetlenmez. _Iterator_debug_level 1 tanımlandığında, güvenli olmayan yineleyici kullanım bir çalışma zamanı hatasına neden olur ve program sonlandırılır. _Iterator_debug_level 2 olarak tanımlandığında, güvenli olmayan yineleyici assert ve olanak sağlayan bir çalışma zamanı hata iletişim kutusu, hata ayıklayıcıya girdikten nedenleri kullanın.

_Iterator_debug_level makrosu _SECURE_SCL ve _HAS_ITERATOR_DEBUGGING makroları benzer bir işlevsellik desteklediğinden, hangi makrosu ve makrosu belirli bir durum değeri belirsiz olabilir. Karışıklığı önlemek için yalnızca _ıterator_debug_level makrosu kullanmanızı öneririz. Bu tablo _SECURE_SCL ve varolan kodda _HAS_ITERATOR_DEBUGGING çeşitli değerler için kullanılacak eşdeğer _ıterator_debug_level makrosu değeri açıklar.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (varsayılan sürüm)|0 (devre dışı)|0 (devre dışı)|
|1.|1 (etkin)|0 (devre dışı)|
|2 (hata ayıklama varsayılan)|(ilgili olmayan)|1 (hata ayıklama modunda etkin)|

Denetlenen yineleyiciler hakkında uyarılar devre dışı bırakma hakkında daha fazla bilgi için bkz: [_scl_secure_no_warnıngs](../standard-library/scl-secure-no-warnings.md).

### <a name="example"></a>Örnek

_Iterator_debug_level makro için bir değer belirtmek için kullanın bir [/D](../build/reference/d-preprocessor-definitions.md) komut satırında tanımlayın veya kullanmak için derleyici seçeneği `#define` önce C++ standart kitaplığı üst bilgiler, kaynak dosyalarınızda dahil edilir. Örneğin, komut satırında derlemek için *sample.cpp* hata ayıklama modunda ve hata ayıklama yineleyici desteği _ıterator_debug_level Makro tanımında belirtebilirsiniz:

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

Bir kaynak dosyasında yineleyiciler tanımlayan standart kitaplığı üst bilgileri önce makro belirtin.

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>Ayrıca bkz.

[Denetlenmiş Yineleyiciler](../standard-library/checked-iterators.md)<br/>
[Hata Ayıklama Yineleyici Desteği](../standard-library/debug-iterator-support.md)<br/>
[Güvenli Kitaplıklar: C++ Standart Kitaplığı](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
