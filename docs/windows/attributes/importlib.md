---
title: ımportlib (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: 004533282ca089a076df6b110d52701abc16f71d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842227"
---
# <a name="importlib"></a>importlib

Oluşturulan tür kitaplığı için kullanılabilir başka bir tür kitaplığına derlenmiş olan türleri oluşturur.

## <a name="syntax"></a>Söz dizimi

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)<br/>
[aktarmaya](import.md)<br/>
[importidl](importidl.md)<br/>
[içeriyor](include-cpp.md)<br/>
[INCLUDELIB](includelib-cpp.md)
