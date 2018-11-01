---
title: cpp_quote (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: 5a281f9f88412df4d3ee18bff1302b19433e07f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466956"
---
# <a name="cppquote"></a>cpp_quote

Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan .idl dosyasına yayar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>Parametreler

*Deyimi*<br/>
Bir C yönergesi.

## <a name="remarks"></a>Açıklamalar

**Cpp_quote** C++ öznitelik, bir .idl dosyasında bir önişlemci yönergesine koymak istiyorsanız kullanışlıdır.

Ayrıca **cpp_quote** ve MIDL derlemenin bir parçası bir .h dosyası oluşturun. C++ IDL öznitelikleri kullanır ancak bazı görev için bu dosyayı kullanamazsınız bir C++ üstbilgi dosyası varsa, örneğin, daha sonra kullanabilmek için bir MIDL tarafından oluşturulan .h dosyası oluşturmak için derleyebilirsiniz.

**Cpp_quote** özniteliği ile aynı işlevlere sahip [cpp_quote](/windows/desktop/Midl/cpp-quote) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [çift](dual.md) kullanma hakkında bir örnek için **cpp_quote**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)