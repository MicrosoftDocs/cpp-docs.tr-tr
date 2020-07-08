---
title: '##line yönergesi (C/C++)'
description: 'Önişlemci makroları tarafından bildirilen satır numarasını ve dosya adını ayarlamak için kullanılan #line yönergesini açıklar.'
ms.date: 07/06/2020
f1_keywords:
- '#line'
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
ms.openlocfilehash: 7b671cfdf5d5ce43024ac3e038c214396ac8679c
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058626"
---
# <a name="line-directive-cc"></a>#line yönergesi (C/C++)

**#Line** yönergesi Önişlemci 'ya, satır numarası ve dosya adı için derleyicinin bildirilen değerlerini belirli bir satır numarasına ve dosya adına ayarlamaya bildirir.

## <a name="syntax"></a>Syntax

> **`#line`***basamak sırası* ["*dosya adı*"]

## <a name="remarks"></a>Açıklamalar

Derleyici, derleme sırasında bulduğu hatalara başvurmak için satır numarası ve isteğe bağlı dosya adını kullanır. Satır numarası genellikle geçerli giriş satırına başvurur ve dosya adı geçerli giriş dosyasına başvurur. Her satır işlendikten sonra satır numarası artırılır.

*Basamak sırası* değeri herhangi bir tamsayı sabiti olabilir. Makro değiştirme, ön işleme belirteçlerinde kullanılabilir, ancak sonuç doğru söz dizimi olarak değerlendirilmelidir. *Dosya adı* herhangi bir karakter bileşimi olabilir ve çift tırnak işaretleri () içine alınmalıdır `" "` . *Dosya adı* atlanırsa, önceki dosya adı değişmeden kalır.

Kaynak satır numarasını ve dosya adını bir yönerge yazarak değiştirebilirsiniz **`#line`** . **`#line`** Yönergesi, kaynak dosyadaki yönergeyi hemen takip eden çizgi için değeri ayarlar. Çevirmen, önceden tanımlanmış makroların ve değerlerini belirleyebilmek için satır numarasını ve dosya adını kullanır `__FILE__` `__LINE__` . Bu makroları, kendini açıklayıcı hata iletilerini program metnine eklemek için kullanabilirsiniz. Önceden tanımlanmış bu makrolar hakkında daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md).

`__FILE__`Makro, içeriği dosya adı olan ve çift tırnak işaretleriyle () çevrelenen bir dizeye genişletilir `" "` .

Satır numarasını ve dosya adını değiştirirseniz, derleyici önceki değerleri yok sayar ve yeni değerleri işlemeye devam eder. **#Line** yönergesi genellikle program oluşturucuları tarafından kullanılır. Hata iletilerinin oluşturulan program yerine özgün kaynak dosyasına başvurmasına neden olmak için kullanılır.

## <a name="example"></a>Örnek

Aşağıdaki örneklerde ve **`#line`** `__LINE__` makroları gösterilmektedir `__FILE__` .

İlk örnekte, satır numarası 10 ' a, ardından 20 ' ye ayarlanır ve dosya adı *Hello. cpp*olarak değiştirilir.

```cpp
// line_directive.cpp
// Compile by using: cl /W4 /EHsc line_directive.cpp
#include <stdio.h>

int main()
{
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
#line 10
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
#line 20 "hello.cpp"
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
}
```

```Output
This code is on line 7, in file line_directive.cpp
This code is on line 10, in file line_directive.cpp
This code is on line 20, in file hello.cpp
This code is on line 21, in file hello.cpp
```

Bu örnekte, makro `ASSERT` önceden tanımlı makroları kullanır `__LINE__` ve `__FILE__` belirli bir onaylama doğru değilse kaynak dosyayla ilgili bir hata iletisi yazdırır.

```C
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci yönergeleri](../preprocessor/preprocessor-directives.md)
