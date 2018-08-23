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
ms.openlocfilehash: f9bc6a88ee7dca0bcd4ad2f87fd3aa4c318d8b9d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604771"
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

*id*  
Giriş noktası kimliği.

## <a name="remarks"></a>Açıklamalar

**Giriş** C++ özniteliği ile aynı işlevlere sahip [giriş](http://msdn.microsoft.com/library/windows/desktop/aa366815) MIDL özniteliği.

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