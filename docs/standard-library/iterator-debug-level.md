---
title: _ITERATOR_DEBUG_LEVEL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
dev_langs:
- C++
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7219ed039e77d0857151c54e73a03a0d1f6a3f5e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL

`_ITERATOR_DEBUG_LEVEL` Makrosu denetimleri olup olmadığını [işaretli yineleyiciler](../standard-library/checked-iterators.md) ve [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md) etkinleştirilir. Bu makrosu yerini alır ve eski birleştirir `_SECURE_SCL` ve `_HAS_ITERATOR_DEBUGGING` makroları.

## <a name="macro-values"></a>Makro değerleri

İçin olası değerler aşağıdaki tabloda özetlenmiştir `_ITERATOR_DEBUG_LEVEL` makrosu.

|Derleme modu|Makro değeri|Açıklama|
|----------------------|----------------|-----------------|
|**Hata ayıklama**|||
||0|İşaretli yineleyiciler devre dışı bırakır ve hata ayıklama yineleyici devre dışı bırakır.|
||1.|İşaretli yineleyiciler etkinleştirir ve hata ayıklama yineleyici devre dışı bırakır.|
||2 (varsayılan)|Hata ayıklama yineleyici sağlar; işaretli yineleyiciler ilgili değildir.|
|**Sürüm**|||
||0 (varsayılan)|Devre dışı bırakır işaretli yineleyiciler.|
||1.|Etkinleştirir işaretli yineleyiciler; hata ayıklama yineleyici ilgili değildir.|

Belirtirseniz yayın modunda derleyici bir hata oluşturur. `_ITERATOR_DEBUG_LEVEL` 2 olarak.

## <a name="remarks"></a>Açıklamalar

`_ITERATOR_DEBUG_LEVEL` Makrosu denetimleri olup olmadığını [işaretli yineleyiciler](../standard-library/checked-iterators.md) olan etkinleştirilebilir ve hata ayıklama modunda olsun [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md) etkinleştirilir. Varsa `_ITERATOR_DEBUG_LEVEL` kapsayıcılarınızı sınırları geçersiz kılınmaz 1 veya 2, işaretli yineleyiciler emin olarak tanımlanır. Varsa `_ITERATOR_DEBUG_LEVEL` 0'dır, Yineleyiciler işaretlenmemiş. Zaman `_ITERATOR_DEBUG_LEVEL` bir çalışma zamanı hatası ve program sonlandırıldığında herhangi güvensiz yineleyici kullanım nedenler 1 tanımlanır. Zaman `_ITERATOR_DEBUG_LEVEL` assert ve olanak sağlayan bir çalışma zamanı hata iletişim kutusu Böl ayıklayıcıya 2, güvenli olmayan yineleyici kullanma nedenleri olarak tanımlanır.

Çünkü `_ITERATOR_DEBUG_LEVEL` makrosu destekleyen benzer işlevsellik `_SECURE_SCL` ve `_HAS_ITERATOR_DEBUGGING` makroları, belirli bir durumda kullanmak için hangi makrosu ve makrosu değeri belirsiz olabilir. Karışıklığı önlemek için yalnızca kullanmanızı öneririz `_ITERATOR_DEBUG_LEVEL` makrosu. Bu tablo eşdeğer açıklar `_ITERATOR_DEBUG_LEVEL` çeşitli değerleri için kullanmak üzere makrosu değeri `_SECURE_SCL` ve `_HAS_ITERATOR_DEBUGGING` var olan kodu.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (yayın varsayılan)|0 (devre dışı)|0 (devre dışı)|
|1.|1 (etkin)|0 (devre dışı)|
|2 (hata ayıklama varsayılan)|(ilgili olmayan)|1 (hata ayıklama modunda etkin)|

İşaretli yineleyiciler ilgili uyarılar devre dışı bırakma hakkında daha fazla bilgi için bkz: [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

### <a name="example"></a>Örnek

İçin bir değer belirtmek için `_ITERATOR_DEBUG_LEVEL` makrosu, kullanım bir [/D](../build/reference/d-preprocessor-definitions.md) komut satırında tanımlayın veya kullanmak için derleyici seçeneği `#define` önce C++ Standart Kitaplığı üstbilgi Kaynak dosyalarınız dahil edilir. Örneğin, komut satırında derlemek için *sample.cpp* hata ayıklama modunda ve hata ayıklama yineleyici desteği kullanmak üzere belirtebilirsiniz `_ITERATOR_DEBUG_LEVEL` makro tanımı:

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

Bir kaynak dosyasında yineleyiciler tanımlamak tüm standart kitaplık üstbilgi önce makrosu belirtin.

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>Ayrıca bkz.

[Denetlenmiş Yineleyiciler](../standard-library/checked-iterators.md)<br/>
[Hata Ayıklama Yineleyici Desteği](../standard-library/debug-iterator-support.md)<br/>
[Güvenli Kitaplıklar: C++ Standart Kitaplık](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
