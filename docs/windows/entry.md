---
title: Giriş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.entry
dev_langs:
- C++
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a40ad39b089ea68209bfef2997f015c355ca6893
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414049"
---
# <a name="entry"></a>giriş

Dışarı aktarılan işlevin ya da sabit bir modülün dll giriş noktası belirleyerek belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ entry(
   id
) ]
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Giriş noktası kimliği.

## <a name="remarks"></a>Açıklamalar

**Giriş** C++ özniteliği ile aynı işlevlere sahip [giriş](/windows/desktop/Midl/entry) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [idl_module](../windows/idl-module.md) bir kullanımı örneği için **giriş**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|`idl_module` Özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  