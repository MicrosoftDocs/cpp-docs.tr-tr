---
title: Sürüm (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87186ee70b5863f51a7cd91f8695052f361bd11c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222538"
---
# <a name="version-c"></a>sürüm (C++)

Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ version(
   "version"
) ]
```

### <a name="parameters"></a>Parametreler

*Sürüm*  
Sürüm numarasını `coclass`. Belirtilmezse, 1.0 .idl dosyasında yer alır.

## <a name="remarks"></a>Açıklamalar

**Sürüm** C++ özniteliği ile aynı işlevlere sahip [sürüm](/windows/desktop/Midl/version) MIDL özniteliği ve oluşturulan .idl dosyasına üzerinden geçirilir.

## <a name="example"></a>Örnek

Bkz: [bağlanabilir](../windows/bindable.md) örnek kullanımını örneğin **sürüm**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass**|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](../windows/compiler-attributes.md)  
[Sınıf Öznitelikleri](../windows/class-attributes.md)  