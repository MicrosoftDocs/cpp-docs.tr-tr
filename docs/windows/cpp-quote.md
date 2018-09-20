---
title: cpp_quote | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.cpp_quote
dev_langs:
- C++
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 00dd1042195bd7593676021cc4f2f1153ec47844
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432860"
---
# <a name="cppquote"></a>cpp_quote

Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan .idl dosyasına yayar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ cpp_quote(
   "statement"
) ];
```

### <a name="parameters"></a>Parametreler

*Deyimi*<br/>
Bir C yönergesi.

## <a name="remarks"></a>Açıklamalar

**Cpp_quote** C++ öznitelik, bir .idl dosyasında bir önişlemci yönergesine koymak istiyorsanız kullanışlıdır.

Ayrıca **cpp_quote** ve MIDL derlemenin bir parçası bir .h dosyası oluşturun. C++ IDL öznitelikleri kullanır ancak bazı görev için bu dosyayı kullanamazsınız bir C++ üstbilgi dosyası varsa, örneğin, daha sonra kullanabilmek için bir MIDL tarafından oluşturulan .h dosyası oluşturmak için derleyebilirsiniz.

**Cpp_quote** özniteliği ile aynı işlevlere sahip [cpp_quote](/windows/desktop/Midl/cpp-quote) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [çift](../windows/dual.md) kullanma hakkında bir örnek için **cpp_quote**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)<br/>
[Tek Başına Öznitelikler](../windows/stand-alone-attributes.md)  