---
description: 'Hakkında daha fazla bilgi edinin: cpp_quote'
title: cpp_quote (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: fe8424fd16cb75e320f8c1a1f8e3e444cf2185ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333172"
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

Bir. IDL dosyasına bir Önişlemci yönergesi koymak istiyorsanız, **cpp_quote** C++ özniteliği yararlıdır.

Ayrıca, **cpp_quote** kullanabilir ve MIDL derlemesinin bir parçası olarak bir. h dosyası oluşturabilirsiniz. Örneğin, C++ IDL öznitelikleri kullanan bir C++ üst bilgi dosyanız varsa ancak bazı görevler için bu dosyayı kullandıysanız, kullanabilmeniz için onu derleyebilmeniz gereken bir MıDL tarafından oluşturulan. h dosyası oluşturabilirsiniz.

**Cpp_quote** özniteliği [cpp_quote](/windows/win32/Midl/cpp-quote) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Örnek [için bkz](dual.md) . **cpp_quote** nasıl kullanacağınızı kullanın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)
