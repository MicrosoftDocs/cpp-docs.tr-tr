---
title: cpp_quote (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 905c9fc41b1b42dffe9c7b39fae0b096cdc24950
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501763"
---
# <a name="cpp_quote"></a>cpp_quote

Belirtilen dizeyi, tırnak karakterleri olmadan, oluşturulan. IDL dosyasına yayar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>Parametreler

*Ekstre*<br/>
C yönergesi.

## <a name="remarks"></a>Açıklamalar

Bir. IDL dosyasına bir Önişlemci yönergesi koymak istiyorsanız, **cpp_quote** C++ özniteliği yararlı olur.

Ayrıca, **cpp_quote** kullanabilir ve MIDL derlemesinin bir parçası olarak bir. h dosyası oluşturabilirsiniz. Örneğin, IDL öznitelikleri kullanan C++ C++ bir başlık dosyanız varsa ancak bazı görevler için bu dosyayı kullanamaz, kullanabilmeniz için onu DERLEYEBILMENIZ gereken bir MIDL tarafından oluşturulan. h dosyası oluşturabilirsiniz.

**Cpp_quote** özniteliği, [cpp_quote](/windows/win32/Midl/cpp-quote) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Örnek için bkz. [](dual.md) **cpp_quote**'in nasıl kullanılacağını gösteren örnek.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)