---
title: cpp_quote (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 451313b5bd1eb5011f1175de5c3bcfe6fb054299
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214922"
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

Bir. IDL dosyasına bir Önişlemci yönergesi koymak istiyorsanız **cpp_quote** C++ özniteliği yararlı olur.

Ayrıca, **cpp_quote** kullanabilir ve MIDL derlemesinin bir parçası olarak bir. h dosyası oluşturabilirsiniz. Örneğin, IDL öznitelikleri kullanan C++ C++ bir başlık dosyanız varsa ancak bazı görevler için bu dosyayı kullanamaz, kullanabilmeniz için onu DERLEYEBILMENIZ gereken bir MIDL tarafından oluşturulan. h dosyası oluşturabilirsiniz.

**Cpp_quote** özniteliği [cpp_quote](/windows/win32/Midl/cpp-quote) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Örnek [için bkz](dual.md) . **cpp_quote**nasıl kullanacağınızı kullanın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)
