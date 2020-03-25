---
title: ımportlib (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: 451204aae52d884b9cbc81d7e589028f5cfefae5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166815"
---
# <a name="importlib"></a>importlib

Oluşturulan tür kitaplığı için kullanılabilir başka bir tür kitaplığına derlenmiş olan türleri oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ importlib("tlb_file") ];
```

### <a name="parameters"></a>Parametreler

*tlb_file*<br/>
Geçerli projenin tür kitaplığına içeri aktarılmasını istediğiniz. tlb dosyasının tırnak içinde adı.

## <a name="remarks"></a>Açıklamalar

**Importlib** C++ özniteliği, bir `importlib` deyimin oluşturulan. IDL dosyasının Kitaplık bloğuna yerleştirilmesine neden olur. **Importlib** özniteliği, [ımportlib](/windows/win32/Midl/importlib) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **ımportlib**kullanımına ilişkin bir örnek gösterir:

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
